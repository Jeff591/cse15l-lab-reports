# CSE 15L - Lab Report 5
## Finishing Up the Grading Script from Lab 6
During Lab 6, my lab group only had the time to create a grading script with the 1 test provided with the starter code. Here is the code that we had with our initial grading script:
 - ```
   CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

   rm -rf student-submission
   git clone $1 student-submission
   echo 'Finished cloning'

   cd student-submission

   if [[ -f ListExamples.java ]]
   then
       echo "ListExamples found"
   else 
       echo "need file ListExamples.java"
       exit 1
   fi

   cp ../TestListExamples.java ./
   cp ../Server.java ./
   cp ../GradeServer.java ./
   mkdir lib
   cp ../lib/hamcrest-core-1.3.jar lib/
   cp ../lib/junit-4.13.2.jar lib/


   javac -cp $CPATH *.java
   if [[ -f ListExamples.class ]] && [[ -f TestListExamples.class ]]
   then
       echo "Compiled files"
   else
       echo "Files did not compile correctly"
       exit 1
   fi

   java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > results.txt
   grep "Tests run: " results.txt > fails.txt
   grep "OK (" results.txt > success.txt
   if [[ "./fails.txt" == `find ./ -type f -empty` ]]
   then
       echo "You Passed"
       exit 1
   else
       echo "You failed"
       exit 1
   fi
   ```
 - ![image](https://user-images.githubusercontent.com/67081225/224467186-8d7dcf9e-0259-410f-b2e1-e79b2fe6d7e2.png)
 - ![image](https://user-images.githubusercontent.com/67081225/224467197-f66c80d7-3220-488d-a95b-ade132368dad.png)
 - As you can see from the code and example repositories used with the grading script, `grade.sh`, our grading script only provides a pass or fail score based on the 1 test. For this Lab Report, I want to make the grading script more robust by providing numbers so that the student knows how many test they passed/failed and I want to write more tests in addition to the one provided in the starter code. 

After using ChatGPT for guidance on how to extract the number tests and the number of failed tests from the output of JUnit, I edited the code within `grade.sh` to produce the following:
 - ```
   CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

   rm -rf student-submission
   git clone $1 student-submission
   echo 'Finished cloning'

   cd student-submission

   if [[ -f ListExamples.java ]]
   then
       echo "ListExamples found"
   else
       echo "need file ListExamples.java"
       exit 1
   fi

   FILTER= $(grep -q "static List<String> filter(List<String> list, StringChecker sc)" ListExamples.java)          
   if [[ $FILTER -eq 0 ]]
   then
      cd ./
   else
      echo "filter method header is incorrect"
      exit 1
   fi
   
   MERGE= $(grep -q "static List<String> merge(List<String> list1, List<String> list2)" ListExamples.java)     
   if [[ $MERGE -eq 0 ]]
   then
      cd ./
   else
      echo "merge method header is incorrect"
      exit 1
   fi

   cp ../TestListExamples.java ./
   cp ../Server.java ./
   cp ../GradeServer.java ./
   mkdir lib
   cp ../lib/hamcrest-core-1.3.jar lib/
   cp ../lib/junit-4.13.2.jar lib/


   javac -cp $CPATH *.java
   if [[ -f ListExamples.class ]] && [[ -f TestListExamples.class ]]
   then
       echo "Compiled files"
   else
       echo "Files did not compile correctly"
       exit 1
   fi

   java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > results.txt
   NUMTESTS=$(grep -o 'Tests run: [0-9]*' results.txt | grep -o '[0-9]*')
   NUMFAILS=$(grep -o 'Failures: [0-9]*' results.txt | grep -o '[0-9]*')

   FULLPASS=$(grep 'OK ([0-9]*' results.txt | grep -o '[0-9]*')
   if [[ $FULLPASS -ne 0 ]]
   then
       echo "You Passed all ${FULLPASS} tests"
       exit 1
   else
       echo "You missed ${NUMFAILS} out of ${NUMTESTS} tests"
       exit 1
   fi
   ```
 - First off, to account for incorrect method headers in the student submissions, I check that the method headers for `filter` and `merge` are correctly written in `ListExamples.java` so that the autograder does not produce problems when trying to run methods.
 - Secondly, instead of storing values within text files like `success.txt` or `fails.txt`, I decided to use bash variables to store the contents of grep. To extract the number tests and failures from `results.txt`, I used the `grep -o` command which allows to only extract the given phrase of grep from the file. So for example, to get the number of tests I used the `NUMTESTS=$(grep -o 'Tests run: [0-9]*' results.txt | grep -o '[0-9]*')` where the first grep finds where in `results.txt` it can find the phrase `"Tests run: [0-9]"`. The `[0-9]*` is used to match zero or more occurances of any digit from 0 to 9. So when we use grep again after the `|`, we extract the actual number, and since the whole command is surrounded by `$()`, the output will be treated as a numerical value which will be stored in `NUMTESTS`. 
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
 - [https://github.com/ucsd-cse15l-f22/list-methods-lab3](https://github.com/ucsd-cse15l-f22/list-methods-lab3) 
   - ![image](https://user-images.githubusercontent.com/67081225/224512980-a80dd7aa-8db9-4153-88d7-a62c17c851aa.png)
   - ![image](https://user-images.githubusercontent.com/67081225/224513234-0b46be0e-cdd6-4029-a091-9958ef1d1895.png)
   - From the output of the autograder, we can see that the repository failed 3 or the 8 tests. By looking at `results.txt` within the `student-submission` directory we can see that the repository failed `testFilterFound`, `testMergeRightEnd`, and `testMergeEmptyLeft`.
   - For `testFilterFound`, the test failed because the order of the filtered list were in the wrong order. For the other two tests, the program timed out. By looking in the code of `ListExamples.java` in the student submission, we can see that the `filter` method always adds a string to the front of the list when it should always be to the back of the list. In the `merge` method we can see that the method will never end because 1) there is no check to see if the values from both lists are equal for the first while loop and 2) the while loop for when list2 is the only list with elements left does not increment the correct index.
 - [https://github.com/ucsd-cse15l-f22/list-methods-corrected](https://github.com/ucsd-cse15l-f22/list-methods-corrected)
   - ![image](https://user-images.githubusercontent.com/67081225/224513651-0bf7026c-c850-41a1-ab26-aec9c78405fc.png)
   - As expected, this repository passes all the tests from the autograder.
 - [https://github.com/ucsd-cse15l-f22/list-methods-compile-error](https://github.com/ucsd-cse15l-f22/list-methods-compile-error)
   - ![image](https://user-images.githubusercontent.com/67081225/224513735-964716af-71b9-4fd7-a1bc-1b71d5243cac.png)
   - For this repository, there is a compiler error due to a missing semicolon. So the autograder reports the error and states that files did not compile correctly, so the tests from JUnit do not run at all.
 - [https://github.com/ucsd-cse15l-f22/list-methods-signature](https://github.com/ucsd-cse15l-f22/list-methods-signature)
   - ![image](https://user-images.githubusercontent.com/67081225/224514908-169956bf-a350-40a8-b5b6-b47d8249ad40.png)
   - For this repository, the method header of `filter` has the parameters switched around. The autograder catches this and tells the student that their `filter` method header is incorrect.
 - [https://github.com/ucsd-cse15l-f22/list-methods-filename](https://github.com/ucsd-cse15l-f22/list-methods-filename)
   - ![image](https://user-images.githubusercontent.com/67081225/224515038-7a8036ac-14bd-49fa-806e-7a02c1e9e196.png)
   - For this repository, the name of the file that contains `ListExamples` is named incorrectly, so the autograder will catch this and say that `ListExamples.java` is needed to run the tests.
 - [https://github.com/ucsd-cse15l-f22/list-methods-nested](https://github.com/ucsd-cse15l-f22/list-methods-nested)
   - ![image](https://user-images.githubusercontent.com/67081225/224515141-a385c839-10be-4e50-9d85-96d670402c9f.png)
   - For this repository, the student's submission is nested within a different directory than we expect so the autograder is not able to find the files required to run the tests. So the autograder says that it needs `ListExamples.java`.

Now that we have run a few examples of repositories with our tests, the final thing we will do is make it so that the autograder can run on a server.
 - We run the server with the [https://github.com/ucsd-cse15l-f22/list-methods-corrected](https://github.com/ucsd-cse15l-f22/list-methods-corrected) repository
 - ![image](https://user-images.githubusercontent.com/67081225/224515717-25bb7cb1-61e9-4d9e-a6db-341d0136ec1c.png)
 
    



