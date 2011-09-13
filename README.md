# Git Spaces

Git spaces gives you as many workspaces as you want on a single Git repository. This can help when you need to work with multi branches, on and off, concurrently throughout the day. Naturally, it kinda sucks to have to be so all over the place, and juggling branches, but sometimes there's really no way around it. That's why I made git spaces. To be able to focus on a single task at hand while being pulled in mutiple directions.

Git spaces allows you to easily set up a git workspace to contain a series of linked wrokspaces within the directories below.

To setup git repository for the first time...

    git spaces init

Which will turn this

    project/                  project/
      .git/   ➔ into this ➔    .spaces/
      *                           master/
                                   .git/
                                   *

The splate indicates that everything under project will be saftly moved into master/ space along with the .git/ folder.

You'll notice a new folder .spaces/ has been created. This contains the main repo. The .git/ folder is specially linked to the .spaces/ directory to allow the space to update branches, make commits and push and pull source for the entire repo, while it also maintains it's own state for controlling which branch it's on, which files it has checked out and so on.

You can still stash, and switch branches like you could before, but now you can have any number of workspaces for scratch work, running multiple versions, reference or whatever.

To create a new space, simply enter the **project directory** (Formally your git working directory) and run the `git spaces create  <name>` command.

    $ ls
    master
    $ git spaces create my_space
    Initialized empty Git repository in /Users/blake/Projects/spaces_example/my_space/.git/
HEAD is now at c3b8baa Initial commit
    $ ls
    master my_space

When you're finish with a space, commit any remaining changes and remove the **workspace** (**workspace** refers the actual git workspaces, which now show up as subdirectories independent of the project directory). You can do this using `rm -rf`. Your changes will remain intact and avaible in all other spaces you've created or will create.

## Installation

### Clone / Tarball:

Download the latest tarball from the link at the top right of the git hub page or clone the repo.

    $ git clone git@github.com:blakefrost/git-spaces.git

Finally, run `make install` from within the directory

     $ make install

You can uninstall at anytime, if need be, with `make uninstall`.

## Usage

    $ git spaces init           # Intiailize a git repository for spaces. Moves everything 
                                  you're currently working on into master/

    $ git spaces create <name>  # Creates a new workspace AKA. "space"

