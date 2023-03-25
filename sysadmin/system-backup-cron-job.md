# System backup cron job

First thing needded for system backup via cron job is script that will check
when the last backup was run because we want to backup daily but run cron
hourly as setting daily cron jobs is unreliable.

```
$ vim ~/.backup.sh
```

Make sure to replace comment with backup command. It can be anything you want,
like [rsync](https://linux.die.net/man/1/rsync), [restic](https://restic.net/)
or even plain old [tar](https://linux.die.net/man/1/tar).

```bash
#!/bin/sh

DATE=$(date +%s)
BACKUP_FILE="$HOME/.last_backup"

if [ ! -f $BACKUP_FILE ]; then
	touch $BACKUP_FILE
	MODIFICATION_DATE=10000000
else
	MODIFICATION_DATE=$(stat -L --format %Y $BACKUP_FILE)
fi

LAST_BACKUP=$(expr $DATE - $MODIFICATION_DATE)
LAST_BACKUP_DAYS=$(expr $LAST_BACKUP / 60 / 60 / 24)
LAST_BACKUP_HOURS=$(expr $LAST_BACKUP / 60 / 60)

echo "$LAST_BACKUP_DAYS days since last backup ($LAST_BACKUP_HOURS hours)"
if [ $LAST_BACKUP_HOURS -ge 24 ]; then
	echo "Time for a new backup!"
	touch $BACKUP_FILE

    # run backup command here
else
	echo "Backup still good..."
fi
```

After saving file in editor, make it executable:

```
$ chmod +x ~/.backup.sh
```

And lastly, add following line to crontab:

```
0 * * * * /home/[your username]/.backup.sh
```

[Script source](https://gist.github.com/adewes/02e8a1f662d100a7ed80627801d0aed0)
