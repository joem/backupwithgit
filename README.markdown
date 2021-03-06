backupwithgit
=============

This progam lets you easily set up a quick method to backup a dir using `git`.

(NOTE: This script should not be used for any serious endeavors like
programming. Use `git` proper for such things, so that you can have better
control over everything, especially commit messages.)

For instance, if I want to backup my `~/.dotfiles` directory, I can simply type
`backupdot`. This will:

 - cd `~/.dotfiles`
 - `git add .`
 - `git commit -m "automatically commited by backupdot"`
 - cd back to dir I was in

It has some error handling (checks for existance of dir, checks to make sure
dir is a `git` repo), and it can accept some arguments.

Usage
-----

`${PROGNAME} [ARGUMENT] [COMMIT_MESSAGE]`

To add a directory, edit the portion of `backupwithgit` that begins with the
line `case "$PROGNAME" in`. Here, you'll want to follow suit and add a new
symlink handler, which you can customize the directory and a few behavior
flags. Then, you'll want to actually make the symlink to `backupwithgit`
(`ln -s backupwithgit your_new_symlink`). Test out your new symlink by using
`your_new_symlink -?` to see if the help works.


Arguments
---------

    help, -h, -?, --help
        Display a brief help text

    push, -p, --push
        Push commit to the repo specified in the script

    status, st, -s, --status
        Display the backup status of dir (as in running 'git status')

    Any other arguments (or arguments following one of the push arguments) are
    used as the commit message. This way, you can type 'backupdot major vimrc
    changes' to do the normal 'backupdot' operations but use 'major vimrc
    changes' as the commit message instead of the default 'automatically
    commited by backupdot'.


Required external programs
--------------------------

  - bash (probably won't work in other shells without some modifications)
  - git (for obvious reasons)


To Do
-----

  - ?




