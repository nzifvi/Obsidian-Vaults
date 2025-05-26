[[1,3) Creating  a Repository]] <- Back

---
## Tracking Files Commits
The status of a program's git can be displayed by...
```git
git status
```
- NOTE: git init must have been run, in the directory, before checking status.

This will show...
```terminal output
file path
the branch

the commits made.

untracked files
```
- file path is the file path of the current repo.
- branch is the current parallel line of the git tree being accessed.
- the commits are how many updates the repository has received.
- untracked files mention how many files, in the directory, are untracked by git.
	- NOTE: if a file is untracked, it will not be added to the repository upon committing.

## Adding Files to Repository 
The files added to a repository are the ones that will be committed per commit.

To add a file, do...
```git
git add fileName.fileExtension
```

Instead of committing files one by one, all untracked files in a directory can be added to the git.

```git
git add ./
```
- the dot, instead of the name, specifies all within the directory.
- slash specifies directory.

## Committing 
Committing in git allows for the current state of the files, added to the repository: creating a copy of the program.
- For each commit, a version of those files will be created.
- Allows for multiple versions, over time, to be added to repository.

Regular commits allow for...
1) Progress to be tracked.
2) Reverts to previous version to be made IF required.
		Without committing a version, you cannot revert to it.

To commit...
```git
git commit -m 'commit message'
```
- -m stands for message, allowing a message to be added to the commit.


## Git Log
When committing, a log is created. It displays the...
- A commit hash, a way to identify the given commit in the repository.
- Username of the one who committed to the branch.
- Email of the one who committed to the branch.+
- Time of commit
- Comments made for the commit.
For all commits

```git
git log
```

## Reverting to Previous Commit
A program can be reverted to a previous commit in the event the current state of the program does not work or for any other reason.

```git
git checkout commitHashCode
```


The checkout changes the head of the git branch to the commit the hash code.
- You will get a detached head warning.
- Detached head warning = the new head, the node in the git branch reverted to, no longer points to whatever commits were made after it.
- The files are not deleted, they are somewhere.
- A branch off the current head can be made to store all of the commits that are detached from the new head.

Takeaway 1) checkout does not delete commits made after the version that has been reverted to.