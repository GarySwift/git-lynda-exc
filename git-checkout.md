#Git Checkout
Updates files in the working tree to match the version in the index or the specified tree. If no paths are given, git checkout will also update `HEAD` to set the specified branch as the current branch.

__Example:__

	$ git checkout index.html
	
This will return the version of index.html that is in the staged area to the working area. This is especially useful when rectifying mistakes.

__Example:__

	$ $ git checkout -- index.html
		
Use the `--` to make sure we get it from the same branch.

