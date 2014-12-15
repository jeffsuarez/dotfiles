jeffsuarez dotfiles (based on thoughtbot dotfiles)
===================

Requirements
------------

Set zsh as your login shell.

    chsh -s /bin/zsh

Install
-------

First, [fork this repo](/jeffsuarez/dotfiles#fork_box) on Github.

Then, clone your Github fork onto your machine and install it:

    git clone git@github.com:your-github-name/dotfiles.git
    cd dotfiles
    ./install.sh

This will create symlinks for config files in your home directory. If you
include the line "DO NOT EDIT BELOW THIS LINE" anywhere in a config file, it
will copy that file over instead of symlinking it, and it will leave
everything above that line in your local config intact.

You can safely run `./install.sh` multiple times to update.


Why fork?
---------

You should be able to experiment with your own dotfiles, save them in version
control, and still get updates from `jeffsuarez/dotfiles`.

The `master` branch is for your customizations and the `upstream` branch is for
jeff's updates.

Set up the upstream branch
--------------------------

You only have to do this once:

    git remote add upstream git@github.com:jeffsuarez/dotfiles.git
    git fetch upstream
    git checkout -b upstream upstream/master

Make your own customizations
----------------------------

Put your customizations at the top of files, separated by "DO NOT EDIT BELOW
THIS LINE."

For example, the top of your `~/.gitconfig` might look like this:

    [user]
      name = Bob Smith
      email = bsmith@example.com

    # DO NOT EDIT BELOW THIS LINE

    [push]
      default = current

The top of your `~/.zlogin` might look like this:

    # RVM
    [[ -s '/Users/ball/.rvm/scripts/rvm' ]] && source '/Users/ball/.rvm/scripts/rvm'

    # DO NOT EDIT BELOW THIS LINE

    # recommended by brew doctor
    export PATH="/usr/local/bin:/usr/local/sbin:$PATH"

Get jeff's updates
------------------------

Each time you want to include thoughtbot's changes:

    git checkout upstream
    git pull
    git checkout master
    git rebase upstream


Notes
-------

Dotfiles is maintained by Jeff Suarez and is based on the dotfiles maintained by [thoughtbot](https://github.com/thoughtbot/dotfiles).

This is free software and may be redistributed under the terms specified in the MIT-LICENSE file.