
```bash
loadkeys fr-pc

cfdisk
```
UEFI : Le partitionnement à appliquer sera le suivant, en utilisant l’outil cgdisk pour les plus prudents. Cela ne concerne que les ordinateurs avec circuits en UEFI. 
 * partition / en /dev/sda1 d’une taille de 20 Go en ext4
 * partition EFI en /dev/sda2, d’une taille de 512 Mo, qui sera formaté en Fat32, et référencée en EF00
 * partition swap d’au moins la taille de la mémoire vive en /dev/sda3
 * le reste sera la partition /home, en ext4

```bash
mkfs.ext4 /dev/sda1
mkfs.fat -F32 /dev/sda2
mkswap /dev/sda3
swapon /dev/sda3
mkfs.ext4 /dev/sda4

mount /dev/sda1 /mnt
mkdir /mnt/{boot,home}
mount /dev/sda2 /mnt/boot
mount /dev/sda4 /mnt/home
```

check internet connection with `ip address show`
Use `wifi-menu` for wifi connection

```bash
pacstrap /mnt base base-devel
pacstrap /mnt zip unzip p7zip vim-minimal mc alsa-utils syslog-ng mtools dosfstools
genfstab -U -p /mnt >> /mnt/etc/fstab
pacstrap /mnt grub efibootmgr

arch-chroot /mnt

echo "gilles-arch" >> /etc/hostname

sed -i 's/^#fr_FR.UTF-8 UTF-8/fr_FR.UTF-8 UTF-8/' /etc/locale.gen
locale-gen
export LANG=fr_FR.UTF-8

echo "LANG=fr_FR.UTF-8" >> /etc/locale.conf
echo "LC_COLLATE=C" >> /etc/locale.conf

echo "KEYMAP=fr-latin9" >> /etc/vconsole.conf
echo "FONT=lat9w-16" >> /etc/vconsole.conf
ln -s /usr/share/zoneinfo/Europe/Paris /etc/localtime
hwclock --systohc --utc

mkinitcpio -p linux

grub-mkconfig -o /boot/grub/grub.cfg
# grub-install --no-floppy --recheck --efi-directory=/boot/efi /dev/sda
mount -t efivarfs efivarfs /sys/firmware/efi/efivars
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=arch_grub --recheck
passwd root
pacman -S networkmanager
systemctl enable NetworkManager.service
echo "[archlinuxfr]" >> /etc/pacman.conf
echo "SigLevel = Optional TrustAll" >> /etc/pacman.conf
echo "Server = http://repo.archlinux.fr/$arch" >> /etc/pacman.conf
echo "[multilib]" >> /etc/pacman.conf
echo "Include = /etc/pacman.d/mirrorlist" >> /etc/pacman.conf

exit
umount -R /mnt
reboot
```

Login

```bash
pacman -Syy
pacman -S yaourt ntp cronie

echo "ForwardToSyslog=yes" >> /etc/systemd/journald.conf
alsamixer
alsactl store

pacman -S gst-plugins-base gst-plugins-good gst-plugins-bad gst-plugins-ugly gst-libav
pacman -S xorg-server xorg-xinit xorg-xmessage xorg-utils xf86-input-mouse xf86-video-modesetting xorg-server-utils xorg-apps

useradd -g users -m -s /bin/bash gilles
passwd gilles

lspci | grep -e VGA -e 3D # To detect current graphic driver
yaourt -S ttf-bitstream-vera ttf-liberation ttf-freefont ttf-dejavu ttf-ms-fonts
yaourt -S cups
yaourt -S chromium

yaourt -S cinnamon gnome-extra gnome-terminal lightdm-gtk3-greeter xdg-user-dirs gnome-icon-theme
systemctl start lightdm
systemctl enable lightdm
```

Dans cinnamon:
 - Changer la dispo clavier
 
yaourt -S xf86-input-synaptics
