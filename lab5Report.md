# CSE 15L - Lab Report 5
## Finishing Up the Grading Script from Lab 6
During Lab 6, my lab group only had the time to create a grading script with the 1 test provided with the starter code. Here is the code that we had with our initial grading script:
 - ![image](https://user-images.githubusercontent.com/67081225/224467139-52ce3b05-f0a1-4b13-b9ad-878740e7ae40.png)
 - ![image](https://user-images.githubusercontent.com/67081225/224467186-8d7dcf9e-0259-410f-b2e1-e79b2fe6d7e2.png)
 - ![image](https://user-images.githubusercontent.com/67081225/224467197-f66c80d7-3220-488d-a95b-ade132368dad.png)
 - As you can see from the code and example repositories used with the grading script, `grade.sh`, our grading script only provides a pass or fail score based on the 1 test. For this Lab Report, I want to make the grading script more robust by providing numbers so that the student knows how many test they passed/failed and I want to write more tests in addition to the one provided in the starter code. 

After using ChatGPT for guidance on how to extract the number tests and the number of failed tests from the output of JUnit, I edited the code within `grade.sh` to produce the following:
 - ![image](https://user-images.githubusercontent.com/67081225/224467350-85a746a8-bb4c-41a7-80d8-7fc0404678b5.png)
 - First off, instead of storing values within text files like `success.txt` or `fails.txt`, I decided to use bash variables to store the contents of grep. To extract the number tests and failures from `results.txt`, I used the `grep -o` command which allows to only extract the given phrase of grep from the file. So for example, to get the number of tests I used the `NUMTESTS=$(grep -o 'Tests run: [0-9]*' results.txt | grep -o '[0-9]*')` where the first grep finds where in `results.txt` it can find the phrase `"Tests run: [0-9]"`. The `[0-9]*` is used to match zero or more occurances of any digit from 0 to 9. So when we use grep again after the `|`, we extract the actual number, and since the whole command is surrounded by `$()`, the output will be treated as a numerical value which will be stored in `NUMTESTS`. 
 - We do the same thing for `NUMFAILS` as well as `FULLPASS`. Note that either `NUMTEST`/`NUMFAILS` will be used or `FULLPASS` will be used as all three cannot occur at once from JUnit. So to check if the student recieved a full score, we can check if `FULLPASS` is not equal to 0. If it is, then we can say the student passed the interger value stored in `FULLPASS`. However if `FULLPASS` equals 0, then that means the student missed some tests so we will say that the student missed `NUMFAILS` fails our of `NUMTESTS` tests.

Now that we have improved the grading script, I have added an additional 5 tests to `TestListExamples.java` to test the `merge` method.
 - First I made a test for when the left list is shorter than the right list (the opposite of the given test).
   - ![image](https://user-images.githubusercontent.com/67081225/224509182-6ffe17cf-cd28-42b1-982c-e05c3a570d9b.png)
 - The next two tests are for when either of the left or right lists are empty. The expected result should just be the non empty list
   - ![image](https://user-images.githubusercontent.com/67081225/224509236-f0ae8bbe-c463-4580-99ce-d06089e56d63.png)
 - The third type of test is for non-sequential lists of letters, but they are still in sorted order so the merged list should have all the characters sorted alphabetically.
   - ![image](https://user-images.githubusercontent.com/67081225/224509299-e990ab44-4349-4c6b-921b-95b3478fa226.png)
 - The final type of test is for non-sequential lists of digits that are in sorted order, similar to the previous test for letters.
   - ![image](https://user-images.githubusercontent.com/67081225/224509336-fe742d63-af6c-4b9d-91aa-54bfc63eb04e.png)

I have also added an additional 2 tests for the `filter` method.
 - The first test checks if `filter` found instances of the filter string in the given list. Then the filtered list should contain all strings from the original list that contained the filter string.
   - ![image](https://user-images.githubusercontent.com/67081225/224510828-0ad5e8de-c8e0-43d5-8eb1-4684533f7432.png)
 - The second test checks if `filter` cound not find any instances of the filter string in the given list. The expected output should be an empty list.
   - ![image](https://user-images.githubusercontent.com/67081225/224511011-14509f9b-9e64-4b25-b5a3-2815d6ec08f4.png)    

 - Note that I changed the `IsMoon` class to `IsString` to make it more generalized for all strings. I added a constructor so that I could send in any string I want as the filter. Also, instead of checking if the string is equal, I chose to check if any of the strings in the given list contain the filter string.
   - ![image](https://user-images.githubusercontent.com/67081225/224510728-7517e1e5-6ba1-4e3e-858a-d51fa23c7eb6.png)

Now I will take some of the example student repositories from Lab 6 and run them with my grading script. I will use the following repositories:
 - 



