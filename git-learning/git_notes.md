# Git Commands & Notes
Personal notes on Git commands, taken while learning version control.  
*This file will keep growing as I learn more.*

## git --version
Shows whether Git is installed and which version you have.  
(The first command to check when setting up Git)

## git config --global user.name
Sets the username that will appear in your Git commits.

## git config --global user.email
Sets the email address that will appear in your Git commits.

## git config --list
Lists Git settings.

## git init
Turns the folder you're in into a Git repository.
The first command when starting a new project.  
(Git starts tracking the changes made in this folder)

## git status
Checks the current state of your files.  
(You can see which files haven't been committed yet)

## git add <*file*>
Adds a file to the staging area. One at a time.  
(Prepares files for commit before committing)

## git add .
Adds all changes in the current folder to the staging area.  
(Prepares all changes made in the project for commit)

## git commit -a
Instead of using git add, this can commit everything directly.

## git commit -m
Permanently saves the changes in the staging area.  
(This is the actual save/commit in git)
* git commit -m "feat: login screen updated"

## git commit --amend
To change the last commit message.  
(To fix a mistake made in the last commit)

## git log
Shows the commit history.  
(You can see which commits were made previously in the project)

## .gitignore
For files you don't want anyone to see. Git won't track this file.  
(If you put the name of a file you don't want to be seen inside this file, that file gets hidden)

## git branch <*new-branch*>
Creates a new branch.  
(Used to open a separate branch when developing something new)

## git branch
Lists existing branches.  
(Used to see which branch you're on and whether other branches exist)

## git switch 
Switches to another branch.

## git switch -c 
Creates a new branch and switches to it immediately.  
(Used to open a branch for a new feature and start working on it right away)

## git merge 
A command used to combine two branches with each other.

## git stash
Temporarily saves changes made without committing.  
(Used when you need to switch branches without losing unfinished work)

## git stash list
Used to see how many temporary saves (stashes) exist.

## git stash pop
Brings back the last stash and removes it from the stash list.  
(We use this to restore saved changes)

## git stash apply
Brings back the stash but doesn't remove it from the list.  
(Apply is the safer option if you need to use the same stash again)

## git stash clear
Deletes all stash records.  
(Hard to undo, be careful)

## git restore
Undoes changes in a file.  
(Deletes changes that haven't been committed, be careful)

## git checkout 
Used to switch branches, or in older Git usage, to switch files/commits.

## git reset
Used to undo a commit or staging state.  
(Reset is a powerful command, must be used knowing what you're doing)

## git reset --hard 
Completely undoes the commit and the changes.  
(Deletes the changes, must be used very carefully, doesn't even leave them staged)   
[git reset --hard: deletes the commit, doesn't create a new commit, risky]

## git revert 
Undoes the effect of a commit by creating a new commit.  
(Safer than reset for undoing shared commits)  
[git revert: preserves the commit, creates a new "undo" commit, safe — everyone can see what was undone]

## git diff
Shows changes that haven't been added to the staging area yet.  
(Used to check what exactly you changed in a file)  
* git diff <*commit1 commit2*>
* git diff <*main branch*>

## git rebase
Repositions a branch's commits onto the end of another branch.  
(Used to make the history look cleaner, but must be used carefully)  
[The important thing is that I haven't shared the commits I want to change the base of, and that other people aren't using them]

## git push
Sends local commits to the remote repository.  
(Uploads the commits on your computer to GitHub)

## git push -u origin main
Sends the main branch to the remote repository named origin and makes the connection permanent.  
(Usually used on the first push operation)

## git remote add origin
Connects the local project to the repository on GitHub.  
(Establishes the connection before sending the project on your computer to GitHub)
* git remote add origin https://github.com/username/project.git   

## git remote remove origin
Removes the connection to the remote repository.  
(Used to remove the connection if you connected to the wrong GitHub repo)

## git fetch
Downloads changes from the remote repo but doesn't merge them automatically.  
(Safely checks whether there are changes on GitHub)  
[A safer command, it brings the changes into the local repo but doesn't change your files. It lets you review the files before merging, before changing files or commits]

## git pull
Downloads changes from the remote repo and merges them with the branch you're on.  
(Used to bring the current version on GitHub to your computer)    
git pull = git fetch + git merge     
[It directly changes our own files — we both bring them into the local repo and merge them, creating a new commit; we pull in all the changes here]

## git clone
Downloads a GitHub repo that exists remotely to your computer.  
(Downloads all the files, now I can use it on my own computer)
* git clone https://github.com/username/project.git