# Week 1 Lab Report
This lab report will detail how to log into a course-specific account on ieng6.
## Part 1: Finding Your CSE 15L (or Any Course) Account
1. To find your user name for the course you want, go to the following [link.](https://sdacs.ucsd.edu/~icc/index.php)
2. Once there you will want to enter your student username and your student ID to search for your account names. Find the account name with your corresponding course name and click on the button associated. ![image](https://user-images.githubusercontent.com/67081225/212378454-c522c230-83bb-40a1-97b4-751310af8e99.png)![image](https://user-images.githubusercontent.com/67081225/212378935-07287926-30c6-4454-9d7a-23ab72d14f02.png)
3. If you have not set your password or want to change it, click the link that says "change your password".
4. Once you enter your username and student ID, you will be prompted to change your password by entering your current password and then entering the new password. Make sure to click No on where it says "Change MyTritonLink password?" if you do not want to change that one. Click Yes on where it says "Change course-specific account passwords?" then hit enter.
5. You will likely have to wait 15 minutes for your password changes to be in effect.

## Part 2: Installing Visual Studio Code
1. If you do not already have Visual Studio Code installed on your computer, go to https://code.visualstudio.com/ to get the instructions on how to install.
2. Once at the site, choose the stable build for the operating system your device is using by clicking on the drop down button. ![image](https://user-images.githubusercontent.com/67081225/212381197-6c6dbd81-a5da-4f77-88a7-e98cb0b5282f.png)
3. Once you get the installer, follow the instructions prompted and choose all the default settings. After installation process, open up VS Code and you will get a window like this.                                                               ![image](https://user-images.githubusercontent.com/67081225/212381592-6d78b56f-bcc9-4e22-81bd-1eab42b5ea3b.png)

## Part 3: Remotely Connecting and Git
1. If you do not have git already installed click the following [link](https://gitforwindows.org/) to be taken to the following page. Hit download and follow the instructions.![image](https://user-images.githubusercontent.com/67081225/212382005-fad827ca-0f77-4e49-98c4-8a6a9ed7dd52.png)
2. Open up VS Code and create a terminal by either going to the top of the window and hitting "New Terminal" under the Terminal tab or hit Ctrl+Shift+`.![image](https://user-images.githubusercontent.com/67081225/212393373-b9af5223-cc9c-4064-a4e7-6ae8907c288d.png)
3. Run `ssh cs15lwi23xx@ieng6.ucsd.edu` but replace the part infront of @ieng6 with correct account name you found in part 1. 
4. After running the commad, you may get a screen which asks `Are you sure you want to continue connecting (yes/no/[fingerprint])?`. Type in yes if you are logging in for the first time. 
5. Enter your password that you set up in part 1 and you should then be on a similar screen to this. ![image](https://user-images.githubusercontent.com/67081225/212392663-16832bc4-9f7c-4784-ab6a-18f37b028959.png)


## Part 4: Try Running Some Commands
1. From here, you will be able to run commands like the following:
* `cd ~` Go back to the home directory
* `cd <directory-name>` Go to the specified directory
* `ls <directory-name>` Shows the contents of the specified directory
* `cp <path> <directory>` Copys the file or directory from the given path to the specified directory
* `cat <path>` Prints out whatever is in the file determined by the path

2. Here is an example of running some of the commands: ![image](https://user-images.githubusercontent.com/67081225/212390979-4cbf9261-84d7-4d73-a408-67d0aafe601c.png)  

* In this example, I ran the `ls` command to show the contents of the current home directory. Then I ran the `cat hello.txt` command to print out the contents of hello.txt to the terminal. We could also get the same reuslt by doing `cat /home/linux/ieng6/cs15lwi23/public/hello.txt` which is where I originally copied the hello.txt from.

