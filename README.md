# Git Spaces

Git spaces gives you as many workspaces as you want for working with a single Git repository. This can help when you need to work with multi branches on and off concurrently throughout the day. Naturally, it kinda sucks to have to be so all over the place and juggling branches, but sometimes there's really no way around it. That's why I made git spaces, that's why I made git spaces. To be able to focus on a single task at hand while being pulled in mutiple directions.

Git spaces allows you to easily set up a git workspace to contain a series of linked wrokspaces within the directories below.

To setup git repository for the first time...

    git spaces init

Which will turn this

    project/                  project/
      .git/   ➔ into this ➔    .spaces/
      *                           master/
                                   .git/
                                   *

The splate indicates that everything under project will be saftly moved into 'master' space along with the .git/ folder.

You'll notice a new folder `.spaces` has been created. This contains the main repo. The .git folder is specially linked to the .spaces directory to allow the space to update branches, make commits and push and pull source for the entire repo, while it also maintains it's own state for controlling which branch it's on, which files are on disk, and in which state.

You can still stash, and switch branches like you could before, but now you can have any number of workspaces for scratch work, running different versions at the same, reference or whatever.

To create a new space, simply enter the 'project directory' (Formally your git working directory) and run the `spaces create` command.

    $ ls
    master
    $ git spaces create my_space
    Initialized empty Git repository in /Users/blake/Projects/spaces_example/my_space/.git/
HEAD is now at c3b8baa Initial commit
    $ ls
    master my_space

When you're finish with a space, commit your changes and remove the 'workspace' (This is the actual git workspace, now a sub directory of the project workspace.) with `rm -rf`. This will remove the working directory and linked repo of the space, but leave the root .space directory intact with all your changes.

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
