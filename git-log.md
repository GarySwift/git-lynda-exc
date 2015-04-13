
#Git Log Notes
###NAME
`git-log` - Show commit logs

###SYNOPSIS
```
'git log' [<options>] [<revision range>] [[\--] <path>...]
```
###DESCRIPTION
Shows the commit logs.

The command takes options applicable to the git rev-list command to control what is shown and how, and options applicable to the git diff-* commands to control how the changes each commit introduces are shown.

###NOTES
You're in the less program, which makes the output of git log scrollable.

Type `q` to exit this screen. Type `h` to get help.

`git log -n 3` will limit the number of returned commits

`git log --since=2015-04-12` will limit the returned commits by given date

`git log --author="Gary"` will filter by author

`git log --grep="init"`, `git log --grep="ticket"` etc, will use regular expressions to filter result


###LINK
<http://git-scm.com/docs/git-log>
<http://stackoverflow.com/questions/9483757/how-to-exit-git-log>
	