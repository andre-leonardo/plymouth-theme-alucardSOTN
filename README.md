# Alucard SOTN Plymouth Boot Theme

A custom Plymouth boot splash screen featuring Alucard from Castlevania: Symphony of the Night, complete with the Sword Familiar as a loading bar.

## Installation

### Step 1: Copy the Theme Folder
First, open your terminal in the directory where you extracted this download, and copy the `alucard` folder into your system's Plymouth themes directory:

```bash
sudo cp -r alucard /usr/share/plymouth/themes/
```

### Step 2: Set the Theme & Update Boot Image
The command to apply the theme and rebuild your boot image depends on your Linux distribution:

#### Arch Linux / CachyOS / Manjaro / EndeavourOS
```bash
sudo plymouth-set-default-theme -R alucard
```
*(Note: Do not interrupt this command while it runs! It may take a minute or two to rebuild your `initramfs`.)*

#### Fedora / RHEL / Nobara
```bash
sudo plymouth-set-default-theme -R alucard
```
*(Note: This uses dracut under the hood to rebuild your boot image. Do not interrupt it.)*

#### Ubuntu / Debian / Linux Mint / Pop!_OS
On Debian-based systems, `plymouth-set-default-theme -R alucard` usually works, but if it doesn't, use the standard alternatives method:
```bash
sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/alucard/alucard.plymouth 100
sudo update-alternatives --set default.plymouth /usr/share/plymouth/themes/alucard/alucard.plymouth
sudo update-initramfs -u
```

### Testing Without Rebooting
If you want to preview the animation on your desktop before restarting your PC, you can run:
```bash
sudo plymouthd ; sudo plymouth --show-splash ; sleep 5 ; sudo plymouth quit
```

---
**Credits & Disclaimer:**
The character "Alucard" and the "Sword Familiar" are properties of Konami Digital Entertainment. This is a non-commercial, fan-made theme.
