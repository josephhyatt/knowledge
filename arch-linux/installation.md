# Installation

## Install Arch Linux

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
5. [Install the Base Packages](https://wiki.archlinux.org/index.php/Installation_guide#Install_the_base_packages) Installs the base arch linux system
   1. In the terminal type`pacstrap /mnt base`
6. [Configure the System](https://wiki.archlinux.org/index.php/Installation_guide#Configure_the_system)
   1. [Fstab](https://wiki.archlinux.org/index.php/Installation_guide#Fstab)
      1. `genfstab -U /mnt >> /mnt/etc/fstab`
   2. [Chroot](https://wiki.archlinux.org/index.php/Installation_guide#Chroot)
      1. `arch-chroot /mnt`
   3. [Time Zone](https://wiki.archlinux.org/index.php/Installation_guide#Time_zone) \(to search for timezone `ls /usr/share/zoneinfo/America`
      1. `ln -sf /usr/share/zoneinfo/America/Los_Angeles /etc/localtime`
      2. `hwclock --systohc`
      3. `locale-gen`
      4. `nano /etc/locale.conf`
         1. Add `LANG=en_US.UTF-8`
         2. Exit `ctrl + x`
         3. Click `y` to save
         4. Click `enter` to save file name
   4. [Network Configuration](https://wiki.archlinux.org/index.php/Installation_guide#Network_configuration)
      1. `nano /etc/hostname`
         1. Enter desired hostname. I used `jh`
         2. Exit `ctrl + x`
         3. Click `y` to save
         4. Click `enter` to save file name
      2. `nano /etc/hosts`
         1. Add `127.0.0.1` tab over and write `localhost`
         2. Add `::1` tab over and write `localhost`
         3. Add `127.0.1.1` tab over and write `jh.localdomain` tab over again and write `jh`. `jh` is the hostname I chose in the `1st` step under `Network Configuration`
         4. Exit `ctrl + x`
         5. Click `y` to save
         6. Click `enter` to save file name
   5. [Root Password](https://wiki.archlinux.org/index.php/Installation_guide#Root_password)
      1. `passwd` and hit `enter`
      2. set your root password
      3. retype your root password
7. [Network Configuration](https://wiki.archlinux.org/index.php/Network_configuration)
   1. Enable DHCPCP \(starts internet on boot\)
      1. `systemctl enable dhcpcd` 
8. [Users and Groups](https://wiki.archlinux.org/index.php/Users_and_groups)
   1. Add username
      1. `useradd -m joseph`
   2. Change password for user `joseph`
      1. `passwd joseph`
   3. Install sudo
      1. `pacman -S sudo`
   4. Add joseph to Group with admin privileges
      1. `usermod -aG wheel,audio,input,optical,storage,video joseph`
   5. Verify groups you belong too
      1. `groups joseph`
   6. Add vim
      1. `pacman -S vim`
   7. Add joseph to sudoers file
      1. `visudo`
         1. vim movement
            1. j - down
            2. k - up
            3. h -left
            4. l -right
         2. Look for line `## Uncomment to allow members of group whell to execute any command`
            1. Move cursor under `#` of `# %wheel ALL=(ALL) ALL` and 
               1. Click `x` to delete the `#` to uncomment that line.
            2. Quit out of vim
               1. click `:` and type `wq` and click `enter`
9. [Install GRUB](https://wiki.archlinux.org/index.php/Arch_boot_process#Boot_loader) \(boot loader\)
   1. Download grub 
      1. `pacman -S grub`
   2. Install grub to disk grub will be going on \(not `sda1`\)
      1. `grub-install /dev/sda` 
   3. Create grub config file
      1. `grub-mkconfig -o /boot/grub/grub.cfg`
10. Reboot \(You're Finished!\)

## Install Graphical Environment

1. Install Xorg
   1. `sudo pacman -S xorg`

## Install Gnome

1. Verify you have sudo privilages
   1. `sudo pacman -Syyu`
2. Install `reflector` to get the fastest mirrors and backup the current mirrorlist and generatte a new one
   1. `sudo pacman -S reflector`
   2. `sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup`
   3. `sudo reflector --verbose --latest 10 --sort rate --save /etc/pacman.d/mirrorlis`
3. Install `Xorg` and needed `video drivers`
   1. `sudo pacman -S xorg-server xterm xorg-xinit xf86-video-vesa bash-completion nvidia`
4. Check if `X` works
   1. `startx`
      1. Exit out of `X`
         1. `exit`
5. [Install Gnome](https://wiki.archlinux.org/index.php/GNOME#Installation)
   1. `sudo pacman -S gnome gdm`
6. Enable the `GDM` service so it starts on boot
   1. `sudo systemctl enable gdm`
7. Reboot your machine! You're Done!
   1. `reboot`



