# Git Commands
List of Commony used commands in Git

#### Start a new repository and publish it to GitHub:
  Create empty repo in public git and follow the steps

* create a new directory, and initialize it with git-specific functions <br>
`git init my-repo`

* change into the `my-repo` directory <br>
`cd my-repo`

* create the first file in the project <br>
`echo "# Second-Project" >> README.md`

* git isn't aware of the file, stage it <br>
`git add README.md`

* take a snapshot of the staging area <br>
`git commit -m "first commit"`

* provide the path for the repository you created on github <br>
`git remote add origin https://github.com/sudhu-gowda/My-Repo.git`

* push changes to github <br>
`git push -u origin master` or <br>
`git push --set-upstream origin master`

================================================

#### Contribute to an existing repository:

* download a repository on GitHub.com to our machine <br>
`git clone https://github.com/me/repo.git`

* change into the `repo` directory <br>
`cd repo`

* create a new branch to store any new changes <br>
`git branch my-branch`

* switch to that branch (line of development) <br>
`git checkout my-branch`

* make changes, for example, edit `file1.md` and `file2.md` using the text editor

* stage the changed files <br>
`git add file1.md file2.md`

* take a snapshot of the staging area (anything that's been added) <br>
`git commit -m "my snapshot"`

* push changes to github <br>
`git push --set-upstream origin my-branch`

===================================================

#### Contribute to an existing branch on GitHub

<b> assumption:</b> a project called `repo` already exists on the machine, and a new branch has been pushed to GitHub.com since the last time changes were made locally

* change into the `repo` directory <br>
`cd repo`

* update all remote tracking branches, and the currently checked out branch <br>
`git pull`

* change into the existing branch called `feature-a` <br>
`git checkout feature-a`

* make changes, for example, edit `file1.md` using the text editor <br>

* stage the changed file <br>
`git add file1.md`

* take a snapshot of the staging area <br>
`git commit -m "edit file1"`

* push changes to github <br>
`git push`

================================================

#### Other Usefull Commands:

* to create branch & check out
`git branch branchName` <br>
`git checkout branchName` <br>or<br>
`git checkout -b branchName`

* to check the current working branch <br>
`git branch` --> this will be indicated asteric mark with dark color

* to switch between branch <br>
`git checkout branchName`

* to merge current working branch with master branch: <br>
`git merge master`

* Merge a branch into a target branch <br>
`git merge [source branch] [target branch]`

* to pull the data to master from server <br>
* update local repository to the newest commit <br>
`git pull`

* Clone a remote branch and switch to it <br>
`git checkout -b [branch name] origin/[branch name]`

* Rename a local branch <br>
`git branch -m [old branch name] [new branch name]`

* Switch to the branch last checked out <br>
`git checkout -`

* Discard changes to a file <br>
`git checkout -- [file-name.txt]`

------------------------------

* Push a branch to your remote repository <br>
`git push origin [branch name]`

* Push changes to remote repository (and remember the branch)	 <br>
`git push -u origin [branch name]`

* Delete a remote branch <br>
`git push origin --delete [branch name]`

* Update local repository to the newest commit <br>
`git pull`

* Pull changes from remote repository <br>
`git pull origin [branch name]`

* Add a remote repository <br>
`git remote add origin ssh://git@github.com/[username]/[repository-name].git`

* Set a repository's origin branch to SSH <br>
`git remote set-url origin ssh://git@github.com/[username]/[repository-name].git`

==============================================

#### Inspection & Comparison

* View changes <br>
`git log`

* View changes (detailed) <br>
`git log --summary`

* View changes (briefly) <br>
`git log --oneline`

* Preview changes before merging <br>
`git diff [source branch] [target branch]`

==============================================

#### Configuration:

* To configure name: <br>
`git config --global user.name sudarshan`

* To configure email: <br>
`git config --global user.email sudarshan@gmail.com`

* To check the configured name: <br>
`git config user.name`

* To  check  the configured email: <br>
`git config user.email`

===============================================

#### Undoing Things

* Get the list of commit id with command <br>
`git log --oneline`

* To checkout:  <br>
`git checkout commit_id`

* To revert:  <br>
`git revert commit_id`

* To reset:  <br>
`git reset commit_id`

======================================

#### Commands to Work with git:

* To Initialize the repo <br>
`git init`

* To check the status of the file <br>
`git status`

* To stage file: <br>
`git add ./*/file_name`

* To unstage file <br>
`git rm --cached file_name`

* To commit file:<br>
`git commit -m "Commit Name"`

===================================

#### Merging Branches:

* Merging Branch: <br>
`git merge bch_name`

<b>Note:</b> To merge the branch branch_name with master, <br>
go to the master branch and execute the above command

* Handling conflicts while merging <br>
Git will automatically resolve the conflicts, In case if not, do the following steps <br>
<ul><li>	Go the conflicted file, edit or the change  the file to remove conflicts  </li>
<li>	git add * </li>
<li>	git commit </li> </ul>

===================================


