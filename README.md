Useful Git Tidbits
==================

## Git ##

### Temporarily Ignore a file ###
`git update-index --assume-unchanged path/to/file`

then undo:

`git update-index --no-assume-unchanged path/to/file`


### Change file mode for git on Windows ###
`git update-index --chmod=+x file`
