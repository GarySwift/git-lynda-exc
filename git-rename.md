#Git Renaming
A good way to handle renaming with git is to use the unix move command like follows:

	$ git mv tours/tour_detail_backpack.html tours/tour_detail_backpack_cal.html
	
This will rename the file is OS file system and the git staging area.

	$ git status
	On branch master
	Changes to be committed:
	  (use "git reset HEAD <file>..." to unstage)
	
		renamed:    tours/tour_detail_backpack.html -> tours/tour_detail_backpack_cal.html
	
	Garys-MacBook-Pro:explore_california garyswift$
	
Another way to rename is do this is to do directly in the file system. Eg, a search and replace in project in Sublime Text. However, this mean that there are discrepencies with the working copy and the staging area as the example below shows:

	$ git status
	On branch master
	Changes to be committed:
	  (use "git reset HEAD <file>..." to unstage)
	
		renamed:    tours/tour_detail_backpack.html -> tours/tour_detail_backpack_cal.html
	
	Changes not staged for commit:
	  (use "git add <file>..." to update what will be committed)
	  (use "git checkout -- <file>..." to discard changes in working directory)
	
		modified:   tours.html
		modified:   tours/tour_detail_backpack_cal.html
		modified:   tours/tour_detail_bigsur.html
		
In this scenario, we also then need to add the changes to the staging area. Eg:

	$ git add tours.html
	$ git add tours/
	$ git status
	On branch master
	Changes to be committed:
	  (use "git reset HEAD <file>..." to unstage)
	
		modified:   tours.html
		renamed:    tours/tour_detail_backpack.html -> tours/tour_detail_backpack_cal.html
		modified:   tours/tour_detail_bigsur.html