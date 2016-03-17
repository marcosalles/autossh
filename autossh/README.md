# autossh

If you are lazy and don't want to type the whole `ssh` or `scp` commands over and over again, you'll love this.

If you don't wish to use the default `~/ssh_hosts_list` hosts file, export the variable `AUTOSSH_REMOTE_HOSTS` on your `.profile` or equivalent pointing to your custom hosts file.

Examples of use:

- `autossh` prompts to connect to any of your registered remote hosts.
- `autossh -e` edits your remote hosts file, creating a sample if not existent.
- `autossh -x -r 3` or `autossh -x -r3` connects you to the third remote available, sorted alphabetically, from your hosts file.
- `autossh -xr1 -d. /absolute/path/files*` downloads all files matching the pattern `/absolute/path/files*` from your registered remote #1 to the current working directory, showing the `scp` command that will be executed beforehand.
- `autossh -r1 -u /absolute/remote/path/ /absolute/path/files* relative/path/files*` uploads all files matching the patterns `/absolute/path/files*` and `relative/path/files*` from your local computer to the `/absolute/remote/path/` directory on your registered remote host #2.
- `autossh -xc50 -d relative/destination/path /absolute/path/files* relative/path/files*` downloads all files matching the patterns `/absolute/path/files*` and `relative/path/files*` from your registered remote #1 to the `relative/destination/path` directory, showing the `scp` command that will be executed beforehand.

PS.: requires bash 4+, because of associative arrays. I will be removing this in the near future.
