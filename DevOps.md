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

1: git restore --staged DevOps.md
Description: Unstage file from the staging area.

2: git branch <BranchName> -> git branch b1
Description: To create new branch.

3: git checkout <ExistedBranchName>
Description: To switch to the specified branch.

4: git add .
Description: To stage all changes in the working directory.
