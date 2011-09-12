# Git Spaces

Multiple workspaces for git.

## Installation

Clone / Tarball:

     $ make install

## Usage

    $ git spaces init

    $ git spaces create some-feature

## Note

The `init` command will move everything intto the `master` subdirectory which may serve as your new main working directory should you choose.

Upon creation, new spaces will automatically be initialized to the master branch. Once created, enter the directory and checkout the desirde branch.

When you are done with a space, you can remove it by exiting the space directory and removeing it with `rm -rf`. Note that this will permanently remove the space, so be sure to commit any work you plan on keeping before doings so.
