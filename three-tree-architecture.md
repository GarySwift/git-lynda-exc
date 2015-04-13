#Git Three-Tree Architecture

Git has taken the programming community by storm. Hundreds of thousands of organizations and developers is starting  to use Git as their Version Control System (VCS).  But you might wonder what makes Git so special?

In this post, I’ll going to dig into one of the mysterious aspect of Git — The 3-Tree Architecture.

To get started with, lets  first take a look at how the typical VCS works. Usually, a VCS works by having two places to store things:

1. Working Copy
2. Repository

__Working copy__ is the place where you make your changes. Whenever you edit something, it is saved in working copy and it is a physically stored in a disk.

__Repository__ is the place where all the version of the files or  commits,  logs etc is stored. It is also saved in a disk and has its own set of files.

You cannot however change or get the files  in a repository directly, in able to retrieve a specific file from there, you have to checkout  

__Checking-out__ is the process of getting files from repository to your working copy.  This is because you can only edit files when it is on your working copy. When you are done editing the file, you will save it back to the repository by commiting it.

__Committing__ is the process of putting back the files from working copy to repository.

![Image](http://www.darwinbiler.com/wp-content/uploads/2014/02/2-tree-New-Page.jpeg)

In this process, Working Copy and  Repository is saved in the disk as series of folders and files like a Tree, since files and directories resembles a tree wherein folder represents a branch of a tree and files represents the leaf. Hence, this architecture is called 2 Tree Architecture. Because you have two tree in there — Working Copy and Repository. The famous VCS with this kind of architecture is Subversion or SVN.

Now, that you know what a 2 Tree Architecture looks like, interesting to say Git has different one, it is instead powered by 3 Trees!

Why three you might ask?

Well, interestingly, Git has also the Working Copy and Repository as well, but it had added an extra tree in between:

![Image](http://www.darwinbiler.com/wp-content/uploads/2014/02/3-tree.jpeg)

As you can see above, there is a new tree called Staging. What this is for?

This is one of the fundamental difference of Git that sets it apart from other VCS, this Staging tree (usually termed as Staging area) is a place where you prepare all the things that you are going to commit.

In Git, you don’t move things directly from your working copy to the repository, you have to stage them first, one of the main benefits of this is, lets say:

You did changes on your 10 files, 2 of the files is something related to fixing an alignment issue in a webpage, while the other 8 changed files is related to database connection..

In 2 Tree architecture, you will commit all those 10 files in a single commit message. Probably you will commit it with this message:

“Had fixed the logo and database connection issue”

Well, the problem with that is, the commit deals with 2 different things:

 Logo fix
 Database connection
So what?  you might say

Well, it might be ok at the first glance, but in a real scenario, this simple things could lead in a disastrous consequence.

Consider after several month, the fix on the logo was requested to be undone for some reason. The first thing you might do is go back to that commit and revert it.

Now the problem is this — the only thing you want to revert it the logo related changes, but apparently, the database-related fixes was also reverted back!

Now, the problem comes up and you have to re-apply the database related changes.

You might say that its not that big of an issue since you cant just manually redo the change, but imagine this thing happening in a large scale codebase with hundreds of codes with 50 programmers working, that is a nightmare!

This problem can be avoided by putting the staging between the working copy and repository. This is how, when you edited the 10 files, you will add the 10 files in the staging area, then selectively commit only the 2 files related to logo fixes, then commit it to repository with a message.

“logo fixes”

Remember that even though you had committed the 2 files, the other 8 files is still in staging area. You then commit the other 8 files with the message:

“database connection fixes”

Now, all the changes is moved from Staging to the repository and they are clearly seperated by 2 commits. When the time needs that you need to revert the “logo fixes commit”, you are sure that the “database connection fixes” will not gonna be unintentionally reverted back as well.

There is many other uses of the Staging area aside from this, but this is the concept behind why Git is using this 3 Tree architecture.

__Source:__ <http://www.darwinbiler.com/understanding-the-3-tree-architecture-of-git/>