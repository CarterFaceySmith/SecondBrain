Pleb, must've been a hot min since you used the command line if you're consulting this.

## The General Setup
Once project is setup and open in VS Code, and repo is setup:
	- `git remote add origin <url>`
	- `git fetch origin
	- `git add .`
	- `git commit -m "initial commit"
	- `git push origin main`

Alternatively you can set the repo up entirely from the command line:
- ```git init```
- ```touch README.md```
- ```git add README.md```
- ```git commit -m "initial commit"```
- ```gh repo create <reponame> --public or --private```
- ```git remote add origin git@github.com:carterfaceysmith/<reponame>.git```
- ```git push -u origin main```

## Commands

- `git init`: Initialize the repository

- `git status`: Check the current directory changes and staging area

- `git add <directory>`: Add current files to staging

- `git commit -m "<commit-message>"`: Commit staging with a message

- `git commit -am "<commit-message>"`: Add & Commit staging with a message (only for edited and deleted)

- `git log --oneline`: Print the log as one line

- `git log --oneline --decorate --all --graph`: Print the log as one line and in graph-mode

- `git reflog`: Show the log of changing the HEAD. It's useful to find missing commits.

- `git branch <branch-name>`: Create a new branch

- `git checkout <branch-name>`: Checkout to a branch

- `git checkout -b <branch-name>`: Create and checkout to a branch

- `git diff <commit-hash-source> <commit-hash-destination>`: Show the difference between two commits

- `git merge <branch-name>`: Merge a branch into the current branch

- `git merge --squash <branch-name>`: Merge a branch into the current branch as a single commit

- `git branch -D <branch-name>`: Delete a branch

- `git push origin --delete <branch-name`: Delete a remote branch

- `git rebase <branch-name>`: Rebase the current branch on another branch

- `git rebase <branch-name> -i`: Rebase the current branch on another branch (with interactive mode)

- `git cherry-pick <commit>`: Apply changes for a certain commit to the current branch

- `git reset --hard <commit-hash>`: Move the branch Head to a certain commit

- `git mv <source> <destination>`: Move a file/directory from one place to another while tracking

- `git remote add <remote-name> <repository-name>`: Add a remote tracking branch. `<remote-name>` is usually `origin`.

- `git push --set-upstream <remote-name> <branch-name> <repository-name>`: Set a remote for a branch

- `git push -u <remote-name> <branch-name> <repository-name>`: Set a remote for a branch (Same to the above one)

- `git push`: Push local commits

- `git fetch`: Fetch commits from remote

- `git pull`: Fetch commits and merge

- `git fetch --prune`: Remove branches that no longer exists on remote before fetching

- `git remote prune origin`: Remove branches from local repository that no longer in remote

## Collaboration

### Pull Request

We need merge to master locally but rather we push the branch and create a Pull Request/Merge Request.

Other developers will review your changes and add comments.

When all is resolved and approved, you can merge your changes.

### Merge Conflicts

Merge conflicts happen when git can't merge two branches. It's always 99% to happen if a file is changed on the same line in two different branches, that's when git can't decide how to merge.

To resolve it, it has to be done manually and you will need to check the git log to find the developer responsible for the conflict and align with them.

### Branching Strategies

#### Single Branch

Create a single main branch and push all your commits there.

Good for personal projects.

#### Feature Branching

We have a single branch and each time there is a feature/bug, we create a new branch, do the changes and then merge back to main branch.

#### Git Flow

We have two branches develop and main.

When creating a feature/bugfix, we create a feature branch from develop. Changes are merged back to develop.

When creating a hotfix, we create a feature branch from main. Changes are tagged with a version and only merged back to develop (if needed).

We can only merge develop into master and we need to tag the commit with a release version.
