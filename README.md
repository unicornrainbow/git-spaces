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

## Acknowledgement

Acknowledgement for base implementation and idea goes to [Dmitry Fink][2] for his post [Multiple working folders with single GIT repository][3].

Additionally, credit must be given to the wonderful [git-extras][1] project from which I took much inspiration and code.

  [1]: https://github.com/visionmedia/git-extras
  [2]: http://twitter.com/finik
  [3]: http://finik.net/2010/10/24/multiple-working-folders-with-single-git-repository/