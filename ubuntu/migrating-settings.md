# Migrating Settings

## Aptik NG \(Backup Software\)

> [Aptik NG](https://github.com/teejee2008/aptik) is a tool for **migrating settings and data** from one Linux installation to another. It can be used while re-installing the operating system, and when moving to next release of a Linux distribution.  [User Manuel](https://github.com/teejee2008/aptik/blob/master/MANUAL.md)

> **Backup**
>
> Usage: `sudo aptik --backup-all`
>
> This will backup all items listed in the sections below. Backups are saved in current directory unless `--basepath <path>` is specified.
>
> **Restore**
>
> Usage: `sudo aptik --restore-all`
>
> This will restore all items listed in the sections below. Backups are restored from current directory unless `--basepath <path>` is specified.
>
> **Remove**
>
> Usage: `sudo aptik --remove-all`
>
> This will remove all backups in backup folder that were created by Aptik.
>
> Backups are saved and restored from current working directory unless `--basepath <path>` is specified.

