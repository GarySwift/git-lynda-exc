###Notes
Let's stage and commit all the changes to our `hello.rb` file. In this first example, we'll use the -m option to provide the commit message on the command line.

	$ git add hello.rb 
	$ git status -s
	M  hello.rb
	$ git commit -m 'my hola mundo changes'
	[master 68aa034] my hola mundo changes
	 1 files changed, 2 insertions(+), 1 deletions(-)

Now we have recorded the snapshot. If we run `git status ` again, we will see that we have a "clean working directory", which means that we have not made any changes since our last commit - there is no un-snapshotted work in our checkout.

	$ git status
	On branch master
	nothing to commit (working directory clean)	 
If you leave off the `-m` option, Git will try to open a text editor for you to write your commit message. 

__Shortcut:__

	$ git commit -a -m "Changed 24hr support number to 866.555.4314"
	
In the example above we we skipped the git add command by adding `-a`. Be carefull as this will add everything to to the stage.

### Commit Message Best Practice

* short single-line summary (less than 50 characters)
* optionally followed by a blank line and a more coomplete description
* keep each line to less than 72 characters
* write commit messages in present tense ("fix bug" or "fixes bug" not "fixed bug")
* bullet points are usually astericks or hyphens
* be clear and descriptive
    - bad "Fix "
    - good "Add missing > in index.html"
    - bad "Update login Code"
    - good "Change user authentication to use Blowfish"

###Good Example
```
Fixed bug where user can't signup.

Users were unable to register if they hadn't visited the plans
and pricing page because we expected that tracking
information to exist for the logs we create after a user
signs up.  I fixed this by adding a check to the logger
to ensure that if that information was not available
we weren't trying to write it.

[Fixes #2873942]
```

###Amending the commit message

`git commit --amend`

Will open your editor, allowing you to change the commit message of the most recent commit. Additionally, you can set the commit message directly in the command line with:

`git commit --amend -m "New commit message"`

…however, this can make multi-line commit messages or small corrections more cumbersome to enter.

Make sure you don't have any working copy changes before doing this or they can get committed too.

Changing the message of a commit that you've already pushed to your remote branch

If you've already pushed your commit up to your remote branch, then you'll need to force push the commit with

```git push <remote> <branch> --force```

Or

```git push <remote> <branch> -f```

__Warning:__ force-pushing will overwrite the remote branch with the state of your local one. If there are commits on the remote branch that you don't have in your local branch, you will lose those commits.

__Warning:__ be cautious about amending commits that you have already shared with other people. Amending commits essentially rewrites them to have different SHA IDs, which poses a problem if other people have copies of the old commit that you've rewritten. Anyone who has a copy of the old commit will need to re-synchronize their work with your newly re-written commit, which can sometimes be difficult, so make sure you coordinate with others when attempting to rewrite shared commit history, or just avoid rewriting shared commits altogether.

####Documentation

<https://www.kernel.org/pub/software/scm/git/docs/git-commit.html>

<http://stackoverflow.com/questions/179123/edit-an-incorrect-commit-message-in-git>

