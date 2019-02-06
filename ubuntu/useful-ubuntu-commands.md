# Useful Ubuntu Commands

## xKill 

`alt + f2`

* `r` - Quick **restart** Ubuntu session

## Diagnose Boot Up Problems

`systemd-analyze blame`- outputs a list of services and how long they took to start in descending order.

## Display/Driver Boot   up Message

`dmesg`

## sudo

> **sudo** \(SuperUser DO\) Linux command allows you to run programs or other commands with administrative privileges, just like “Run as administrator” in Windows. This is useful when, for example, you need to modify files in a directory that your user wouldn’t normally have access to.

## apt-get

> `apt-get` is the one of the most important Ubuntu commands every beginner must know. It is used to install, update, upgrade and remove any package. apt-get basically works on a database of available packages. Here is the list of different apt-get commands:
>
> `sudo apt-get update`
>
> `apt-get update` with super user privileges is the first command you need to run in any Linux system after a fresh install. This command updates the database and let your system know if there are newer packages available or not.

> `sudo apt-get upgrade`
>
> After updating the package database, next step is to to upgrade the installed packages. For upgrading all the packages with available updates you can use this command.

> And if you like to upgrade a particular package, the you should tweak the above command a little:
>
> `sudo apt-get upgrade <package-name>`. Replace the &lt;package-name&gt; with your desired package.
>
> `sudo apt-get install`
>
> If you know the name of the package, then you can easily install a program using this command:
>
> `sudo apt-get install <package-name>`. Replace the &lt;package-name&gt; with your desired package.
>
> If you are not sure about the package name, the you can type a few letters and press tab and it will suggest all the packages available with those letters. Thanks for auto-completion feature.

## ls

> `ls` \(list\) command lists all files and folders in your current working directory. You can also specify paths to other directories if you want to view their contents.

## cd

> `cd` \(change director”\) Linux command also known as chdir used to change the current working directory. It’s one of the most used basic Ubuntu commands. Using this command is easy, just type cd followed by the the folder name. You can use full paths to folders or simply the name of a folder within the directory you are currently working. Some common uses are:
>
> `cd /`  – Takes you to the root directory.
>
> `cd ..` – Takes you up one directory level.
>
> `cd –`  – Takes you to the previous directory.

## pwd

> `pwd` \(print working directory\) Ubuntu command displays the full path name of the current working directory.

## cp

> `cp` \(copy\) Linux command allows you to copy a file. You should specify both the file you want to be copied and the location you want it copied to – f_or example, `cp xyz/home/myfiles` would copy the file “_xyz_” to the directory “/home/_myfiles_”_.

## mv

> `mv` \(move\) command allows you to move files. You can also rename files by moving them to the directory they are currently in, but under a new name. The usage is the same as cp – f_or example `mv xyz /home/myfiles` would move the file “_xyz_” to the directory “/home/_myfiles_”_.

## rm

> `rm` \(remove\) command removes the specified file.
>
> `rmdir` \(“remove directory”\) – Removes an empty directory.
>
> `rm -r` \(“remove recursively”\) – Removes a directory along with its content.

## mkdir

> `mkdir` \(make directory\) command allows you to create a new directory. You can specify where you want the directory created – if you do not do so, it will be created in your current working directory.

## history

> `history` command displays all of your previous commands up to the history limit.

## df

> `df` \(display filesystem\) command displays information about the disk space usage of all mounted filesystems.

## du

> `du` \(directory usage\) command displays the size of a directory and all of its subdirectories.

## free

> `free` – Displays the amount of free space available on the system

## uname -a

> `uname -a` – Provides a wide range of basic information about the system.

## top

> `top` – Displays the processes using the most system resources at any given time. “q” can be used to exit.

## Ubuntu Terminal Shortcuts:

| **Command** | **Description** |
| :--- | :---: |
| `Ctrl + Shift + T` | Open new tab on current terminal |
| `Ctrl + Shift + W` | Close the current tab |
| `Ctrl + A` | Move cursor to beginning of line |
| `Ctrl + E` | Move cursor to end of line |
| `Ctrl + U` | Clears the entire current line |
| `Ctrl + K` | Clears the command from the cursor right |
| `Ctrl + W` | Delete the word before the cursor |
| `Ctrl + R` | Allows you to search your history for commands matching what you have typed |
| `Ctrl + C` | Kill the current process |
| `Ctrl + Z` | Suspend the current process by sending the signal SIGSTOP |
| `Ctrl + L` | Clears the terminal output |
| `Alt + F` | Move forward one word |
| `Alt + B` | Move backward one word |
| `Ctrl + Shift + C` | Copy the highlighted command to the clipboard |
| `Ctrl + Shift + V` or `Shift + Insert` | Paste the contents of the clipboard |
| `Up/Down Arrow keys` | To scroll through your command history, allowing you to quickly execute the same command multiple times |
| `TAB` | Used to complete the command you are typing. If more than one command is possible, you can press it multiple times to scroll through the possible completions. If a very wide number of commands are possible, it can output a list of all possible completions. |

