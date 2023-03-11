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


