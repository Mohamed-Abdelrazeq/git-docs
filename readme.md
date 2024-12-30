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


## 11. git rm -r --cached
Removes files from the index (staging area) but keeps them in the working directory.

```sh
git rm -r --cached filename
```

**Output:**
```
rm 'filename'
```

## 12. git stash
Temporarily shelves (or stashes) changes in the working directory that are not ready to be committed.

### Save changes to stash:
```sh
git stash
```

**Output:**
```
Saved working directory and index state WIP on branch-name: commit-hash Commit message
```

### List stashed changes:
```sh
git stash list
```

**Output:**
```
stash@{0}: WIP on branch-name: commit-hash Commit message
stash@{1}: WIP on branch-name: commit-hash Commit message
```

### Apply stashed changes:
```sh
git stash apply
```

**Output:**
```
On branch branch-name
Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
        modified:   filename
```

### Drop a stash:
```sh
git stash drop stash@{0}
```

**Output:**
```
Dropped stash@{0} (commit-hash)
```

### Apply and drop the latest stash:
```sh
git stash pop
```

**Output:**
```
On branch branch-name
Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
        modified:   filename
Dropped stash@{0} (commit-hash)
```

## 13. git reset
Resets current HEAD to the specified state.

### Soft reset (keeps changes in working directory and index):
```sh
git reset --soft commit-hash
```

### Mixed reset (keeps changes in working directory but not in index):
```sh
git reset --mixed commit-hash
```

### Hard reset (discards all changes in working directory and index):
```sh
git reset --hard commit-hash
```

**Output:**
```
HEAD is now at commit-hash Commit message
```

## 14. git commit --amend
Modifies the most recent commit.

### Amend the last commit:
```sh
git commit --amend -m "New commit message"
```

**Output:**
```
[branch-name new-commit-hash] New commit message
 Date: Date
 1 file changed, X insertions(+), Y deletions(-)
```

## 15. git revert
Reverts a commit by creating a new commit that undoes the changes.

### Revert a specific commit:
```sh
git revert commit-hash
```

**Output:**
```
[branch-name new-commit-hash] Revert "Commit message"
 Date: Date
 1 file changed, X insertions(+), Y deletions(-)
```