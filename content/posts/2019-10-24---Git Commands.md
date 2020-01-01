---
title: Git Commands
date: "2019-10-24 T10:00:00.000Z GMT+0900"
template: "post"
draft: false
slug: "/posts/git_commands/"
category: "Git"
tags:
  - "GIT"
  - "GITHUB"
description: A list of my commonly used Git commands
socialImage: "../../static/media/macbook_showing_programming_language.jpg"
---

> # Tell Git who you are

- ### Configure the author name and email address to be used with your commits. Note that Git strips some characters (for example trailing periods) from user.name. :

```
git config --global user.name "Chungsik Park"
git config --global user.email chungsik@example.com
```

---

> # Create repository

- ### Create a new local repository :

```
git init
```

---

> # Check out a repository

- ### Create a working copy of a local repository :

```
git clone /path/to/repository
```

- ### For a remote server, use :

```
git clone username@host:/path/to/repository
```

---

> # Add files

- ### Add one or more files to staging (index) :

```
git add <filename>
git add .
```

---

> # Commit

- ### Commit changes to head (but not yet to the remote repository) :

```
git commit -m "Commit message"
```

- ### Commit any files you've added with git add, and also commit any files you've changed since then :

```
git commit -a
```

---

> # Push

- ### Send changes to the master branch of your remote repository :

```
git push origin master
```

---

> # Status

- ### List the files you've changed and those you still need to add or commit :

```
git status
```

---

> # Connect to a remote repository

- ### If you haven't connected your local repository to a remote server, add the server to be able to push to it :

```
git remote add origin <server>
```

- ### List all currently configured remote repositories :

```
git remote -v
```

---

> # Branches

- ### List all the branches in your repo, and also tell you what branch you're currently in (This is synonymous with git branch --list.) :

```
git branch
```

- ### Create a new branch called <branch> (This does not check out the new branch.) :

```
git branch <branch>
```

- ### Delete the specified branch (This is a “safe” operation in that Git prevents you from deleting the branch if it has unmerged changes.) :

```
git branch -d <branchname>
```

- ### Force delete the specified branch, even if it has unmerged changes (This is the command to use if you want to permanently throw away all of the commits associated with a particular line of development.) :

```
git branch -D <branchname>
```

- ### Rename the current branch to <branch> :

```
git branch -m <branchname>
```

- ### List all remote branches :

```
git branch -a
```

- ### Switch from one branch to another :

```
git checkout <branchname>
```

- ### Create a new branch and switch to it :

```
git checkout -b <branchname>
```

- ### Push the branch to your remote repository, so others can use it :

```
git push origin <branchname>
```

- ### Push all branches to your remote repository :

```
git push --all origin
```

- ### Delete a branch on your remote repository :

```
git push origin :<branchname>
```

---

> # Update from the remote repository

- ### Fetch and merge changes on the remote server to your working directory :

```
git pull
```

- ### To merge a different branch into your active branch :

```
git merge <branchname>
```

- ### View all the merge conflicts :

```
git diff
```

- ### View the conflicts against the base file :

```
git diff --base <filename>
```

- ### Preview changes, before merging :

```
git diff <sourcebranch> <targetbranch>
```

- ### After you have manually resolved any conflicts, you mark the changed file :

```
git add <filename>
```

---

> # Tags

- ### CommitId is the leading characters of the changeset ID, up to 10, but must be unique. Get the ID using :

```
git log
```

- ### You can use tagging to mark a significant changeset, such as a release :

```
git tag 1.0.0 <commitID>
```

- ### Push all tags to remote repository :

```
git push --tags origin
```

---

> # Search

- ### Look through the files in your working directory :

```
git grep
```

- ### Option to print out the line numbers where Git has found matches :

```
git grep -n "String"
git grep --line-number "String"
```

- ### Option to summarize the output by showing you only which files contained the search string and how many matches there were in each file :

```
git grep --c "String"
git grep --count "String"
```

- ### Option to find the enclosing method or function for each matching string :

```
git grep -p "String"
git grep --show-function "String"
```

---
