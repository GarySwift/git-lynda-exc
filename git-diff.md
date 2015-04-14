#Git Diff
__NAME__

`git diff` - Show changes between commits, commit and working tree, etc

__SYNOPSIS__

```'git diff' [options] [<commit>] [--] [<path>...]
'git diff' [options] --cached [<commit>] [--] [<path>...]
'git diff' [options] <commit> <commit> [--] [<path>...]
'git diff' [options] <blob> <blob>
'git diff' [options] [--no-index] [--] <path> <path>```

__DESCRIPTION__

Show changes between the working tree and the index or a tree, changes between the index and a tree, changes between two trees, changes between two blob objects, or changes between two files on disk.

__NOTES__

`git diff --staged` If you want to see only changes that have already been added to the Staging Area, "git diff --staged" is your command of choice.

`git diff --color-words contact.html` 

__SOURCE__

<http://git-scm.com/docs/git-diff>

<http://www.git-tower.com/learn/ebook/command-line/advanced-topics/diffs>