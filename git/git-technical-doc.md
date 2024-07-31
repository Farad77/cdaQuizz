# Git Technical Documentation

## Introduction

Git is a distributed version control system designed to handle everything from small to very large projects with speed and efficiency. It was created by Linus Torvalds in 2005 for development of the Linux kernel.

## Key Concepts

### Repository
A Git repository is the `.git/` folder inside a project. This repository tracks all changes made to files in your project, building a history over time.

### Commit
A commit represents a specific point in the project's history. It contains information about the changes made, when they were made, and by whom.

### Branch
A branch is a lightweight movable pointer to a commit. Branches allow you to develop features isolated from each other.

### Remote
A remote is a common repository that all team members use to exchange their changes. In most cases, it's stored on a code hosting service like GitHub or GitLab.

## Basic Commands

### Initialization
To create a new Git repository:
```
git init
```

### Cloning
To create a local copy of a remote repository:
```
git clone <repository-url>
```

### Staging Changes
To stage changes for commit:
```
git add <file-name>
```
To stage all changes:
```
git add .
```

### Committing Changes
To commit staged changes:
```
git commit -m "Commit message"
```

### Pushing Changes
To push local commits to a remote repository:
```
git push origin <branch-name>
```

### Pulling Changes
To fetch and merge changes from a remote repository:
```
git pull origin <branch-name>
```

## Branching and Merging

### Creating a New Branch
```
git branch <branch-name>
```

### Switching Branches
```
git checkout <branch-name>
```
Or, to create and switch in one command:
```
git checkout -b <branch-name>
```

### Merging Branches
To merge changes from another branch into the current branch:
```
git merge <branch-name>
```

## Advanced Git Concepts

### Rebasing
Rebasing is the process of moving or combining a sequence of commits to a new base commit. It's an alternative to merging:
```
git rebase <base>
```

### Cherry-Picking
Cherry-picking in Git means to choose a commit from one branch and apply it onto another:
```
git cherry-pick <commit-hash>
```

### Stashing
Stashing takes the dirty state of your working directory and saves it on a stack of unfinished changes that you can reapply at any time:
```
git stash
git stash pop
```

## Git Workflow

A typical Git workflow might look like this:

1. Create a new feature branch: `git checkout -b new-feature`
2. Make changes and stage them: `git add .`
3. Commit changes: `git commit -m "Add new feature"`
4. Push branch to remote: `git push origin new-feature`
5. Create a pull request on GitHub/GitLab
6. After review, merge the pull request
7. Pull the changes to your local main branch: `git pull origin main`

## Best Practices

1. Write clear, concise commit messages
2. Commit early and often
3. Use branches for new features or bug fixes
4. Keep your main/master branch stable
5. Regularly pull changes from the remote repository
6. Use .gitignore to exclude files from version control
7. Review your changes before committing

## Resolving Conflicts

When Git can't automatically merge changes, you need to resolve conflicts manually:

1. Git will mark the conflicting areas in the files
2. Manually edit the files to resolve the conflicts
3. Stage the resolved files: `git add <resolved-file>`
4. Commit the changes: `git commit -m "Resolve merge conflict"`

## Git Hooks

Git hooks are scripts that Git executes before or after events such as: commit, push, and receive. They can be used to enforce certain workflows or policies.

Common hooks include:
- pre-commit: Run tests before allowing a commit
- post-receive: Notify team members of a push to the repository

## Git Large File Storage (LFS)

Git LFS is an extension that replaces large files with text pointers inside Git, while storing the file contents on a remote server:
```
git lfs install
git lfs track "*.psd"
```

