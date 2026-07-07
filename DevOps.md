## Definition

Devops is a software development methodology which imporoves the collaboration between developers and operations team using various automation tools. These automation tools are implemented using various stages which are a part of the Devops Lifecycle.

Code => Plan => Build => Test => Release => Deploy => Operate => Monitor

## Version Control System?

Version control is a system that records/manages changes to documents compute programs etc over time. It helps us tracking changes when multiple people work on the same project.

- **Git**: Distributed version control system
- **GitHub/GitLab/Bitbucket**: Remote repository hosting services
- **Commands**: `git init`, `git add`, `git commit`, `git push`, `git pull`, `git merge`

## Problem before Version Control

- Versioning was manual
- Team collaboration was a time consiming and hectic tasks
- No easy access to previous version.
- Multiple version took a lot of space.

## Advantages of Version Control

- Versioning Automatic
- Team Collaboration is simple.
- Easy access to previous version.
- Only miodified code is stored accross different versions, hence saves storage.

## Types of Version Control System

1: Central VCS
2: Distributed VCS

Centralized VCS

- Centralized Version Control System has one single copy of code in the central server.
- Developer will have to "commit" their change in the code to this central server.
- "Commiting" a change simply means recording the change in the central system.

Distributed VCS

- In Distributed VCS, one does not necessarily rely on the central server to store all the version of a project's file.
- Every developer "clones" a copy of the main repository on their local system.
- This also copies, all the past version of the code on the local system too.
- Therefore, the developer need not to be connected to the internet to work on the code

Note: We follows Cetralized VCS

What is SVN?

SVN (Apache Subversion) is a centralized version control system developed by Apache Software Foundation. It manages files and directories and the changes made to them over time. Unlike Git, which is distributed, SVN requires a central server to store all versions of the codebase.

- **Centralized Repository**: All changes are committed to a central server
- **Commands**: `svn checkout`, `svn update`, `svn commit`, `svn add`, `svn delete`
- **History**: Tracks changes through revision numbers
- **Branching**: Supports branching and merging, though less flexible than Git

## Disadvantage of SVN?

- Constantly need an internet connection for any operation.
- Version history not downloaded or maintained on the local system.
- Slower than DVCS, since require intenet for every operation
- Slower performance compared to distributed VCS
- Limited offline capabilities
- Confilict have to resolve manually.

DVCS

- Git is the most popular tool among all the DVCS tools.

## Git

Git is a verison-control system for tracking changes in computer file and coordinate work on those files among multple people. It is primarily used for source-code management in softwate development, but it can be used to keep track of changes in set of files.

