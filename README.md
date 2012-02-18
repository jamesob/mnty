# mnty

SSHFS is awesome, but typing out its cumbersome command isn't. Especially when
you have a bunch of different remote projects you're working on.

So here's mnty, a utility for managing sshfs mount profiles.

## Using

    usage: mnty [-h] [--init] [-m] [-u] [profile_name]

    A tiny convenience for managing sshfs mount profiles.

    positional arguments:
      profile_name   The mount profile to act on.

    optional arguments:
      -h, --help     show this help message and exit
      --init         Initialize a skeleton config file.
      -m, --mount    Mount the sshfs drive.
      -u, --unmount  Unmount the sshfs drive.

## Installing

1. Clone this repo.
2. Symlink `mnty` to somewhere in your path.
3. Run `mnty --init` to initialize a config file at `$HOME/.mnty`.
4. Modify the config file. It may look something like this:

```javascript
{
  "default_remote_user": "jobeirne", 
  "sshfs_options": "-o reconnect", 
  "mount_profiles": {
    "kali": {
      "mountpoint": "~/mnt/kali", 
      "remote_dir": "dev1.company.com:code/kali"
    },
    "foia": {
      "mountpoint": "~/mnt/foia", 
      "remote_dir": "dev1.company.com:code/foia"
    }
  }
}
```

5. Mount and unmount with `mnty -m foia` or `mnty -u foia`.

