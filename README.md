# GitHub Tutorial

_by <Maie Sayed>_

---
## Git vs. GitHub
git: a version control system* of repositorires
github: is a large repository where you are able to store code in cloud, collaborate with others, and easily track changes, requires git in order to work
version control system = a set of tools that helps manage changes to code over time
version control software = keeps track of every modification doen to a code over time (in a database)
---
## Initial Setup
one-time setup// making a github account
steps towards making a account
1.) sign up
2.) Username
- if you are an hstat student use Firstname_Lastname_Last4OSIS#
3.) Password
- if you have an hstat student use the osis number
4.) Email address
- use your hstat/school email
5.) Password
- could be your osis number
6.) Verify your account
7.) press green button
- create account
8.) Verify email address
9.) Fill in preferences

[Click here to learn how to set up your IDE](https://github.com/hstatsep/ide50)

SSH Key:
Alternative way to identify yourself that does not require you to enter your username and password every time
Could be used like a public key that gets shared with services like Github/ private key that stored only on your computer
ssh command provides a secure encrypted connection between two hosts over an insecure network
SSH (Secure Shell) is used for managing networks, operating systems, and configurations.
Clone ssh
Not http
Use SSH when cloning, http will ask for your password every time you try to clone
---
## Repository Setup
In Git
Create a directory to contain the project.
Go into the new directory.
Type git init.
Write some code.
Type git add to add the files (see the typical use page).
git add puts "people in the staging area" of the "code" you ahev written in it
once you are done adding it and are ready to commit, use git commit -m" put a message here".
Git commit takes a "snapshot" of the items in the staging area
Git commit keeps track of changes
Once you are satisfied with your project and want to push the changes up from local to remote, where it can be safely stored, push it
- for pushing, use the command git push

In Github
In the upper-right corner of any page, use the drop-down menu, and select New repository
name your repository
Add a description of your repository // optional
Choose to make the repository either public or private. ...
Select Initialize this repository with a README.
Click Create repository.


---
## Workflow & Commands

pwd print working directory
ls list
cd change directory
mkdir make directory
rmdir remove directory
touch make a file
rm remove
rm -rf force remove
mv (to rename)
mv (to move)
c9 file (or c9 open file)
git init initialize the repository
rm -rf .git uninitialize the repo
git add . add unknown files
git commit -m "message" commit all changes mad ein your workspace
git remote add origin URL
git push -u origin master
git push
git diff
git log
q (while in git log)
git checkout -- file
git reset HEAD file
git remote -v

---
## Rolling Back Changes