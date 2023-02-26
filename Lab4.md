# Lab Report #4
## Step #4
![ssh](https://user-images.githubusercontent.com/56090826/221434070-4a8c2d97-de69-4ce6-adc9-7c460d05b92f.png)
*Keys pressed:* `<right click on trackpad><enter>`

For this step, I put the correct command in my clipboard to start, so all I had to do was right-click on my trackpad to paste the command in. Then I hit enter to run it.
## Step #5
![clone](https://user-images.githubusercontent.com/56090826/221434073-378d312b-1087-4d8e-89f8-44298c902bf7.png)
*Keys pressed:* `<navigate to the github repo on chrome> <click Code -> SSH> <click copy to clipboard button> <navigate to terminal> <typing> git clone <right click on the trackpad> <enter>`

For this step, I went to GitHub on chrome, copied the link to SSH the repo, then navigated back to the terminal. From there I typed in the "git clone" command manually since it was so quick. Then I copied in the SSH URL and hit enter to clone the repo onto my remote machine.
## Step #6
![testsFail](https://user-images.githubusercontent.com/56090826/221434071-7e47ad02-d971-45a9-abce-cae1951021c5.png)
*Keys pressed:* `<typing> cd la <tab> <enter> <navigate to week 3 15L page> <copy javac command for mac tests> <navigate to terminal> <right click on trackpack> <enter> <navigate to week 3 15L page> <copy java command for mac tests> <navigate to terminal> <right click on trackpack> <right arrow to end of the line> <hold delete key until "ArrayTests is gone"> <typing> Li <tab> <typing> T <tab> <enter>`

For this step, I moved into the repository that I just cloned. Then I copy-and-pasted the commands for running the tests from the course website. I had to change the end of the second command to `ListExamplesTests` instead of `ArrayTests` before I was able to run the command.
## Step #7
**Command Line:**
![editTests1](https://user-images.githubusercontent.com/56090826/221434224-89edaebb-0d5e-4bb3-b97a-cc94b2e3732d.png)

**Nano editor:**
![editTests2](https://user-images.githubusercontent.com/56090826/221434223-abf81a4e-660b-4aa7-9616-6f671274e9a0.png)
*Keys pressed:* `<typing> nano L <tab> <typing> .java <enter> <hold down arrow until line with the error is reached> <right arrow x12> <delete x1> <typing> 2 <control + X> <typing> y <enter>`

For this step, I used nano to edit the file. I first tried to use `<control + W>` to skip right to the line I wanted, but since there were several occurrences of it, I just used the down arrow which was quite fast. Then I deleted the character that was causing the error (the 1 in `index1`) and replaced it with a `2`. Then I quit nano using the `<control + X>` command and saved the file.
## Step #8
![testsPass](https://user-images.githubusercontent.com/56090826/221434072-0ddc8170-1497-4d39-ac7b-6780009a8397.png)
*Keys pressed:* `<up> <up> <up> <up> <up> <up> <enter> <up> <up> <up> <up> <up> <up> <enter>`
 
 For this step, I used the up arrow 6 times to access each command (`javac` and `java`) to run the tests again and show that they pass now after the changes that were made in Step #7.
## Step #9
![git](https://user-images.githubusercontent.com/56090826/221434069-99554092-472c-4faf-984c-e8efb707bcf6.png)
*Keys pressed:* `<typing> git add L <tab> <typing> .j <tab> <enter> <typing> git commit -m "fixed error" <enter> <typing> git push <enter>`
 
For this step, I staged the file that I changed, committed it, and pushed those changes to GitHub. There no opportunities for major time-savings during this step, so it was mainly just using tab to autocomplete the names of files.
