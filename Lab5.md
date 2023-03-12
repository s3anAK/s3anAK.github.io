# Lab Report #5
For this lab report, I chose to redo the week #7 lab by creating a bash script that would execute the commands for me instead of having to do it manually. It was a good way to combine the skills that I have learned during this quarter into something practical.
## Implementation
Since I had to be inside of `ieng6` to start running the commands, I didn't include the `ssh` command in my script. Therefore, I still had to run `ssh cs15lwi23amc@ieng6.ucsd.edu` before I started. Once I was in `ieng6`, I created the file `lab7quick.sh` that does all the commands for me. It contained this code:
```
git clone git@github.com:s3anAK/lab7Fork.git
cd lab7Fork
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
sed -i '43s/index1/index2/' ListExamples.java
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
git add ListExamples.java
git commit -m "fixed error"
git push
```
Mostly, it was just a matter of copy and pasting all the commands that I ran into one script, but there were a couple things I had to work on. Some difficulties/new things I encountered while making this were:

 - I initially didn't know how to edit a file without manually going in and changing it myself, but I did some googling and found the `sed` command was very useful. I had another minor roadblock when I realized that the text I wanted to change ,`index1`, appeared many times so I couldn't just match it outright. However, I got past this with some more googling which told me that I could use `43s` to only match things on the 43rd line, which was the line that I wanted to change. I tested this command a couple times on its own to make sure it worked before putting it in my script.
 - I initially had `set -e` as the first line in the script because I didn't want bash doing anything funky with trying to commit the changes if they were not the right ones. However, I quickly realized that this didn't work because the Junit tests throw an error when one of them fails and then my program would just stop because of `set -e`. I took it out and was just more careful to not make mistakes after that.
 - When I initially created `lab7quick.sh`, I could not run it because I had not added the executable permission. I was confused for a bit, but thankfully I remembered back to when I created a project last summer that I could add the executable permission by `chmod +x lab7quick.sh`. After that, I was able to run it just fine.
 - It's important that I had my ssh permissions set up for my github account otherwise I would have had to input my username and password when I wanted to clone or push. I'm not sure how I would done that from a bash script, though there is probably a way.
## Output
After making sure everything worked, the total time to do all the steps was probably around 3 seconds, much faster than my fasted attempt at the lab manually. This was the output that I got from running `lab7quick.sh`:
### Screenshot #1
![ss1](https://user-images.githubusercontent.com/56090826/224565254-584d01a5-618d-4740-a6ce-75e63b917dab.png)
### Screenshot #2
![ss2](https://user-images.githubusercontent.com/56090826/224565259-85a680bf-374f-4443-bf8a-ce9213b78f9e.png)
### GitHub Account Showing the Commit
![commit](https://user-images.githubusercontent.com/56090826/224565263-9f901a0c-e18c-4fb3-a3ae-e3accf8c9ffc.png)
