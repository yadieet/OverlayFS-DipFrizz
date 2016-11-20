# OverlayFS DipFrizz
The simple yet easy way to boot and running GNU/Linux system READ-ONLY using OverlayFS.<br />
Applying overlay via `systemd service` method, not via `initramfs hook` method.


####2 Modes :
- *DipFrizz* Mode
- *KeepSession* Mode

####A note about OverlayFS :

+ From https://www.kernel.org/doc/Documentation/filesystems/overlayfs.txt :

   >
   > ######Non-directories
   > ---------------

   >Objects that are not directories (files, symlinks, device-special
files etc.) are presented either from the upper or lower filesystem as
appropriate.  When a file in the lower filesystem is accessed in a way
the requires write-access, such as opening for write access, changing
some metadata etc., the file is first **copied from the lower filesystem
to the upper filesystem (copy_up)**.  Note that creating a hard-link
also requires copy_up, though of course creation of a symlink does
not.

   It doesn't operate at block-level.
   Means, it doesn't really fit for editing big files.
   Except, you use fast storage media (SSD) and or patient enough to wait for first "copy up" process.


