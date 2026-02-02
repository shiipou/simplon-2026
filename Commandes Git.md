
# Commandes Git

---
## Configuration and help


	Defines username:
		Set a config option:
		$ git config user.name "Your name"
		Set option globally:
		$ git config --global user.name "Your name"
	
	Defines the email address:
	$ git config --global user.email "email@example.com"
	
	Display all actives configuration variables:
	$ git config --list

	Add an alias:
	$ git config --global alias.co checkout

	See all possible config options:
	$ man git-config

	Get help on command:
	$ git help command or git command --help

---

## Getting started

	Create a new local repository:
		$ git init

	Download from an existing repository:
		$ git clone my_url

	Add a remote:
	$ git remote add <name> <url>


---

## Observe your repository

	List new or modified files not yet comitted:
		$ git status

	Show the changes to files no yet staged:
		$ git diff

	Show the changes between two commit IDs:
		$ git diff commit1 commit2

	Show full change history:
		$ git log

	Show change history for file/directory including diffs:
		$ git log -p [file/directory]

	Show the file changes for a commit ID and/or file :
		$ git show [commit] : [file]
	

---

## Make a change


	Stages the file, ready for commit:
	$ git add [file]

	Add all files or repositories to staging area:
	$ git add -A

	Commit stages changes with a message:
	$ git commit -m "Add message"

	Stage and commit changes with a message:
	$ git commit -am "Add message"

	Amend the last commit:
	$ git commit --amend

	Unstages file, keeping the file changes:
	$ git reset [file]

	Revert everything to the last commit:
	$ git reset --hard


---


## Working with Branches


	List all local branches:
	$ git branch

	List all branches, local and remote:
	$ git branch -av

	Create a new branch, call "new_branch":
	$ git branch new_branch

	Switch to a branch "my_branch", and update working directory:
	$ git checkout my_branch

	Checkout and create branch:
	$ git checkout -b new_branch

	Delete the branch called "my_branch":
	$ git branch -d my_branch

	Merge branch_b to branch_a:
	$ git checkout branch_a
	$ git merge branch_b

---

## Synchronize


	Fetch the latest changes from origin and merge:
	$ git pull

	Get the latest changes from origin:
	$ git fetch

---

## Push your changes


	Push a branch that you've never pushed before:
	$ git push -u origin <name>

	Push the main branch to the remote:
	$ git push origin main

	Push the current branch to default remote:
	$ git push
