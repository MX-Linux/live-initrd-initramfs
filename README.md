# live-initrd-initramfs
workspace for making the live initrd.gz mount things under /run/initramfs rather than /live.  This is not a final repository.

The easiest way to test the live initrd is on a live usb.  Persistence is not required, and may not even be good for early testing.

While running live, place the initrd folder somewhere accessible and use the unpack-initrd utility to repack the new initrd into the antiX folder of the top level live system.

so if the initrd folder is in $HOME, from $HOME

unpack-initrd --repack
