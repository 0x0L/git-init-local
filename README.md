git-init-local
==============
Create a local bare Git repository on your hard drive and set it up as
a remote to the current Git repository.

This is useful for quickly setting up private Git repositories on
Google Drive, Dropbox or similar systems based on folder synchronization.

Configuration
-------------
By default, repositories will be created in `~/Google Drive/git`. Edit the
value of the variable `REMOTE_ROOT` at the top of the script to suit
your needs.

Usage
-----
    git init-local [-h] [-p PATH] [NAME]
        -h          Display help.
        -p PATH     Remote repository will be created under $REMOTE_ROOT/PATH.
        NAME        Customize remote name (default=origin).

To clone an existing repository

    git clone file:///Users/USER/Google\ Drive/git/myrepo

In your `~/.gitconfig` file, you can setup an alias for `REMOTE_ROOT`

    [url "file:///Users/USER/Google Drive/git/"]
        insteadOf = "local:"

After adding these lines, you can clone a repository using

    git clone local:myrepo
