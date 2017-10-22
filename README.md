# GitHub Tutorial

_by Arieta Haskaj_

---
## Git vs. GitHub
#### Git runs in the command line.
* It manages your code through **_version control_**. Think of each version of your code as a checkpoint  
  in Mario Kart.
    * Each time you commit changes in your code, it is like passing a "checkpoint"
    * You can revert back to that version later
* Git lives in your **_local directory_**
    * This is where you are actually coding and can be directly on your computer or in a program  
      called cloud9
* **_Cloud9_** is a place where you can code in a language of your choice and your projects will live  
  in a cloud  
    * We consider this our local directory
* Git does **NOT** need github to run

#### Github is a website where code is stored. 
* Code is stored in the cloud
* It visually tracks changes
* Code is sent from our local machine to github
* Github **NEEDS** git to run


---
## Initial Setup
#### Creating a github account and connecting it to cloud9
1. Go to [github](www.github.com).
2. You should see a screen asking you to create an account. If not, click on "Sign up"  
   in the top-right corner.
3. Type in a username, email address, and password then click "Create an account".
4. It will bring you to a welcome page. Choose the option that says "Unlimited public repositories for free"  
   and click "Continue". You have now created an account.
#### Connecting your github to cloud9  
1. Go to [cloud9](www.c9.io).
2. Click on the image of the github "octocat" and sign in with your github account.
3. Once you sign in you should be taken to your dashboard where you can see your workspaces.  
   If not, press on "DASHBOARD" at the top of the screen.
4. Press the gear icon in the top-right corner of the screen.
5. On the left side, press "SSH Keys".
6. Copy the second SSH key.
7. On github, press on your profile picture and click "Settings" on the dropdown.
8. Press "SSH and GPG keys" on the left side and then the green button that says "New SSH key".
9. Paste the SSH key under "key" and type "cloud9" as the title.  
10. Click "Add SSH key".  
11. To make sure it is working, go back to your terminal and type `ssh -T git@github.com`. You  
    should see a message that says "Hi <your username>! You've successfully authenticated, but  
    GitHub does not provide shell access."
**_You have now finished setting yourself up to use cloud9 and github!_**


---
## Repository Setup
#### Creating and initializing a new repository in cloud9
1. On cloud9, make sure you have a terminal open. If not, go to "Window" on the top and click  
   "New Terminal". In the terminal you should see `yourusername:~/workspace`.
2. Type `mkdir yourdirectoryname`. This creates a new directory in cloud9.
3. Go into this directory by typing `cd yourdirectoryname`. You should see `yourusername:~/workspace/yourdirectoryname`.
4. To initialize this directory, or get it ready coding, type `git init`. You should see  
   `yourusername:~/workspace/yourdirectoryname (master)`. If you accidentally initialized the wrong directory, 
   type `rm -rf .git`. This will unitialize it and you can then repeat steps 3+4 to initialize it correctly.  
**_You have now created your first repository and prepared it for coding._**
#### How to add and commit
1. Now that you have created a repository in cloud9, you can begin coding. To create a new file, type  
   `touch yourfilename`.  Type whatever you want in this file.
2. To see if you have made changes, type `git status`. In red, you should see `modified: yourfilename`.  
   This means there are changes that have not been added or committed.
3. To add everything to the staging area, which prepares it for being committed, type `git add .` When  
   you type `git status` again, you should now see `modified: yourfilename` in green.
4. Now type `git commit -m "your commit message"`. This takes a "snapshot" of the files on the stage.  
   Your message should be relevant and written in the present tense.  
**_You have now added and committed for the first time._**
#### Creating a remote repository
1. Go to [github](www.github.com).
2. Click on the "+" sign on the top-right corner then click "New repository". You will be brought to a  
   page entitled "Create a new repository".
3. Under "Repository name", type the name _exactly_ the same as your repository in cloud9. Then click  
   the green button called "Create repository".
#### Linking your remote repository to your local repository on cloud9
1. Go to your project page on github.
2. 


---
## Workflow & Commands
* Adding, committing, and pushing should be done often enough to ensure that you work is being saved and so 
  that you can rollback to a working version of your code.
* You should also do `git status` often, every other command is best, to be sure that you are adding, committing,  
  and pushing correctly and to show you that everything is on track.


---
## Rolling Back Changes
* **To undo an edit,** you use the command `git checkout --filename`. This will undo any changes you have made 
  since your last commit.
* **To undo something that was added,** you use the command `git reset HEAD filename`. This will take everything 
  off of the staging area.
* **To undo something that was committed,** you use the command `git reset --soft HEAD-1`. This removes the "snapshot" 
  taken and brings it back to the staging area.
* **To undo a commit and add,** you use the command `git reset HEAD-1`. This removes the "snapshot" taken and 
  takes it off of the stage.
* **To undo a commit, add, and edit,** you use the command `git reset --hard HEAD-1`. This completely rollsback to 
  your last committed version of the code. 
* **To undo a pushed commit:**
  1. In the terminal in cloud9, do `git log` to get the commit SHA. Press **q** to quit.
  2. Do `git revert a b`, with a being the most recent commit and b being the commit before that.
     * This will revert back to the commit you put the SHA key for.