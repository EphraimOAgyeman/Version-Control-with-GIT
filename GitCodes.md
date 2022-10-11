## This is a document- summary of codes for `git`

---


#### Summary of lessons

  1. Setup
  2. Navigating directories
  3. Creating a file or directory
  4. Cloning a directory or repo
  5. Checking the status of the repo or directory
  6. Ignoring files
  7. Adding and removing tags
  8. Branches
  9. Checkouts
  10. Merge and merge conflicts
  11. Reversing commits
  12. Resetting commits

# _Setup of GIT_

#### a. Download `GIT` from the website

Click [here](https://git-scm.com/downloads) to go to download page and complete the installation

#### b. Set up terminal

Click [here](https://github.com/EphraimOAgyeman/Git/blob/080fe1368cdfcfa74c177daadf8bdb9b3fa9351c/ud123-udacity-terminal-config.zip) to download the files.

  1. Extract it
  2. Move the extracted files to the home directory
  3. Change the file names by adding `.` infront of them
  4. Done

#### c. Set up credentials
  
   sets up Git with your name
> `git config --global user.name "Your-Full-Name"`

   sets up Git with your email
> `git config --global user.email "your-email-address"`

#### d. Set up editor

  I use VScode, thus this is my code for the setup. Click [here](https://docs.github.com/en/get-started/getting-started-with-git/associating-text-editors-with-git) to find yours
  
> `git config --global core.editor "code --wait"`  


# _Navigation directories_

### **Codes in GIT**

1. `cd` - change directory in or out
2. `ls` - list all available repositories or directories
3. `rm` - remove repository
4. `q` - To exit a commit history display

# _Creating, Cloning,  and Status_

 ### **How to start a repository**
 
 >`mkdir` -- name of repo

### How to create a new file

> `touch "filename.extension_name"`

### How to edit a file

> `nano fileName.txt`

After having your work done, press `Ctrl + x`. 

Then approve changes with `y` to finally exit nano.

**NB:** This is best on newly created files, not exiting files with content since you cannot navigate to exactly where you want the change in a content-exiting file.

### **How to initialize a created repo**

> `git init` - gains the task _master_

### **How to clone an existing repo**

> `git clone` --link --new_name

### How to check the status of a repo created

> `git status`

### How to display the commits of a repo

> `git log` - all details of the commit history

> `git log --oneline` shows one commit per line

### How to display the commits of a repo - in super detials

> `git log --stat` - files changed, number of files added or deleted. - stats == statistics


### How to view the specific changes made in every commit

> `git log -p` - p represents patch or change

### How to view the specific changes for a specific commit

Add the first 7 parts of the SHA as a flag
> `git log -p fdf5493`

or

> `git show fdf5493`



### Ignoring some files

There are times one has to ignore a file or more.
To do this
  1. You have to create a `.gitignore` file inside the where you have the hidden git directory
  2. Add the name of the file you want to ignore inside the the ignore file created.

# _Tags, Branch and Merge_

### Adding a tag in git

Running `git tag -a "tagName"` will tag the most recent commit.

> `git tag -a v1.0`

### Tagging an older commit
All you have to do is provide the `SHA` of the commit you want to tag

> `git tag -a v1.0 a87984`

### Deleting a tag
> `git tag -d v1.0`

### How to list all the branches in a repo

> `git branch`

### How to create a new branch

> `git branch "branchName"`

### How to move the head to any branch

> `git checkout "branchName"`

### How to know which branch has the head

> `git branch` - check the astericks

or

> `git log --oneline --decorate` - An arrow explicitly says which branch has the head

### How to make a branch on any commit

> `git branch "branchName" "SHA"`

Please verify if you want to make the branch before a particular commit or make the commit after the branch.

### How to delete a branch

> `git branch -d "branchName"`

### How to checkout and create a branch in one command

> `git checkout -b "branchName"`

> `git checkout -b "branchName" "exitingbranch"` - This shows where to particularly create the branch.

### How to see all the branches at once

> `git log --oneline --decorate --graph --all`

### How to merge - regular merge

> `git merge "name-of-branch-to-merge-in"`

When a merge happens, Git will:

* look at the branches that it's going to merge
* look back along the branch's history to find a single commit that both branches have in their commit history
* combine the lines of code that were changed on the separate branches together
* makes a commit to record the merge

### Fast-forward merge

Get into your branch, then merge the other branch(es) with it

> `git merge footer`

### Merging conflicts

To resolve a merge conflict, you need to:

* Choose which line(s) to keep
* Remove all lines with indicators

once the resolve it done, add and commit the file again

### Alter your most-recent commit

With this command, you can alter the most-recent commit.

> `git commit --amend`

**It is used in two ways:**
1. When its about the message
2. When you have to change files

_In the first instance,_ if you have a clean working directory and you pass `git commit --amend`, you simply get the chance to chance the commit message.

_In the second scenario,_ if you have to make changes in the last commit you made, instead of making a new commit;
1. edit the file(s)
2. save the file(s)
3. stage the file(s)
4. and run `git commit --amend`

### How to revert a commit

`git revert "SHA-of-commit-to-revert"`

### How to erase commits

Resetting erases commits!

⚠️ **To Reset Is Dangerous** ⚠️

You can reference commits by their `SHA`, by `tags`, `branches`, and the special `HEAD` pointer.

Sometimes, you can use parent and grandparent style for reference...

* `^`or `~` – indicates the parent commit


* `Head^` - first commit after head
* `Head^^` - second commit after head
* `Head^^^` - third commit after head

or

* `Head~1` - first commit after head
* `Head~2` - second commit after head
* `Head~3` - third commit after head

Branches arent recorded with this reference type ^^

---


* `Head^2` - Branch at first commit after head
* `Head^^2` - Branch at second commit after head
* `Head^^^2` - Branch at third commit after head

This command is used to reset (erase) commits:

`git reset "reference-to-commit"`


It can be used to:

* move the HEAD and current branch pointer to the referenced commit
* erase commits
* move committed changes to the staging index
* unstage committed changes

The kind of reset flag will state which category it falls within.

`--mixed`- working directory - default setting

`--soft` - staging index

`--hard` - trash

> `git reset HEAD^^ --hard`

### Making a backup

simply make a branch called backup or anything else

> `git branch backup`

### Find lost commits in the last 30 days

> `git reflog`

---

_Get video tutorials of this document-summary [here](https://classroom.udacity.com/courses/ud123)_




@Ephraim Opoku-Agyeman
