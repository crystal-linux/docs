---
title: How to make GNOME Wayland work on an NVIDIA GPU
---
Sometimes, GDM disables GNOME Wayland when it detects you have an NVIDIA GPU. If you want to force-enable GNOME Wayland, you first have to enable DRM [kernel mode setting](https://wiki.archlinux.org/title/Kernel_mode_setting) (KMS) on the NVIDIA driver so Wayland is able to run. To do this, you need to add a kernel parameter to tell the NVIDIA driver to enable KMS. The kernel parameter you need to add is `nvidia_drm.modeset=1`.

## GRUB
For example, if you are using GRUB, there should be a file called `/etc/default/grub` and there should be a line in that file that looks like this.
```
GRUB_CMDLINE_LINUX_DEFAULT="loglevel=3 quiet"
```
You want to append the new kernel parameter at the end of the line, between the quotes. Parameters are separated by spaces, so put a space after the last parameter and append the parameter there. Make sure to edit the file with super-user permissions (like with `sudo`) or you might get errors writing the file.

### Example
 ```
GRUB_CMDLINE_LINUX_DEFAULT="loglevel=3 quiet nvidia_drm.modeset=1"
```
After you do that, you want to make sure GRUB knows that you have changed your kernel parameters. So you need to rebuild your GRUB configuration file. To rebuild your GRUB configuration file, run `sudo grub-mkconfig -o /boot/grub/grub.cfg` and your GRUB configuration should have the new kernel parameter and you can apply it by rebooting your system.

## What to do after you add the kernel parameter.
After you add the kernel parameter, that might be all you need to do to get GNOME Wayland working. Check if you can access GNOME Wayland and if you can't, try these other steps.

GDM uses some chipset dependent [udev rules](https://gitlab.gnome.org/GNOME/gdm/-/blob/main/data/61-gdm.rules.in) to see if it should force Xorg usage instead of letting you use Wayland. If you want to force-enable Wayland, run this command.
```
sudo ln -s /dev/null /etc/udev/rules.d/61-gdm.rules
```
This command should symlink *nothing* to GDM's udev rules. Rules in `/etc/udev/rules.d/` should overwrite rules in `/usr/lib/udev/rules.d` (which are shipped by the package its self and managed by your package manager).


After that, try and reboot and check if GNOME Wayland works. If it still doesn't work, you need to add some modules to your initramfs for early boot modesetting. There should be a file (in Arch based distributions) called `/etc/mkinitcpio.conf`. In that file, there should be a `MODULES` line. On that line, there should be some parentheses. Between them, you can add kernel modules you want built into your initramfs (each module is separated by a space). We want to add some NVIDIA modules to our initramfs so it can be loaded early in the boot process. So add these modules to the file. Make sure to edit this file with super-user permissions.
```
nvidia nvidia_modeset nvidia_uvm nvidia_drm
```
### Example
```
MODULES=(nvidia nvidia_modeset nvidia_uvm nvidia_drm)
```

And after that, you need to regenerate your initramfs. To do that, run this command.
```
sudo mkinitcpio -P
```

And after that, reboot and GNOME Wayland *should* be working!