- **Distributed Architecture**: Every clone contains the full history of the repository
- **Local Operations**: Most commands operate locally without network access
- **Branching**: Lightweight and efficient branching and merging capabilities
- **Commands**: `git init`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git merge`

## Git Life Cycle

Working directory → Staging area → Commit -> Local Repository → Remote repository

Working Directory

- Once we are in the working directory, we have to specify which file are to be tracked by git.
- Use `git add <file>` to move changes from the working directory to the staging area.

Staging Area

- This is where changes are prepared before committing.
- Use `git commit -m "message"` to save the staged changes to the local repository.

Commit

- This is the snapshot of your changes that is saved to the local repository.
- Use `git commit -m "message"` to create a new commit with the staged changes.

Local Repository

- This is the database that stores all the commits and history of the project.
- Use `git push origin main` to upload your local commits to the remote repository.
- Use `git pull origin main` to fetch and merge changes from the remote repository to your local copy.

Remote Repository

- This is the central server where the codebase is hosted (GitHub, GitLab, Bitbucket, etc.).
- Use `git clone <repository-url>` to create a local copy of the remote repository.
- Use `git push` to upload local commits to the remote repository.
- Use `git pull` to fetch and merge changes from the remote repository to your local copy.

## Git Branching

Branches allow you to work on different versions of a project simultaneously without affecting the main codebase.

- **Main/Master**: The primary branch where the production-ready code lives
- **Feature Branches**: Created from main to develop new features (`git checkout -b feature-branch`)
- **Merge**: Integrating changes from one branch into another (`git merge feature-branch`)
- **Rebase**: Reapplying commits on top of another base tip (`git rebase main`)

## How does Git Work?

- Any project which is saved on git, is saved using a commit. The commit is identified using a commit ID.
- All these commits are bound to a branch. Any new commits made will be added to this branch. A branch always points to the latest commit. The pointer commit is known as HEAD.
- The default branch in a git repository is called the Master Branch.
- **HEAD**: Pointer to the current working branch
- **Staging Area**: Temporary area where changes are prepared before committing
- **Local Repository**: Database storing all commits and history
- **Remote Repository**: Central server hosting the codebase (GitHub, GitLab, etc.)

Note: Branch noting but timeline of commit.

## Common Git Commands

Createing Repository
Making Changes
Parallel Development
Making Changes
Parallel Development
Syncing Repositories

## Getting Started

1: git init - Start a new repo
Description: To initialize a new Git repository in the current directory.

2: git clone <url> - Clone an existing repo
Description: To create a local copy of a remote repository.

## Prepare to Commit

3: git add <filePath> - Add untracked file or unstaged changes
Description: To stage all changes in the working directory.

4: git add . - Add all untracked files and unstaged changes
Description: To stage all untracked files and unstaged changes.

5: git add -p - Choose which parts of a file to stage
Description: To interactively choose which parts of a file to stage.

6: git mv <old> <new> - Move or rename a file
Description: To move or rename a file in the working directory.

7: git rm <filePath> - Delete file
Description: To delete a file from the working directory.

8: git rm --cached <filePath> - Tell Git to forget about a file without deleting it:
Description: To remove a file from the repository while keeping it in the working directory.

9: git reset <file> - Unstage file from the staging area
Description: Unstage file from the staging area.

10: git reset - Unstage everything
Description: Unstage all files from the staging area.

11: git status - Check what you added:
Description: To display the current state of the working directory and staging area.

## Make Commits

1: git commit - Make a commit (and open text editor to write message)
2: git commit -m 'message' - Make a commit
3: git commit -am 'message' - Commit all unstaged changes

## Move Between Branches

1: git checkout <ExistingBranchName> or git switch <name> - Switch branches
Description: To switch to the specified branch.

2: git checkout -b <name> or git switch -c <name> - Create and checkout a branch:
Description: To create a new branch and switch to it.

3: git branch <BranchName> -> git branch b1 - Create new branch
Description: To create new branch.

4: git branch - List branches
Description: To list all local branches.

5: git branch --sort=-committerdate - List branches by most recently committed to
Description: To list branches sorted by most recent commit date.

7: git branch -D <name> - Force delete a branch
Description: To delete a branch forcefully.

## Diff Staged/Unstaged Changes

1: git diff <commitId_1> <commitId_2>
Description: To show the differences between two commits.

2: git diff --staged - Diff just staged changes:
Description: To show the differences between the staging area and the last commit.

3: git diff - Diff just unstaged changes
Description: To show the differences between the working directory and the staging area.

## Diff Commits

9: git fetch <remote>
Description: To download new commits from a remote repository without merging them.

10: git merge <branch>
Description: To integrate changes from a specified branch into the current branch.

11: git push <remote> <branch>
Description: To upload local commits to the specified branch on the remote repository.

12: git branch -r
Description: To list remote-tracking branches.

13: git log origin/main
Description: To view the commit history of the main branch on the remote repository.

14: git pull origin <BranchName>
Description: To fetch and merge changes from the specified branch on the remote repository.

15: git reset --hard HEAD
Description: To discard all local changes and reset the working directory to the last committed state.

16: git log
Description: To view the commit history of the current branch.

17: git stash -m "stash commit"
Description: To temporarily save uncommitted changes and revert the working directory to the last committed state.

18: git stash pop
Description: To apply the most recently saved stash and remove it from the stash list.

19: git revert
Description: To create a new commit that undoes the changes made by a previous commit.

19: git reset --hard HEAD~1
Description: To permanently remove the last commit from the current branch.

20: git merge <BranchName>
Description: To merge changes from the specified branch into the current branch.

21: git rebase <BranchName>
Description: This is an alternative to git merge command. Should be used on local branches, since history does change and will be confusing for other team members. Does not create any new commit, and result in a cleaner history. The history is based on common commit of the two branches (base). The destination's branch commit pulled from it's "base" and "rebased" on the latest commit on the source branch.

22: git push origin --delete checkout
Description: To delete a remote branch named 'checkout' from the remote repository.

23: git reset --soft HEAD~5
Description: To reset the current branch to the previous commit while keeping the changes in the staging area (soft reset).

24: git remote add origin <url>
Description: To add a new remote repository with the given name and URL.

25: git remote -v
Description: To list all configured remote repositories and their URLs.

26: git remote set-url origin <url>
Description: To change the URL of an existing remote repository.

## How to resolve Merge Confilict

- **Step 1**: Identify conflicting files using `git status` or `git diff`
- **Step 2**: Open the conflicting files and look for conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
- **Step 3**: Edit the file to keep the desired changes and remove the conflict markers
- **Step 4**: Stage the resolved file using `git add <file>`
- **Step 5**: Complete the merge by committing the changes with `git commit -m "Resolved merge conflict"`

## Git Cherry-Pick-----------------------------------------------

Cherry-picking allows you to apply the changes from a specific commit onto your current branch instead of merging.

- **Command**: `git cherry-pick <commit-id>`
- **Description**: Creates a new commit on the current branch with the changes from the specified commit, without merging the entire branch history.
- **Use Case**: When you want to apply a specific bug fix or feature from one branch to another without merging all changes from that branch.
- **Conflict Resolution**: If conflicts occur during cherry-pick, resolve them as described above and then use `git cherry-pick --continue` to proceed.
