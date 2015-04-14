#Git Reset

###TO TAKE THINGS OUT OF THE STAGING AREA
__EG.__ `$ git reset HEAD resources.html`

This is used when we want to take the last add from the staging area. This is different from checkout in that it does not effect the file system. EG:

	Garys-MacBook-Pro:explore_california garyswift$ git status
	On branch master
	Changes not staged for commit:
	  (use "git add <file>..." to update what will be committed)
	  (use "git checkout -- <file>..." to discard changes in working directory)
	
		modified:   resources.html
	
	no changes added to commit (use "git add" and/or "git commit -a")
	Garys-MacBook-Pro:explore_california garyswift$ git add resources.html
	Garys-MacBook-Pro:explore_california garyswift$ git status
	On branch master
	Changes to be committed:
	  (use "git reset HEAD <file>..." to unstage)
	
		modified:   resources.html
	
	Garys-MacBook-Pro:explore_california garyswift$ git reset HEAD resources.html
	Unstaged changes after reset:
	M	resources.html
	Garys-MacBook-Pro:explore_california garyswift$

