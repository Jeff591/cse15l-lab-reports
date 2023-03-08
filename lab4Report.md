# CSE 15L - Lab Report 4
## Steps for the Done Quick Competition
1. Setup Delete any existing forks of the repository you have on your account
    - ![image](https://user-images.githubusercontent.com/67081225/221300608-2d52bdb8-f5c6-412a-9608-abd789c4b185.png)
    - Go to the settings of the forked lab7 repository and scroll to the bottom to find the "Delete this repository" button.
2. Setup Fork the repository
    - ![image](https://user-images.githubusercontent.com/67081225/221301311-ab5d61ac-8939-4cf5-a217-e127961d7e01.png)
    - Go to [https://github.com/ucsd-cse15l-w23/lab7](https://github.com/ucsd-cse15l-w23/lab7) and then press the Fork button in the top right to then create a fork of the repository 
3. The real deal Start the timer!
    - ![image](https://user-images.githubusercontent.com/67081225/221301853-f808ac94-1320-4637-a9d3-c00ab6d9748d.png)
    - Go to Google and search up timer and use the stopwatch setting to time yourself
4. Log into ieng6
    - ![image](https://user-images.githubusercontent.com/67081225/221303388-86119fa9-c10b-42a9-b062-dbab2767723c.png)
    - Keys Pressed: `<up><enter>`
    - The `ssh` command was 1 up in the search history and I pressed enter to run the command. The reason why we do not have to type in a password for logging in is because in lab of week 7 we generated an SSH key on our local terminal and then copied the path of the key into the `.ssh` directory where we store `authorized_keys`. Then on our local computer we run the `scp <path to your public SSH key> cs15lwi23atn@ieng6.ucsd.edu:~/.ssh/authorized_keys` and enter our password when prompted, which then allows us to log in to the remote account from the current local machine without having to retype the password.
5. Clone your fork of the repository from your Github account
    - ![image](https://user-images.githubusercontent.com/67081225/221303937-8f06ddaa-a47e-45a8-ba6b-af73a388446b.png)
    - Keys Pressed: `<ctrl+R><g><enter>`
    - To find the `git clone` command, I used `<ctrl+R>` to open up reverse-i-search. Then I typed in `<g>` and the first command that showed up was `git clone git@github.com:Jeff591/lab7.git`. Once the command was pulled up, I pressed enter to run the command and clone the repository. 
6. Run the tests, demonstrating that they fail
    - ![image](https://user-images.githubusercontent.com/67081225/223595756-18b96724-466e-4c88-9ad9-2e64377b4a2b.png)
    - ![image](https://user-images.githubusercontent.com/67081225/223595820-f3a869d5-0828-4af8-ba38-d670ca2f7008.png)
    - Keys Pressed: `<c><d><l><a><b><7><enter>`, `<ctrl+R><j><a><v><a><c><enter>`, `<h><i><s><t><o><r><y><space><|><space><g><r><e><p><space><"><j><a><v><a><space><-><c><p><"><ctrl+C><ctrl+V><enter>`
    - Since `cd lab7` is a short command, I just typed the command out and hit enter. For the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`, I used `<ctrl+R>` and looked for `javac` which brought up the command and allowed me to run it with enter. For the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command, I used `history | grep "java -cp"` to search up the command. Once I found it in history, I copied and pasted the command using `<ctrl+C><ctrl+V>` and pressed enter to run it. These commands compiled the necessary files and ran them to show that the tests would fail.
7. Edit the code file to fix the failing test
    - ![image](https://user-images.githubusercontent.com/67081225/221308431-6a34cc22-a433-44ee-b7e4-b95bb9ad75c7.png)
    - Keys Pressed: `<up><up><up><up><up><up><up><up><up><enter>`, `<ctrl+W><<><space><0><enter><right><=><ctrl+W><r><e><t><u><r><n><enter><up><up><right><right><right><right><right><right><right><right><backspace><2><ctrl+O><crtl+X>`
    - It took 9 up arrow key presses to access to the `nano ListExamples.java` command. Once in the file, I used `<ctrl+W>` and searched for `< 0` then appended an `=` to the end of the `<`. Then I used `<ctrl+W>` and searched for `return` and then navigated up and to the right to then change `index1` to `index2`. Once the edits were done, I saved using `<ctrl+O>` and exited using `<ctrl+X>`. By making these edits, the tests should not fail.
8. Run the tests, demonstrating that they now succeed
    - ![image](https://user-images.githubusercontent.com/67081225/223596770-c376d611-c63b-4956-a284-5b0951ed6f61.png)
    - Keys Pressed: `<up><up><up><up><up><enter>`, `<up><up><up><up><up><enter>`
    - It took 5 up arrow presses to access the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command, and it took another 5 up arrow presses to access the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` in search history. These two commands compile the files again and run the tests to show that that program passes all the written tests.
9. Commit and push the resulting change to your Github account
    - ![image](https://user-images.githubusercontent.com/67081225/223597154-a842182d-46b3-477f-a25c-2d115824b97a.png)
    - Keys Pressed: `<ctrl+R><g><i><t><space><a><enter>`, `<ctrl+R><g><i><t><space><c><enter>`, `<ctrl+R><g><i><t><space><p><enter>`
    - To get the command `git add ListExamples.java`, I used `<ctrl+R>` and typed `git a` which brought up the most recent git add command. In a similar way I used `<ctrl+R>` to get the commands `git commit -m "Fixed"` and `git push`. After getting each of the commands I hit enter to run them. These commands allow the changes made on our remote account to show up on our GitHub repository.

## Results
![image](https://user-images.githubusercontent.com/67081225/223599251-3685148b-a464-40b3-9198-06e6a0c6ef72.png)
 
