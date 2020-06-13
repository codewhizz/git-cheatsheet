`git config --global user.name USERNAME`\
`git config --global user.email EMAIL`

`cat ~/.gitconfig`
`git config --global --list`
`git config --global -e`



### Config P4Merge as Default Merge Tool and Diff Tool
In Windows Add P4Merge installation directory as path to environment variables

`git config --global merge.tool p4merge`\
`git config --global mergetool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"`\
`git config --global mergetool.prompt false`

`git config --global diff.tool p4merge`\
`git config --global difftool.p4merge.path "C:/Program Files/Perforce/p4merge.exe"`\
`git config --global difftool.prompt false`


### Git States
There are 3 Local states:
* **Working Directory**\
	Contains all files and folders for the application which may or may not be managed by Git. Either way, Git is aware of those files.
* **Staging Area**\
	Used to prepare for the next commit. Files are moved from modified working directory state to the staging area.
* **Repository (.git folder)**\
	Contains all the commited or saved changes to the Git repo. Anything here is part of Git's history.

Consider this 4th state:
* **Remote**\
	It's another repo with its own 3 states internally.


## 1. Initialize Project / Repository
`git init PROJECT_NAME`  <!-- creates a folder called PROJECT_NAME and initializes a git repository -->\
`git init .`  <!-- if project folder is already created, initialize inside it -->
<!-- Note: A .git folder is created inside which is the actual git repository-->


## 2. Repository Status
`git status`


## 3. Move files to Staging Area
`git add FILE_NAME`  <!-- Adds the file with FILE_NAME to the staging area -->\
`git add ./FOLDER_NAME`  <!-- Adds the folder with FOLDER_NAME to the staging area -->\
`git add .`  <!-- Recursively adds all the files and folders from the working directory -->\
`git add -A`\
`git add -u`  <!-- staging deleted files -->


## 4. Move files into .git repo folder (Commit Changes)
`git commit -m "COMMIT MESSAGE"`  <!-- 'm' option allows to provide a commit message -->\
`git commit`  <!-- An editor pops up automatically and commit message can be entered there -->


## 5. Commit History
`git log`  <!-- All commits that are part of this repository -->\
`git show`  <!-- Shows the last commit and diff containing all the changes -->\
`git log --oneline --graph --decorate --all`


## 6. Express Commit
`git commit -am "COMMIT MESSAGE"`  <!-- Used for modified files and not untracked(new) files -->


## 7. Backing out Changes
`git restore .`\
`git restore FILE_NAME/FOLDER_NAME`\
`git restore --staged .`\
`git restore --staged FILE_NAME/FOLDER_NAME`


## 8. Git Aliases
`git config --global alias.hist "log --oneline --graph --decorate --all"`


## 9. Rename and Delete using Git
`git mv ORIGINALFILE_NAME CHANGEDFILE_NAME`\
`git rm FILE_TO_REMOVE`
<!--Note: Commit required after this -->