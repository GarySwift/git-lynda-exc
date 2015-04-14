#Deleting with Git

garyswift$ __git status__

On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   test-files/second.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	file-to-delete-1.txt
	file-to-delete-2.txt

no changes added to commit (use "git add" and/or "git commit -a")


garyswift$ __git add .__

garyswift$ __git status__

On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   file-to-delete-1.txt
	new file:   file-to-delete-2.txt
	modified:   test-files/second.txt

garyswift$ __git commit -m "Add red shirt files"__

[master 6cc9177] Add red shirt files
 3 files changed, 3 insertions(+), 5 deletions(-)
 create mode 100644 file-to-delete-1.txt
 create mode 100644 file-to-delete-2.txt
 rewrite test-files/second.txt (100%)
 
garyswift$ __git status__

On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean

garyswift$ __git status__

On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    file-to-delete-1.txt

no changes added to commit (use "git add" and/or "git commit -a")

