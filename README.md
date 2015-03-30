# clonebak
clone local repositories to a backup location

you know, so when your hard disk dies on you, you don't lose all the
stuff you haven't yet pushed upstream

run me out of cron, like:

    ... $HOME/bin/clonebak ~/projects /mnt/backup/clonebak

each time it is run, it will create a timestamped directory under
/mnt/backups/clonebak containing tarballed clones of the git repositories
under your projects directory (one tarball per repo)

the cloning and gzipping takes place under /var/tmp/clonebak (or wherever
else you specify), which means:

* you've also got copies on (probably) the same (fast) storage as your main
  storage, which might make recovering from non-device-destroying problems
  faster (until you clean them up)
* you'll need to clean out /var/tmp/clonebak periodically
* you can use a usb flash drive for your final storage and not have to worry
  about the clone/archive/compress cycle wearing out the flash prematurely
