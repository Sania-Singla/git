## git notes

# ' ~ ' represents that we are in the root directory of the system
# git - VCS (version control system) : an app installed on device that keep tracks of the changes so we install gitbash for windows
# Github is a website where we can reflect the changes and push the code and colaborate 

## basic commands:
*git --version 
*ls - list all items 
*clear - clear screen
*pwd - to get the present working directory 

# first step is to configure git so that by which account we are going to be making changes (local&global)
since we only have one git account so will use global and then all teh changes will be from that account no matter where we change
### SYNTAX: 
    git config --global user.name "name" (instrings)
    git config --global user.email "email" (instrings)
    git config --list (will show what we did in the config)

## COMMANDS:
⭐CLONE a repo : this will copy any repo into our device
### SYNTAX: 
    git clone <link of the project>
we can get the link of the repo from the code option and then copy the https link 
**there is always some hidden files  (.git) and folders in all folders which are git repos so get a list of them run ls -a (use cmd not powershell ok!!)

⭐STATUS: tell about the status of the code
### SYNTAX: 
    git status
there are four statuses:
*untracked: files which are not tracked by git (every new file is untracked until we commit)
*modified (M): when we make any change
*unmodified (U): when no changes are made
*staged: file is ready to be commited (because before commiting we have to add the changes(makes the files staged))

⭐ADD:adds new or changed files in the working directory to the git staging area
### SYNTAX: 
    git add <filename>
git status . (for all the changes to be added from all files in one go)

⭐COMMIT: it is the record of the changes
### SYNTAX: 
    git commit -m "some message" (but they wont reflect on github yet)

⭐PUSH: upload the changes on github now (remote repo (github repos) , local repo (our device or PC ) )
### SYNTAX: 
    git push origin main 
*origin means push on the cloned repo out of all the remote repos (the target repo basically which is named as origin)
and there can be multiple branched in a repo so currently we are pushing on to the main branch

# to create a new git repo ( which is what we generally do because we first creat a local folder rather than a repo )
⭐GIT INIT: will initalize the current directory as git repo, but still we will have to create a repo manually on github ***without a readme*** because otherwise we will have to clone that on to the device

ex: add a new remote repo and name it origin
### SYNTAX: 
    git remote add origin <link>
    git remote -v ( to verify remote )
    git branch (to check branch )
    git branch -M <new name> ( to rename a branch )
    git push origin main 
    short form : git push -u origin main ( created an upstream: so that everytime we dont have to write this we can now just write git push )

⭐BRANCH COMMANDS:so when multiple persons are working on a same project so we create multiple copies of the repo and then merge them at end
### SYNTAX:
   git branch (to check current branch)
   git branch -M <new name> ( to rename a branch )
   git checkout <branch name> (to navigate to some other branch)
   git checkout -b <branch name> (to create a new branch & will navigate also)
   git branch -d <branch name> (to delete a branch) ( cant delete current branch )
****then if we make any changes they will be only present in that branch and after that when we push we need to use => git push origin <branch name>

⭐merging branches:
1) using cmd:
### SYNTAX:
    git diff <branch name> (to compare commits,branches,files & more) ( will compare the current branch to this branch which we entered in the command)
    git merge <branch name> (to merge 2 branches)

2) using Pull Request on github
so we pull request on github and then to reflect that merge on local folder we use pull command: 
### SYNTAX:
    git pull origin <branch name to pull(feature) into the current branch(main)>

*** resolving merge conflicts : when both branches have some changes to same lines so which ones to keep ?? so we will manually delete the one we dont want

⭐git log : to check all the commits 
⭐UNDOING CHANGES: there are three scenarios

1) staged changes: 
### SYNTAX:
    git reset <filename>
    git reset (will reset all files after the latest commit)

2) commited changes: (for one commit)
### SYNTAX:
    git reset HEAD~1 (will move the head(last commit) backwards by 1 step)

3) commited changes: (for multiple commits)
### SYNTAX:
    git reset <commit hash code>
    git reset --hard <hash code> (will undo the changes on vs code also)

⭐can use 'q' for quitting 