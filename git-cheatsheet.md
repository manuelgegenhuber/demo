<h1>Configuration</h1>

<pre>git config --global user.name "Your Name"</pre>
Sets the username in git

<br>
<br>

<pre>git config --global user.email "your.email@your-place.com"</pre>
Sets the users email in git

<br>
<br>

<pre>git config core.editor "mate -w"</pre>
Sets textmate as default git editor

<br>
<br>

<pre>git config core.editor "code -w"</pre>
sets vscode as default git editor.
add code to shell - https://code.visualstudio.com/docs/setup/mac

<br>
<br>

<pre>git config --global -e</pre>
Opens global git config file in specified editor.

<br>
<br>

<pre>git init</pre>
Create an empty Git repository or reinitialize an existing one.

<br>
<br>

<pre>git config --global --list</pre>
Lists all global configurations

<br>
<br>

<pre>
git config --global diff.tool p4merge
git config --global difftool.p4merge.path "/Applications/p4merge.app/Contents/MacOS/p4merge"
git config --global difftool.prompt false
</pre>
Configure P4Merge as Diff tool
(Download: https://www.perforce.com/products/helix-core-apps/merge-diff-tool-p4merge)

<br>
<br>

<pre>
git config --global merge.tool p4merge
git config --global mergetool.p4merge.path "/Applications/p4merge.app/Contents/MacOS/p4merge"
git config --global mergetool.prompt false
</pre>
Configure P4Merge as Merge tool
(Download: https://www.perforce.com/products/helix-core-apps/merge-diff-tool-p4merge)

<br>
<br>

<pre>HEAD</pre>
Like "pointers"
Points to last Commit of current Branch
Can be Moved (Advanced)

<br>
<br>

-------------------------------------------------------------------------------

<h1>Basics</h1>

<pre>git status </pre>
shows status of current work & staging area. And also untracked files.

<br>
<br>

<pre>git add <file></pre>
takes file from working area and places it on stagin area.

<br>
<br>

<pre>git add .</pre>
Adds all files from the working area to the staging area.

<br>
<br>

<pre>git rm --cached <file></pre>
Removes file from repo and staging and sets it as untracked. (need commit afterwards)

<br>
<br>

<pre>git reset HEAD <file></pre>
Removes file from staging area and puts it to the working area.
HEAD -> last commit

<br>
<br>

<pre>git reset HEAD .</pre>
Removes all files from the staging area and places them on the working area.
HEAD -> last commit

<br>
<br>

<pre>git commit <file></pre>
Commits selected file to the repo. (Opens file for message)

<br>
<br>

<pre>git commit -m "<message>"</pre>
A little bit faster to put q file to the repo.

<br>
<br>

<pre>git commit -a</pre>
Commits a file from the working area directly to the repo. (Opens file for message)

<br>
<br>

<pre>git commit -am "<message>"</pre>
Commits a file from the working area directly to the repo.

<br>
<br>

<pre>git mv <old_filename> <new_filename></pre>
Renames a file and also keeps track about it. (need commit afterwards)

<br>
<br>

<pre>git checkout <file></pre>
if changes are in the working area -> gets the last version in the repo (gets "original")

<br>
<br>

<pre>git checkout .</pre>
gets the last version in the repo of all files in the working area (removes changes)

<br>
<br>

<pre>exclude files from git</pre>
Create .gitignore file. (mate .gitignore)
Each line represents 1 expression
(i.e. *.log -> excludes all files that end with '.log')

<br>
<br>

<h1>Clean changes outside of git</h1>

<pre>git add -u</pre>
if you renamed a file without git mv (recommended).
Updates these changes to the staging area.
(needs commit afterwards)

<br>
<br>

<pre>git add -A</pre>
All file modification get to the staging area.
(i.e. if you changed the name of a file, and the new name is marked as untracked file.)

<br>
<br>

<h1>Alias</h1>

<pre>git config --global alias.<alias name> "<alias command>"</pre>
add an alias to git (can be found in git config --global --list)
(i.e. git config --global alias.history "log --oneline --graph --decorate --all")

<br>
<br>

-------------------------------------------------------------------------------


<h1>Advanced</h1>

<pre>git diff #<commit number> HEAD</pre>
Compares the HEAD commit with the specified (commit mnumber) commit.
HEAD -> last commit

<br>
<br>

<pre>git difftool <commit number> HEAD</pre>
Compares the HEAD commit with the specified (commit mnumber) commit.
via the specified git.difftool (i.e. P4Merge)
cmd + q -> to quit P4Merge and return to the terminal.
HEAD -> last commit

<br>
<br>

<pre>git diff</pre>
Compares recent changes on the working directory with the HEAD commit.
HEAD -> last commit

<br>
<br>

<pre>git difftool</pre>
Compares recent changes on the working directory with the HEAD commit.
via the specified git.difftool (i.e. P4Merge)
cmd + q -> to quit P4Merge and return to the terminal.
HEAD -> last commit

<br>
<br>

<pre>git diff <branch name> master</pre>
Compares last commits on the specified branches.

<br>
<br>

<pre>git difftool <branch name> master</pre>
Compares last commits on the specified branches.
via the specified git.difftool (i.e. P4Merge)
cmd + q -> to quit P4Merge and return to the terminal.

<br>
<br>

<pre>git branch</pre>
Listd all branches
* -> you're currently on that branch.

<br>
<br>

<pre>git checkout <branch name></pre>
To switch to a specified branch.

<br>
<br>

<pre>git checkout -b <branch name></pre>
To create a new branch $
switch to that specified branch.

<br>
<br>

<pre>git merge <branch name> </pre>
Merges the commits into the current branch.
switch to master (recommended):
<br>
<code>git checkout master</code>
<br>

Fast-Forward
<ul>
<li>Simplest Case</li>
<li>Like Never Branched (Commits on Destination)</li>
<li>Can Be Disabled</li>
</ul>
Automatic
<ul>
<li>Non-Conflicting Merge Detected</li>
<li>Preserves both Timelines</li>
<li>Merge Commit on Destination</li>
<li>New Merge Commit is created</li>
</ul>
Manual
<ul>
<li>Automatic Merge Not Possible</li>
<li>Conflicting Merge State</li>
<li>Changes Saved in Merge Commit</li>
<li>New Merge Commit is created</li>
</ul>

<br>
<br>