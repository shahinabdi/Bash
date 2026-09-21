# Build Real Linux Tools With Bash

Three standalone projects intended to be recreated in a Linux terminal during a live-coding video:

- `disk-doctor`: interactive disk investigation menu.
- `backup-it`: timestamped `.tar.gz` snapshots with list and restore commands.
- `linux-watch`: live system dashboard built from `/proc` and standard commands.

The `linux-tools` script is an optional final wrapper that makes the three scripts feel like one CLI.

## Run on Linux

```bash
chmod +x disk-doctor backup-it linux-watch linux-tools
./disk-doctor /home
./backup-it ~/Documents
./backup-it --list
./linux-watch --once
./linux-tools watch --interval 5
```

`backup-it` writes snapshots to `~/backups` by default. Set `BACKUP_ROOT` to use another destination:

```bash
BACKUP_ROOT=/mnt/backup ./backup-it ~/Documents
```

These are GNU/Linux scripts. `disk-doctor` relies on GNU `find -printf` and `numfmt`; `linux-watch` reads Linux `/proc` files.