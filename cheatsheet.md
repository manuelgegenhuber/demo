# Git Commands

###################
## Configuration ##
###################

### git init
Create an empty Git repository or reinitialize an existing one.

### git config --global --list
Lists all global configurations


##############
##  Basics  ##
##############  

###	git status 
shows status of current work & staging area. And also untracked files.

###	git add <file>
takes file from working area and places it on stagin area.

### git add .
adds all files from the working area to the staging area.

### git reset HEAD <file>
removes file from staging area and puts it to the working area.

### git reset HEAD .
removes all files from the staging area and places them on the working area.

### git commit <file>
commits selected file to the repo. (Opens file for message)

### git commit -m "<message>"
a little bit faster to put q file to the repo.

### git commit -a
commits a file from the working area directly to the repo. (Opens file for message)

### git commit -am "<message>"
commits a file from the working area directly to the repo.

### git mv <old_filename> <new_filename>
renames a file and also keeps track about it. (need commit afterwards)

### git checkout <file>
if changes are in the working area -> gets the last version in the repo (gets "original")

### git checkout .
gets the last version in the repo of all files in the working area (removes changes)

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