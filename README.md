# GitHub Tutorial

_by Maie Sayed_

## Topics
---
##### Git vs. GitHub
Git: a *version control system* of repositories
 - version control system = a set of tools that helps manage changes to code over time
Github: a large repository where you are able to store code in cloud, collaborate with others, and easily track changes
Note: In order for Github to function it requires Git
The code written in Git is what Github stores in cloud
---
##### One-Time Setup
Part One: Making a Github Account
1.) Sign Up
2.) Username
 for HSTAT students use: Firstname_Lastname_Last4OSIS#
3.) Password
for HSTAT students use: your OSIS#
4.) Email Address
for HSTAT students use: your hstat/school email
5.) Password
      - for HSTAT students use: your OSIS#
6.) Verify your account
7.) Press the green button
create account
8.) Verify email address
9.) Fill in preferences
Part Two: Setting up your IDE
Congrats! You now have a Github Account but what good is a Github account if you can’t use it?
Make sure you set up your IDE (it's not as hard as you think!)

[Click here to learn how to set up your IDE!](https://github.com/hstatsep/ide50)

So you got to the SSH Key and don’t understand its importance huh?
Let me explain it then:
The SSH Key is:
“Secure Shell” Key
an efficient way to verify yourself that doesn’t ask you to enter your information (username and password) every time you log into and connect to Github (or any other *remote server/services*) (unlike using HTTP)
Could be used like a public key that gets shared with services like Github/ private key that stored only on your computer
The SSH command provides a secure encrypted connection between two hosts over an insecure network
When you set up your SSH, you'll generate an SSH key and add it to the ssh-agent and then add the key to your GitHub account. (directions on how to set up SSH Key is included in the link ;) )

Difference between SSH and Http:
when cloning: http will ask for your password every time you attempt to clone to verify that it is you
---
##### Repository Setup
Log into Git:
Create a directory to contain the project.
Go into the new directory.
Type git init.
Write some code.
Type in the command *git add* to add the files (see commands list below for more info.).
git add puts "people in the staging area" of the "code" you have written in it
Once you are done adding to it and are ready to commit, use *git commit -m "put a message here”*
The message should be formatted to be:
Short
Concise
In Present Tense
If you follow these conditions you will limit confusion if you end up collaborating with another person or if you want to go back to your code later on and fix a certain portion of your code where you committed
Git commit: takes a "snapshot" of the items in the staging area
Git commit keeps track of changes done to a code
Always make sure you do *git status*
The git status command shows you what you have in the working directory  what you have in the staging area.
It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git.
Status output does not show you any information regarding the committed project history, it just shows you what has been committed and what hasn’t been
Green = committed
Red = not yet committed
Git status is vital for making sure everything is functioning probably
If  you are
satisfied with your project and want to push the changes up from local to remote, where it can be safely stored AND
added the code in the staging area into the working directory AND
committed it into your *local* working directory THEN
YOU ARE READY TO PUSH -
- *git push* is the command you use when you are ready to push - your local commits onto the remote branch

In other words:
*git push* takes your commited files on (Git) and send it to the cloud on (Github)

In Github:
If you want to create a repository in Github
Go to the upper-right corner of any page
Click on the drop-down menu
Select “New Repository”
Name your repository
Add a description of your repository (you don’t have to)
Choose to make your repository either public or private
Select “Initialize this repository with a README”.
A README is a file place inside your directory that  _usually_ contains user manual information/ instructions (don’t worry about this)
Click “Create repository”

#####Rolling Back Changes

So say you accidentally edited, added, committed, and/or pushed some text and want to undo some/ all of the changes on your local.

This may seem complicated but it's not that hard!

Undo an edit
In order to undo an edit, you have 4 different options:
Type *git status* in your IDE Terminal
It will give you two commands
Type the command that will “discard changes in working directory”
Buy Why would you undo an edit?
   - If you are collaborating on a repo with someone else and accidently edit a file that you shouldn't have (because it’ll lead to a  merge conflict - and don’t want to deal with an issue like that). Youc na just use this command Instead of doing edit > undo a whole bunch of times, and it will reset that file (or multiple files) back to the last commit
- Now your file will return to the exact same way it was before you edited it

Undo an add
Say you added a file to the stage and you want to remove it
How do you know you added the file though? - *git status*  will show green silly!
In order to undo an add type what is on top of the green filename  in git status
To make sure you undid that add - type *git status* again; if done correctly the filename that used to be green will now be red
But why?
If you hypothetically edit two files and you accidentally do git add . Both files will be added to the stage. Say you only wanted one of the files, then you will use this process to remove the other one from stage

Undo a commit
Hypothetical situation: you committed the staging area by taking a snapshot but didn’t mean to
How do you undo your commit but leave your files and your staging area:
Type in your IDE Terminal : git reset --soft HEAD~1
Check that you have done it correctly by typing in the *git status* command
You should see a green file which takes you back to where you started (before you commited)
But why?
If you want to remove your commit message ONLY, this should be the command you use

Undo a commit and add
Hypothetical situation: You added new edits to the stage and committed it but later realized you had to add more things before you committed again. In other words ,you realized you want to DESTROY the commit
Just type in git reset HEAD~1
HEAD acts as a pointer to the most recent commit made
This commit message tells git to move one commit back, everything else stays the same
The commit you moved back form no longer exists- you have ANNIHILATED it, well done:)
But Why would I use this?
If you want to fix/add/edit anything in the screenshot before setting it in the staging area (through the commit command) but realized you committed to early- this command will destroy the latest commit so you could reset the staging area

Undo a commit AND add AND edit
Hypothetical situation:You want to destroy the most recent commit with everything it contains including the snapshots you added to the staging area and the edits you made to that as well. In other words you want to go back to your previous commit
The command you use is git reset --hard HEAD~1
This removes the latest commit with everything it includes (hence the --hard)
Use this command wisely
But why?
Since you used --hard with the command, you are unable to undo that if you want to go back
Rollbacking to a previous commit using another command is much safer because it isn’t permanent like this one\
This command removes the commit from existence, not just from Git, normally if you delete a commit it remains in Git for 90 days BUT if you use this command, the commit gets removed from history, from Git, FROM EXISTENCE, FROM… well you get the idea:)
Undo a push
Hypothetical situation: You decided to push the changes on Git to Github, but just realized that one of your  commits has a problem. You wnat to undo this and restore it.

