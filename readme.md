# Backush #

Reliably and easily manage several backup locations. Fast, secure, resilient, portable.

## Backup: Example Usage ##

	backush --push server-name-here [ second-server-name-here ... ]

`backush` can also be executed without any server arguments, this will start an interactive mode.

	backush [ --push ]

Push is assumed if no arguments are given.

## Upback: Example Usage ##

Note: Upback is the opposite of backup. It's when you pull from a server instead of push.

	backush --pull server-name-here [ second-server-name-here ... ]

Again, no server arguments will run in interactive mode.

	backush --pull

## Where does it backup from? ##

It uses the current working directory as the source.
The server is listed in the backup-servers file (autogenerated).

## Cleaning ##

Before `./backush --push` uploads, it calls `clean` recursively. Usage: encrypting sensitive data, cleaning up temporaries, compress files.

Perform cleaning without uploading with `./backush --clean`

## Contaminating ##

After `./backush --pull` downloads, it calls `contamine` recursively. Usage: decrypt files, extract files, create temporaries.
Contamine is the antonym of clean.

Perform contamination without downloading with `./backush --contamine`

## Dependencies ##

Dependencies are always checked. To explicitly check without running further use `./backush --check`.
