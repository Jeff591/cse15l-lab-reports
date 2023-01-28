# CSE 15L - Lab Report 2
## Part 1: StringServer
For this part of the lab, we are tasked with creating a web server that holds a string and when the `/add-message?s=<string>` request is given in the URL, a new string is concatenated with the currently stored string with a newline character seperating them. Then when visitng the web page for the server, the currently stored string on the page.

Here is the code I wrote for the StringServer and StringHandler classes:
- ![StringServerCode](https://user-images.githubusercontent.com/67081225/215285308-f665c7f5-f933-47f2-9efe-037a29e7cc17.PNG)
  - 

Here are two example screenshots of using the `/add-message?s=<string>` request:
- ![StringServerPage](https://user-images.githubusercontent.com/67081225/215285375-ae5c21f2-86b9-4d6c-9e0e-a62810054eea.PNG)
  - In this example, we added `"How are you"` to exsisting string `"Hello\nBob\n"`by giving the url `http://localhost:4000/add-message?s=How are you`. When this url is given, the `handleRequest(URI url)` method is called from the StringHandler class. The method takes in the url we give as an argument and will return a string to be output to the page. Once in the method, the program checks if the path is `"/"`, which is the root, or if the path contains `"/add-message"`. In our case, the url we provided contains `"/add-message"` so we will then look for the query and check if `"s"` is present. If it is we will take the string after the `"="` and concatenate it, and a `"\n"`, with the string `stored` that is part of the StringHandler class. Then stored is returned from the `handleRequest(URI url)` method. `stored` is changed from `"Hello\n Bob\n"` to `"Hello\nBob\nHow are you\n"` by the end of the method.
- ![StringServerPage2](https://user-images.githubusercontent.com/67081225/215285423-c74e8b65-a449-47e4-826a-a070bde51c6b.PNG)
  - In this example, we added `"I'm fine thank you!"` to exsisting string `"Hello\nBob\nHow are you?\n"`by giving the url `http://localhost:4000/add-message?s=I'm fine thank you!`. When this url is given, the `handleRequest(URI url)` method is called from the StringHandler class. The method takes in the url we give as an argument and will return a string to be output to the page. Once in the method, the program checks if the path is `"/"`, which is the root, or if the path contains `"/add-message"`. In our case, the url we provided contains `"/add-message"` so we will then look for the query and check if `"s"` is present. If it is we will take the string after the `"="` and concatenate it, and a `"\n"`, with the string `stored` that is part of the StringHandler class. Then stored is returned from the `handleRequest(URI url)` method. `stored` is changed from `"Hello\nBob\nHow are you?\n"` to `"Hello\nBob\nHow are you?\nI'm fine thank you!\n"` by the end of the method.

## Part 2: List Methods
For this part of the lab, we will take a look at the bugs within ListExamples.java specifically for the `static List<String> filter(List<String> list, StringChecker sc)` method.

First we will give a failure-inducing input for the buggy program:
- ```
  public class ListTests{
      @Test
      public void testFilter()
      {
          List<String> input = new ArrayList<String>();
          input.add("apple");
          input.add("pineapple");
          input.add("orange");
          StringChecker check = new StringChecker1("app");
          List<String> expected = new ArrayList<String>();
          expected.add("apple");
          expected.add("pineapple");
          assertEquals(expected, ListExamples.filter(input, check));
      }
  }
  ```
Now let's give a input that does not induce a failure that continues from the ListTests class:
- ```
  @Test
  public void testFilter2()
  {
      List<String> input = new ArrayList<String>();
      input.add("apple");
      input.add("orange");
      StringChecker check = new StringChecker1("app");
      List<String> expected = new ArrayList<String>();
      expected.add("apple");
      assertEquals(expected, ListExamples.filter(input, check));
  }
  ```

Also since there is no concrete implementation for StringChecker, we will create a StringChecker1 that implements the StringChecker interface. StringChecker1 will contain the `boolean checkString(String s)` method which will only return true if the given string matches the check string intialized in the StringChecker1 constructor `StringChecker1(String input)`
  - ```
    public class StringChecker1 implements StringChecker
    {
        String check;
        StringChecker1(String input)
        {
            check = input;
        }

        public boolean checkString(String s)
        {
            if (s.contains(check)) return true;
            return false;
        }
    }
    ```
When we run JUnit with our test, we expect that the filter method will take out any strings from the input list that do not contain the string for the check StringChecker object while maintaining the ordering of the list. Therefore we would expect the list to be {"apple", "pineapple"} for testFilter() and {"apple"} for testFilter2(), however instead we get the following output from JUnit:
  - ![image](https://user-images.githubusercontent.com/67081225/215291119-6f08ed45-91ae-4d06-a59a-70fd27f844ee.png)
  - As we can see, the testFilter() test returned {"pineapple", "apple"} instead which is not the correct ordering. But testFilter2() seems to have run fine.

For a list of strings that only has only has one valid string like in testFilter2(), no problem arises from ordering as there only one way to order the resulting list. However when we have multiple valid strings like in testFilter(), we run into the ordering problems. So we should look at the static List<String> filter(List<String> list, StringChecker sc)` method inside ListExamples.java.
- Here is a screenshot of the bugged code:
  - ```
    static List<String> filter(List<String> list, StringChecker sc) {
      List<String> result = new ArrayList<>();
      for(String s: list) {
        if(sc.checkString(s)) {
          result.add(0, s);
        }
      }
      return result;
    }
    ```
  - The problem here is that when adding the strings to the result list, we always add to the front of the list rather to the back which will actually reverse the original ordering of the list. So in order to fix that, we should keep track of the index or counter that starts from 0 and then increments each time a new string is added to result through `result.add(index, s);`.
- Here is a screenshot of the fixed code:
  - ```
    static List<String> filter(List<String> list, StringChecker sc) {
      List<String> result = new ArrayList<>();
      int index = 0;
      for(String s: list) {
        if(sc.checkString(s)) {
          //FIX: it is always adding at the front instead of the back
          result.add(index, s);
          index++;
        }
      }
      return result;
    }
    ```
- Then if we run the JUnit tests again we get:
  - ![image](https://user-images.githubusercontent.com/67081225/215291490-d2d57e6f-ad57-4eb4-b9b0-24b5d6bb57e8.png)
  




