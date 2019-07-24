# Installation

1. Pull up [Arch Linux Installation Guide](https://wiki.archlinux.org/index.php/Installation_guide)
   1. Scroll down to [Connect to the Internet](https://wiki.archlinux.org/index.php/Installation_guide#Connect_to_the_internet).
2. Verify internet is working
   1. `ping google.com`
3. [Update the System Clock](https://wiki.archlinux.org/index.php/Installation_guide#Update_the_system_clock)
   1. `timedatectl set-ntp true`
   2. `timedatectl status`
4. [Partition the disks](https://wiki.archlinux.org/index.php/Installation_guide#Partition_the_disks) using `cfdisk` instead of `fdisk`
   1. Run `lsblk` to verify the disk you want to partition
   2. In Virtual Machine I am partitioning `sda`
   3. Run `cfdisk`
   4. Select Label Type `dos`
      1. Choose `New`
      2. Create 2 partitions \(1 `main` and 1 `swap`\)
         1. Main partition needs to be `primary`
         2. Move `tab` to `Bootable` which adds an`*` under `Boot`
         3. Move down to `Free space` and create another `New` space for the `swap` partition
            1. Add rest of memory
            2. Choose `primary` or `extended`. I chose `primary`
            3. Click on the tab `Type`
               1. Change `Type` from `83 Linux` to `82 Linux swap / Solaris` and click `enter`
            4. Now move `tab` to `Write` and hit `enter`
               1. Type `yes` and click `enter`
            5. Now move `tab` to `Quit` and hit enter
   5. [Format the Partitions](https://wiki.archlinux.org/index.php/Installation_guide#Format_the_partitions)
      1. Make the file system `mksf` with type `ext4` to location of the partition `/dev/sda1`. 
         1. In the `terminal` type `mkfs.ext4 /dev/sda1` 
      2. Run `lsblk` to make sure partitions `sda1` and `sda2`are correct.
      3. Now make `swap`
         1. `mkswap /dev/sda2`
         2. Now run command `swapon /dev/sda2`
   6. [Mount file system](https://wiki.archlinux.org/index.php/Installation_guide#Mount_the_file_systems)
      1. `mount /dev/sda1 /mnt`
   7. [Select the Mirrors](https://wiki.archlinux.org/index.php/Installation_guide#Select_the_mirrors)
      1. Edit `etc/pacman.d/mirrorlist`
         1. `nano /etc/pacman.d/mirrorlist`
      2. Delete all lines using `ctrl + k` that arent in the United States. Only keep about `6` or `7`.
      3. Press `ctrl + x` to exit nano.
      4. Click `y` for yes to save modified buffer.
      5. Click `enter` again to save filename
5. [Install the Base Packages](https://wiki.archlinux.org/index.php/Installation_guide#Install_the_base_packages)

