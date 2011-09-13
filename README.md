# Git Spaces

Git spaces gives you as many workspaces as you want on a single Git repository. This can help when you need to work with multi branches, on and off, and concurrently throughout the day. Naturally, it sucks to have to be so all over the place juggling branches, but sometimes there's no way around it. When your time is divided, git spaces can help to focus on a single task at a time.

Git spaces creates workspaces as subdirectories of the project directory. The subdirectories, or **spaces** can easily be navigated as you would a typical directory structure.

Setup git spaces with a git repo for the first time.

    git spaces init

Which will:

                project/                  project/
   turn this ➔    .git/   ➔ into this ➔    .spaces/
                   *                         master/
                                               .git/
                                               *

The splate indicates that everything under project will be saftly moved into master/ space along with the .git/ folder.

You'll notice a new folder, .spaces/, has been created. The .spaces/ directory contains the repo. The .git/ folder, now in master, is configured and linked to the .spaces/ directory. This allows you to continue updating branches, make commits and push and pull source for the entire repo, while keeping track of the branch, local index and working tree for each space individually.

You can still stash, and switch branches like before, but now you can also have any number of workspaces for scratch work, running multiple versions, reference or whatever (wish you can stash on pop on too)

To create a new space, simply enter the **project directory** (formally your git working directory) and run the `git spaces create  <name>` command.

    $ ls
    master
    $ git spaces create my_space
    Initialized empty Git repository in /Users/blake/Projects/spaces_example/my_space/.git/
HEAD is now at c3b8baa Initial commit
    $ ls
    master my_space

When you're finish with a space, commit any remaining changes and remove the **workspace** (workspace refers the actual git workspaces, which now show up as subdirectories independent of the project directory). You can do this using `rm -rf` . Your changes will remain intact and avaible in all other spaces you've created or will create.

**Note:** Always be careful when using `rm -rf`. Sorry, I have to say it.

## Installation

### Clone / Tarball:

Download the latest tarball from the link at the top right of the git hub page or clone the repo.

    $ git clone git@github.com:blakefrost/git-spaces.git

Run `make install` from within the directory

     $ make install

You can uninstall with `make uninstall`.

## Usage

    $ git spaces init           # Intiailize a git repository for spaces. This oves everything
                                  you're currently working on into master/

    $ git spaces create <name>  # Creates a new workspace AKA. "space"

## Reporting Issues

If you find somthing wrong please open up an issue on [git issues](https://github.com/blakefrost/git-spaces/issues).