-	The command git revert <SHA> create a new commit that will undo the SHA you are given
-  git revert will create a new commit that’s the opposite of the given SHA.
**each commit has it own unique SHA code. This could be accessed by doing `git log`**


- anything removed in the old commit will be added in the new commit
- anything added in the old commit will be removed in the new commit.
- git revert and SHA will essentially cancel each other out
-so you can now git push the new “inverse” commit to undo your mistaken commit.
But why use this?
This git command is the most simple way to “undo” anything in Git.
It doesn’t affect the history of your staging history, its just a command that cancels out another!
Say you start with 2, then add 2, then subtract 2, the original 2 didn’t change but the +2 and -2 canceled each other out!



#####Workflow and Commands

## Workflow & Commands
All commands below are essential and should be memorized for you own sake

`git init` - This command initializes the git in a directory
An initialized driectory is a repsoitory
YOU SHOULD NOT GIT INIT IN THE ROOT DIRECTORY
Initializing git in the root directory causes merge conflicts
The root direcotry is a rpository and you AHOULDN’T HAVE A REPO INSIDE A REPO

`rm -rf .git` - this will un-inititilaize git.
It is useful when you  initialize git in the wrong directory or in the root directory

`git add file.ext` - Adds changes/edits  for a *specific file* to the stage ready to commit

`git add .` - Adds change/edits s of **ALL** files to the stage

Adding them to the stage allows you to take a snapshot of the staging area, making the changes/edits permanent


`git status` - allows you to see the changes/edits you have added/not added to the stage
-if all edits/changes are added, then you are ready to commit.
- Green : added
- Red : not added yet

> `Modified: <file_name>` in red= not added to stage.
If yous ee the smae text in green then the file has been added to the satge and is ready to be commited

`git commit -m "short/specific message"`
- use this when there is no more edits to add and the file is ready to be commited/saved

* Your message *must be a short consise present command
       * This will allow you to look back and make changes, in the future, if needed whether it be during collaboration or by yourself

#####Comands used when comparing/seeing previous commits


`git diff` - shows the difference between the previous commit and your current edit

`git log` - shows you _all_ your previous commits

HYpothetical Situation: You are stuck in git log and want to git out( pun intented)
* On your keyboard, press *Control and Q* at the same time

#### Setting up Push and Pull
Loca Repo l- Git
Remote Repo - Github

When you have Git and Github, it is essential to know how to Push and Pull. But what are they exactly?

`git push` - Send commits from local repo (ide terminal) “up” to remote repo (github).
Once you refresh Github, it updates and you are able to see the changes caused by git push

>Wait - where will the pushed commits go?
You want to push your commits to a repo on Github, but if the repo doesn’t exist - the commits won’t go anywhere!
So how do you create it?- Simple:
Go to your IDE
 Initialize git in a directory
Now you have a repo
 Make a file called README.md
touch README.md
Add text to it, then git add. And commit

