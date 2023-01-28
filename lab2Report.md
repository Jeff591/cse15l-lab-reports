# CSE 15L - Lab Report 2
## Part 1: StringServer
For this part of the lab, we are tasked with creating a web server that holds a string and when the `/add-message?s=<string>` request is given in the URL, a new string is concatenated with the currently stored string with a newline character seperating them. Then when visitng the web page for the server, the currently stored string on the page.

Here is the code I wrote for the StringServer and StringHandler classes:
- ![StringServerCode](https://user-images.githubusercontent.com/67081225/215285308-f665c7f5-f933-47f2-9efe-037a29e7cc17.PNG)
  - 

Here are two example screenshots of using the `/add-message?s=<string>` request:
- ![StringServerPage](https://user-images.githubusercontent.com/67081225/215285375-ae5c21f2-86b9-4d6c-9e0e-a62810054eea.PNG)
  - In this example, we added `"How are you"` to exsisting string `"Hello\n Bob\n"`by giving the url `http://localhost:4000/add-message?s=How are you`. When this url is given, the `handleRequest(URI url)` method is called from the StringHandler class. The method takes in the url we give as an argument and will return a string to be output to the page. Once in the method, the program checks if the path is `"/"`, which is the root, or if the path contains `"/add-message"`. In our case, the url we provided contains `"/add-message"` so we will then look for the query and check if "s" is present. Ifi it is we will take the string after the "=" and concatenate it, and a `"\n"`, with the string `stored` that is part of the StringHandler class. Then stored is returned from the `handleRequest(URI url)` method.
- ![StringServerPage2](https://user-images.githubusercontent.com/67081225/215285423-c74e8b65-a449-47e4-826a-a070bde51c6b.PNG)

