# Git Tutorial

Welcome to the Git tutorial! This guide will help you understand Git and use it effectively in your projects.

## Table of Contents
- [What is Git?](#what-is-git)
- [Why Use Git?](#why-use-git)
- [Prerequisites](#prerequisites)
- [Installing Git](#installing-git)
- [Understanding Git Concepts](#understanding-git-concepts)
- [Usual Git Workflow](#usual-git-workflow)
- [Professional Git Workflow](#professional-git-workflow)
- [Branching and Merging](#branching-and-merging)
- [Undoing Changes](#undoing-changes)
- [Working with Remotes](#working-with-remotes)
- [Handling Merge Conflicts](#handling-merge-conflicts)
- [Advanced Git](#advanced-git)

---

## What is Git?
Git is a **version control system** that helps developers track changes in their code. It allows you to create **snapshots** of your project, work with **branches**, and synchronize changes with **remote repositories**.

Instead of saving files with names like `version1`, `version2`, or `final_version`, Git helps you organize your source code efficiently, enabling collaboration without blocking other contributors.

## Why Use Git?
- **Track changes**: Git lets you save different versions of your code and revert if needed.
- **Collaborate seamlessly**: Multiple developers can work on the same project without overwriting each other’s work.
- **Experiment safely**: Create separate branches to test features before merging them into the main project.
- **Backup your code**: Pushing code to a remote repository ensures that your work is not lost.

---

## Prerequisites
Before diving into Git, having basic command-line knowledge is helpful. If you're new to the command line, here are some helpful resources:

- [Learn the Command Line (Codecademy)](https://www.codecademy.com/learn/learn-the-command-line)
- [Command Line Crash Course (Learn Enough)](https://www.learnenough.com/command-line-tutorial)
- [Linux Command Line Basics (edX)](https://www.edx.org/course/introduction-to-linux)

---

## Installing Git
To install Git, follow these instructions:
- **Windows**: Download and install Git from [git-scm.com](https://git-scm.com/).
- **Mac**: Install via Homebrew:
  ```sh
  brew install git
  ```
- **Linux**: Install via package manager:
  ```sh
  sudo apt install git  # Debian/Ubuntu
  sudo dnf install git  # Fedora
  ```

Verify installation:
```sh
git --version
```

---

## Understanding Git Concepts
### Repositories
A repository (repo) is a folder for your project that contains all your files and their history. Git tracks changes inside the repository.
```sh
git init  # Creates a new local repository
```

### Staging Area
The staging area is an intermediary step between your working directory (where you make changes) and the repository (where changes are permanently saved). It allows you to select which changes to include in your next commit.
```sh
git add file1.txt file2.txt  # Add specific files
git add .  # Add all changes in the current directory
```

### Commits
A commit is a snapshot of your project at a certain point. Each commit should include a descriptive message explaining the changes.
```sh
git commit -m "Describe your changes"
```

### Branches
A branch is like a separate workspace where you can work on new features without affecting the main project.
```sh
git branch feature-branch  # Create a new branch
git switch feature-branch  # Switch to the new branch
```

### HEAD
`HEAD` is a pointer representing your current working state. It usually points to the latest commit of the checked-out branch. 
Intuition think you are writing a book with a friend. Pointers is like bookmarks, whenever you use it you end up in a particular page. The bookmark `head` always points to the last page of the book you are working with. So you have a book version, your colleague has another one, and you also have a validated version. If you are working on your version we say you are workin on your branch, if you call the bookmark head, you end up on the last page of your version. If you switch to your friends version, head is going to point to your friend's last page and the same happens in the validated version. The bookmark `head` helps us manage the changes on each version.
```sh
cat .git/HEAD  # Check where HEAD is pointing
```

### Remote Repository
A remote repository is a copy of your project stored on a server, allowing collaboration with others. Platforms like GitHub, GitLab, and Bitbucket host remote repositories.
```sh
git remote add origin <repository-url>
```

---

## Usual Git Workflow (Barebones)
1. **Initialize a repository**
   ```sh
   git init
   ```
2. **Check repository status**
   ```sh
   git status
   ```
3. **Stage changes**
   ```sh
   git add <filename>
   ```
4. **Commit changes**
   ```sh
   git commit -m "Your commit message"
   ```
5. **Push changes to a remote repository**
   ```sh
   git push origin main
   ```
6. **Pull latest changes**
   ```sh
   git pull origin main
   ```

---

## Professional Git Workflow
1. **Clone a remote repository**
   ```sh
   git clone <repository-url>
   ```
2. **Create a feature branch**
   ```sh
   git checkout -b feature-branch
   ```
3. **Work on the feature and commit regularly**
   ```sh
   git add .
   git commit -m "Add initial implementation of feature"
   ```
4. **Rebase with the latest changes from main**
   ```sh
   git fetch origin
   git rebase origin/main
   ```
5. **Push the branch to the remote repository**
   ```sh
   git push origin feature-branch
   ```
6. **Create a pull request (PR) and request a review**
7. **Merge the PR once approved**
8. **Delete the feature branch**
   ```sh
   git branch -d feature-branch
   git push origin --delete feature-branch
   ```

---

## Undoing Changes
- **Undo changes before staging**:
  ```sh
  git checkout -- <filename>
  ```
- **Unstage a file**:
  ```sh
  git reset HEAD <filename>
  ```
- **Undo the last commit**:
  ```sh
  git reset --soft HEAD~1
  ```

---

## Handling Merge Conflicts
If you encounter a conflict while merging:
1. Open the conflicting file and resolve the conflicts.
2. Stage the resolved file:
   ```sh
   git add <filename>
   ```
3. Complete the merge:
   ```sh
   git commit -m "Resolved merge conflict"
   ```

---

## Advanced Git
- **Interactive rebase**:
  ```sh
  git rebase -i HEAD~3
  ```
- **Cherry-picking commits**:
  ```sh
  git cherry-pick <commit-hash>
  ```
- **Using Git hooks for automation**:
  ```sh
  .git/hooks/pre-commit
  ```

---

## Conclusion
This guide covers the fundamentals of Git. To master Git, keep practicing and explore more advanced concepts.

Happy coding! 🚀

