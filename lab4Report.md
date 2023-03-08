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
    - Keys Pressed: `<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>`
    - The  `git clone` command was 15 up in the search history so I used the up arrow to access it and pressed enter afterwards to run it.
6. Run the tests, demonstrating that they fail
    - ![image](https://user-images.githubusercontent.com/67081225/221304636-3e9fa966-11e5-462a-a964-6cf628915a42.png)
    - Keys Pressed: `<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>`, `<up><up><up><enter>`, `<up><up><up><up><up><up><up><up><up><up><up><up><up><enter>`
    - It took 16 up arrow presses to access the `cd lab7` command in the search history, it took another 3 up arrow presses to access the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamples.java ListExamplesTests.java` command, and it took another 13 up arrow presses to access the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command. 
7. Edit the code file to fix the failing test
    - ![image](https://user-images.githubusercontent.com/67081225/221308431-6a34cc22-a433-44ee-b7e4-b95bb9ad75c7.png)
    - Keys Pressed: `<up><up><up><up><up><up><up><up><up><enter>`, `<ctrl+W><<>< ><0><enter><right><=><ctrl+W><r><e><t><u><r><n><enter><up><up><right><right><right><right><right><right><right><right><backspace><2><ctrl+O><crtl+X>`
    - It took 9 up arrow key presses to access to the `nano ListExamples.java` command. Once in the file, I used `<ctrl+W>` and searched for `< 0` then appended an `=` to the end of the `<`. Then I used `<ctrl+W>` and searched for `return` and then navigated up and to the right to then change `index1` to `index2`. Once the edits were done, I saved using `<ctrl+O>` and exited using `<ctrl+X>`.
8. Run the tests, demonstrating that they now succeed
    - ![image](https://user-images.githubusercontent.com/67081225/221323883-f99b47a9-6c2f-4992-9e00-bf2a78e4118d.png)
    - Keys Pressed: `<up><up><up><up><up><enter>`, `<up><up><up><up><up><enter>`
    - It took 5 up arrow presses to access the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamples.java ListExamplesTests.java` command, and it took another 5 up arrow presses to access the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar
9. Commit and push the resulting change to your Github account
    - ![image](https://user-images.githubusercontent.com/67081225/221324358-3c3d8624-f1ba-4d14-b2bb-a6f185b2a24a.png)
    - Keys Pressed: `<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>`, `<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>`, `<up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><up><enter>`
    - It took 17 up presses to get to the `git add ListExamples.java` command, 17 more up presses to get to the `git commit -m "Fiexed"` command, and a final 17 more up presses to get to the `git push` command in the search history.
