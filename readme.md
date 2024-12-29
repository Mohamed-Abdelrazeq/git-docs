# Git Commands Documentation

## 1. git init
Initializes a new Git repository.

```sh
git init
```

**Output:**
```
Initialized empty Git repository in /path/to/repo/.git/
```

## 2. git clone
Clones a repository into a newly created directory.

```sh
git clone https://github.com/user/repo.git
```

**Output:**
```
Cloning into 'repo'...
remote: Counting objects: 100% (X/Y), done.
remote: Compressing objects: 100% (X/Y), done.
Receiving objects: 100% (X/Y), done.
```

## 3. git add
Adds file contents to the index (staging area).

```sh
git add filename
```

## 4. git commit
Records changes to the repository.

```sh
git commit -m "Commit message"
```

**Output:**
```
[branch-name commit-hash] Commit message
 X files changed, Y insertions(+), Z deletions(-)
```

## 5. git status
Displays the state of the working directory and the staging area.

```sh
git status
```

**Output:**
```
On branch branch-name
Your branch is up to date with 'origin/branch-name'.

Changes to be committed:
    (use "git reset HEAD <file>..." to unstage)
        modified:   filename

Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
        modified:   filename
```

## 6. git push
Updates remote refs along with associated objects.

```sh
git push origin branch-name
```

**Output:**
```
Enumerating objects: X, done.
Counting objects: 100% (X/Y), done.
Delta compression using up to Z threads
Compressing objects: 100% (X/Y), done.
Writing objects: 100% (X/Y), done.
Total X (delta Y), reused Z (delta W)
To https://github.com/user/repo.git
     old-commit-hash..new-commit-hash  branch-name -> branch-name
```

## 7. git pull
Fetches from and integrates with another repository or a local branch.

```sh
git pull origin branch-name
```

### Rebase instead of merge:
```sh
git pull --rebase origin branch-name
```

**Output:**
```
remote: Enumerating objects: X, done.
remote: Counting objects: 100% (X/Y), done.
remote: Compressing objects: 100% (X/Y), done.
Receiving objects: 100% (X/Y), done.
From https://github.com/user/repo
 * branch            branch-name -> FETCH_HEAD
Successfully rebased and updated refs/heads/branch-name.
```

**Output:**
```
remote: Enumerating objects: X, done.
remote: Counting objects: 100% (X/Y), done.
remote: Compressing objects: 100% (X/Y), done.
Receiving objects: 100% (X/Y), done.
From https://github.com/user/repo
 * branch            branch-name -> FETCH_HEAD
Updating old-commit-hash..new-commit-hash
Fast-forward
 filename | X insertions(+), Y deletions(-)
```

## 8. git branch
Lists, creates, or deletes branches.

### List branches:
```sh
git branch
```

**Output:**
```
* branch-name
    another-branch
```

### Create a new branch:
```sh
git branch new-branch
```

### Delete a branch:
```sh
git branch -d branch-name
```

**Output:**
```
Deleted branch branch-name (was commit-hash).
```

## 9. git merge
Joins two or more development histories together.

```sh
git merge branch-name
```

**Output:**
```
Updating old-commit-hash..new-commit-hash
Fast-forward
 filename | X insertions(+), Y deletions(-)
```

## 10. git log
Shows the commit logs.

```sh
git log
```

**Output:**
```
commit commit-hash
Author: Author Name <email@example.com>
Date:   Date

        Commit message

commit commit-hash
Author: Author Name <email@example.com>
Date:   Date

        Commit message
```
