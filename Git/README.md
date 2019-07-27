# HackYourFuture

Hack Your Future Git classwork.

## Version Control

Version control systems are a category of software tools that help a software team manage changes to project's source code over time. 

## Why Version Control?

1. History
    - Keep a track of every change we make to our project. We can know which code was added on which day to which particular file. Thus, if a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the bug while minimizing disruption to all team members.
2. Collaboration
    - Allows multiple developers to work on the same project with ease without having to worry about to manage changes from all of them. Without a VCS, a developer has to get a lock on a file he/she is editing so that no one else touches that file and hence avoid the painful task of merging all changes manually.

## What is Git?

Git is one of the most popular version management tools available. In addition to above VCS features, one of the advantageous feature that Git provides is its branching capabilities. In Git, each developer gets their own local repository, complete with a full history of commits. This allows all developers to work in an isolated environment using feature branches. This is also termed as a distributed version control system.

## Create a Git repository

[git init](https://git-scm.com/docs/git-init) - creates an empty git repository. An initial HEAD file that references the HEAD of the master branch is also created.

[git clone](https://git-scm.com/docs/git-clone) - create a copy of an existing repository on your machine. Internally, it calls `git init` to create a repository and later copies contents from the repository to your machine.

## Git staging

Files in a repository go through three stages before being under version control with Git. Use `git status` to understand which stage the files in repository are at.

1. Untracked
    - The file exists but is not part of Git's version control. Use [git add](https://git-scm.com/docs/git-add) to add files to staging area. Use `git diff` to see the differences in code before you intend to add it to staging.
2. Staged
    - The files here are in the staging area and ready to be committed.
3. Committed
    - Use [git commit](https://git-scm.com/docs/git-commit) to create a record or a snapshot of changes which you have made. Usually, this is done by recording a short message that explains what we did and why.
    - One useful command in this section is `git commit --amend` flag, which allows you to amend the previous commit, for example to fix a spelling mistake.

**git rm**

This command is the (almost)inverse of `git add`. It can be used either to unstage staged files(using **--cached** option) or remove files entirely from the git repository.

## Remote

As Git is a distributed VCS, most work is often done on a developer's local repository. In order to communicate with the outside world and share work with other developers, Git uses what is called as **remotes**. These are repositories other than our local where we can push our changes and from which we can pull work done by other developers.

[git remote](https://git-scm.com/docs/git-remote) - This command lets you create, view and delete connections to other repositories. 

Once our work is committed in our local repository and is ready to be shared with other developers, we should push those changes to the remote git server. In order to create that connection, we use 

```
git remote add <alias> <remote-url>
```

It takes two arguments: a remote name which acts as an alias to the remote server and the URL of the remote server.

You can also remove a connection to a remote repository using 

```
git remote rm <name>
```` 

or rename the alias using 

```
git remote rename <old-name> <new-name>
```

[git push](https://git-scm.com/docs/git-push) - It allows a developer to upload local repository content to a remote repository once all local commits are ready to be shared with the outside world. Usually, you provide the remote alias along with the branch name as command line arguments. Example,

```
git push origin master
```

**Note:** When you clone a repository with `git clone`, it automatically creates a remote connection called **origin** pointing back to the cloned repository.

## Branching

It is a way of working where you can diverge from the main line of development and continue to do work without messing with that main line. A detailed explanation of how branching in git works is present [here](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell).

Execute below to create a new branch and switch to it on your local
```
git branch <branch-name>
git checkout <branch-name>
```

or use a shorthand

```
git checkout -b <branch-name>
```

#### HEAD ####

It is a reference to the last commit object in the currently checked-out branch(or tip of the current branch). It is used by Git to keep a track on what branch are you currently on. When a developer switches branches using `git checkout`, the HEAD revision changes to point to the tip of the new branch. Use `cat .git/HEAD` to see current position of HEAD.

#### Tracking ####

Tracking branches know which remote branches they are related to. When we checkout a branch from remote repository and have established an upstream branch relationship, the local `<branch-name>` can be considered as the **local tracking branch** and `<remote>/<branch-name>` can be considered as **remote tracking branch**.

This is quite useful when we intend to do push and pull operations to interact with our remote repository.

Executing below would checkout a new branch and establish a tracking with the remote branch name.
```
git checkout -b <branch-name> --track <remote-alias>/<remote-branch-name>
```

## Forking

It is a Git workflow which instead of using a single server-side repository to act as the “central” codebase, gives every developer their own server-side repository. This means that each contributor has not one, but two Git repositories: a private local one and a public server-side one. This type of a workflow is quite common in open-source projects.

The main advantage of the Forking Workflow is that contributions can be integrated without the need for everybody to push to a single central repository.

Developers push to their own server-side repositories, and only the project maintainer can push to the official repository.

Workflow:
1. When a new developer wants to start working on a project, they do not directly clone the official repository. Instead, they fork the official repository to create a copy of it on the server. 
2. After they have created their server-side copy, the developer performs a git clone to get a copy of it onto their local machine.
3. When they're ready to publish a local commit, they push the commit to their own public repository—not the official one.
4. Then, they file a pull request with the main repository, which lets the project maintainer know that an update is ready to be integrated. 

## Other frequently used commands
- [git pull](https://git-scm.com/docs/git-pull)
- [git fetch](https://git-scm.com/docs/git-fetch)

## References
- https://nl.atlassian.com/git/tutorials
- https://git-scm.com/book/en/v2
