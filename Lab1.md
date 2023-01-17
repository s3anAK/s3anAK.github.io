# Logging into your CSE 15L account
This tutorial will cover how to use ssh to log into your course-specific account on `ieng6`. It will be divided up into 3 steps:

 -  Installing VScode
-   Remotely Connecting
-   Trying Some Commands
## Installing VScode
First, we are going to install VScode. The overall installation instructions can be found [here](https://code.visualstudio.com/docs), and Windows-specific instructions (since I use Windows), can be found [here.](https://code.visualstudio.com/docs/setup/windows) All you need to do is download the Windows installer and run it. If everything is set up properly, you should be able to open VScode and have it look something like the screenshot below. I already had VScode installed, so I personally skipped this step.

![VScode sample](https://user-images.githubusercontent.com/56090826/211933477-f166a89b-032b-49c6-b7ad-6942c370950c.png)
## Remotely Connecting
Now we are going to remotely connect to our account through the terminal in VScode. To do this, you first need to install Git Bash which is a Bash emulator that can run Git. The instructions to do that can be found [here](https://gitforwindows.org/). Once you have Git bash installed, you need to open a Git Bash terminal in VScode, for which instructions can be found [here](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994). I already had Git Bash installed, so I personally skipped this step.

We are ready to start running commands in the terminal now. To use ssh to log in to your account, run the command  `ssh USERNAME@ieng6.ucsd.edu` where `USERNAME` is replaced by your CSE15L username. The first time you run this command, you may be prompted to answer a question with yes/no. Just type in `yes` and hit enter. Then you will be prompted to enter your password. When typing it in, your password will not show up, but rest assured that as long as you are type it correctly, it will work properly. Assuming you type in your password properly, you are now logged in! When you log in the first time, there will be some extra text, but it should look something like below. I followed this part of the instructions exactly.

![Screenshot_20230111_014026](https://user-images.githubusercontent.com/56090826/211941573-33542327-a8e0-4b63-a6b5-2dc877ab31e1.png)
## Running Some Commands
Now we are going to run some commands to get used to the bash terminal. Things to try include `cd`, `ls`,`cp`,`cat`, `touch`, or `pwd`. You may or may not run these commands properly, but they should all at least be seen as valid commands. An example of what some of these commands might look like is below.

![Screenshot_20230111_014449](https://user-images.githubusercontent.com/56090826/211941696-cecfb634-30e6-4d75-b812-5642334f59e4.png)

