# Git Commands

###################
## Configuration ##
###################

### git config --global user.name "Your Name"
Sets the username in git

### git config --global user.email "your.email@your-place.com"
Sets the users email in git

### git config core.editor "mate -w"
Sets textmate as default git editor

### git config core.editor "code -w"
sets vscode as default git editor. (add code in shell - https://code.visualstudio.com/docs/setup/mac)

### git config --global -e
Opens global git config file in specified editor.

### git init
Create an empty Git repository or reinitialize an existing one.

### git config --global --list
Lists all global configurations

### git config --global diff.tool p4merge
### git config --global difftool.p4merge.path "/Applications/p4merge.app/Contents/MacOS/p4merge"
### git config --global difftool.prompt false
Configure P4Merge as Diff tool
(Download: https://www.perforce.com/products/helix-core-apps/merge-diff-tool-p4merge)

### git config --global merge.tool p4merge
### git config --global mergetool.p4merge.path "/Applications/p4merge.app/Contents/MacOS/p4merge"
### git config --global mergetool.prompt false
Configure P4Merge as Merge tool
(Download: https://www.perforce.com/products/helix-core-apps/merge-diff-tool-p4merge)


##############
##  Basics  ##
##############  

###	git status 
shows status of current work & staging area. And also untracked files.

###	git add <file>
takes file from working area and places it on stagin area.

### git add .
Adds all files from the working area to the staging area.

## git rm --cached <file>
Removes file from repo and staging and sets it as untracked.

### git reset HEAD <file>
Removes file from staging area and puts it to the working area.

### git reset HEAD .
Removes all files from the staging area and places them on the working area.

### git commit <file>
Commits selected file to the repo. (Opens file for message)

### git commit -m "<message>"
A little bit faster to put q file to the repo.

### git commit -a
Commits a file from the working area directly to the repo. (Opens file for message)

### git commit -am "<message>"
Commits a file from the working area directly to the repo.

### git mv <old_filename> <new_filename>
Renames a file and also keeps track about it. (need commit afterwards)

### git checkout <file>
if changes are in the working area -> gets the last version in the repo (gets "original")

### git checkout .
gets the last version in the repo of all files in the working area (removes changes)

### exclude files from git
Create .gitignore file. (mate .gitignore)
Each line represents 1 expression (<filename>)
(i.e. *.log -> excludes all files that end with '.log')


###################################
##  Clean changes outside of git ##
###################################

### git add -u
if you renamed a file without git mv (recommended).
Updates these changes to the staging area.
(needs commit afterwards)

### git add -A
All file modification get to the staging area.
(i.e. if you changed the name of a file, and the new name is marked as untracked file.)

##############
##  Alias   ##
##############

### git config --global alias.<alias name> "<alias command>"
add an alias to git (can be found in git config --global --list)
(i.e. git config --global alias.history "log --oneline --graph --decorate --all")

-------------------------------------------------------------------------------