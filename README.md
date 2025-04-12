# external-ssd-linux-fix
Simple solution for installing Linux on external SSDs without boot issues - remove internal drives during installation.

# Install Linux on External SSD/M.2 Drive

## Common Error
- "Reboot and select proper boot device"
- GRUB installing to internal SSD boot sector instead of external drive
- Boot failures after seemingly successful installation

## Solution
Simply remove all internal storage devices before installation!
- For M.2 SSDs: physically remove them
- For SATA SSDs/HDDs: unplug the data cables

This forces the installer to properly configure bootloaders on your external drive without confusion.

## Tested With
- Arch Linux (confirmed working)
- Method should work for all major Linux distributions

## Arch Linux Installation Steps
1. Boot from Arch Linux netboot media
2. Once in shell:
   ```bash
   pacman -Sy
   pacman -Sy archlinux-keyring
   pacman -Sy archinstall
   archinstall
3. Follow the installation.

# Why This Works
Linux installers can get confused about bootloader placement when multiple drives are present. Removing internal drives forces correct configuration on the external drive.
