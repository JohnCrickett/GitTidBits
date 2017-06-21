Useful Git Tidbits
==================

## Git ##

### Squash changes on a branch and then merge back to master (useful for gerrit) ###
Create a banch to squash on - so if we mess up the squash we can delete it and try again:

`git checkout -b squashed`

`git rebase -i master`

then edit the file that looks like this:

<pre>
pick ef4d325 commit 1
pick d2drf45 commit 2
pick cf45d2a commit 3
</pre>

to:

<pre>
pick ef4d325 commit 1
squash d2drf45 commit 2
squash cf45d2a commit 3`
</pre>

to squash everything into the first commit. Then

`git checkout master`
`git merge squashed_feature`


### Temporarily Ignore a file ###
`git update-index --assume-unchanged path/to/file`

then undo:

`git update-index --no-assume-unchanged path/to/file`


### Change file mode for git on Windows ###
`git update-index --chmod=+x file`

### All files to have LF (Unix) line endings in the repo ###
Add the following to the `.gitattributes` file:

`* text=auto eol=lf`