You are now done with creating your repo- now go to [github.com](https://github.com/) and sign in.
Press the _plus icon_ at the top right side of your screen
Press *create repository*
Enter the name of your repository from your IDE
    * This won’t work if the names aren’t the same
Go to the bottom of the page and turn "Initialize this repository with a README" **OFF**.
Press the green button _"Create Repository"_
    * This will direct you to another page
If done right, the code in your IDE repo will be the same as the code in yourGithub repo!
    * If it isn’t - make sure the SSH key is turned on
```
git remote add origin git@github.com:user_name/repository_name.git
git push -u origin master
```
Copy the code that looks like the one above ( on **YOUR** page) and paste it in the command line
 Press enter

Now that you have your local and remote synchronized if you:
 edit your README.md, add the edits, and commit them:  you can now use just the command `git push`

> The process done above was the synchronization of your ide and your repository in the cloud.	- 	If you didn't select SSH key, and selected HTTPS, you would have to be signing in every time you are going to push and pull which is inconvenient and tiring
The SSH Key tells your computer to recognize the fact that you linked your ide with your github- now it won’t ask for your information again.

**** More Commands
    * `git remote add origin URL` - sets up the connection between the remote and local repo
    * `git push -u origin master` -  creates a permanent bridge between the remote and the local. This allows to push without the extra origin master part that usually follows the command.

`git remote -v` - tells you where your commtis are being sent to and from.
This is similar to `git status`

> `git pull` only used when you're working in your remote (Github) and wanted to update your local.
Sends commits from remote repo (github) down to local repo (ide).
updates your remote.

#### Cloning Vs Forking

##### Clone:

> Hold up.

What if :  your local repo disappears due to a virus
What if : your repo got delet\ed on accident
What if :you want to work off someones project for yourself,

Now that you know how to backup your local, you should learn how to clone!


1. Go to [github.com](https://github.com/)
2. Go to the repository you'd like to copy
3. Press "Clone or Download"
    * Make sure it says "Clone with SSH"
        * If it says "Clone with HTTPS" click "Use SSH"
4. Copy the URL
5. Go to your IDE and make sure you are in the directory where you want this repo to go
6. Type `git clone` and paste the URL after it
7. Press ENTER
    * If you are going to work in the repo make sure to `cd` into it.

`git clone` - Allows you to copy a remote repo into your ide.

> Cons of `git clone`
you can not push your local commits to the remote repo
But why?
 When you clone you have a local copy of **THEIR** remote repo.
 You DON’T have permission to push to their remote.

In this case, you’ll need to knwo how to fork

##### Collaboration

**Forking**

> Forking on the other hand, give you a **remote copy** of *THEIR* **remote repo**.
Forking gives you the ability to :
clone your remote to your local machine.
 collaborate with others
work on the local repository and then push it  to the remote repository
suggest changes in the remote repo (pull requests- down below)


In order to fork you need to know how to clone.
Steps to effectively Fork:

1. Go to [github.com](https://github.com/)
2. Go to a repository you'd like to fork
3. Press the fork button located at the top right of the screen.
4. Wait for it to load then click on "Clone or Download"
    * Make sure it says "Clone with SSH"
        * If it says "Clone with HTTPS" click "Use SSH"
4. Copy the URL
5. Go to your ide and make sure you are in the directory where you want this repo to go
6. Type `git clone` and paste the URL after it
7. Press ENTER


“What if I wanted to learn how to suggest changes to the owner of the original remote repo?”
Great question- the answer to that is Pull Requests!

#####** How to send and accept Pull Requests**


1. Follow the steps on how to fork
2. Make a change in the file of the local repo that was just formed by forking and cloning.
3. After the change/edit
    * `git add`
    * `git commit -m "specific/short change`
    * `git push`
        * *** Step 3 steps are important overall, they summarized as _The Workflow Process_ ***

> Now that you forked and cloned the repositories at the same time, all you have to do now is set the location of where you're going to push.

6. Go to the owners version of the repository
7. Press _"New pull request"_
    * Github is smart enough to compare their remote repo with your remote repo
8. Press _"Create pull request"_
9. Write a comment telling them about your suggested revisions and push your repo.
10. Press _"create pull request"_

> “Why did their repo not change?”
You're suggesting a change. Once you send a pull request they will get notified through their email and see your suggested changes. Ultimatley they get to decide whether or not they accept your Pull Request- Welcome to the Real World!

“What if I am the owner and I want to accept/merge the pull request?”

1. Go to your remote repository that received a pull request
    * You can quickly access this by going to the email you got with the pull request and click the first link given
2. Press on “pull requests”
    * Located in between _"Actions"_ and _"Issues"_
3. Open the sent pull request
4. If you chose to accept the changes- press "Merge pull request"
5. Press _"Confirm Merge"_
6. Check the remote repo and make sure it went through

 > “It only appears in my remote and not my local. Did I do something wrong?”
Of course not! You will have to use `git pull` to pull the repo from your remote to your local

7. Go to your local repo
8. In your command line type `git pull`
    * Your local repo will instantly updateby pulling information from your remote repo

_And that’s all folks!_
---









