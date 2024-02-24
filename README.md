# live-initrd-initramfs
workspace for making the live initrd.gz mount things under /run/initramfs rather than /live.  This is not a final repository.

The easiest way to test the live initrd is on a live usb.  Persistence is not required, and may not even be good for early testing.

While running live, place the initrd folder somewhere accessible and use the unpack-initrd utility to repack the new initrd into the antiX folder of the top level live system.

so if the initrd folder is in $HOME, from $HOME

unpack-initrd --repack

there are currently a lot of problems, particularly with generation of the initrd.out file, which sets all the paths up for the inital LIVE_DIR but what is needed by things like persist-save is that the file paths contained in initrd.out should be FINAL_DIR.   If you wnat to test things with persistence enabled, I suggest p_static_root which does work as it does not require periodic persist-save action to keep the file system in check.

to mitigate some issues, the custom 8.sh script will make a symlink from /live to /run/initramfs.  This works to keep a few things operating, like copying of several directories from /live to /run/initramfs (custom menus bin etc locale, and so on.)

Work for not should focus on a operable initrd.  Once that is complete, work can continue to the main file system applicatins.

The initial commit of this repo is the initrd as it currently stands on MX releases as of mx23.  there are several commits for various parts of the initrd file system so that diff comparisons between original and this first rough state are easier.

The intention is that the initrd work while booting sysVinit, and all testing and development should be so.  It is also the intention to keep the initrd functional on antiX, with the furthur intention of offering back upstream once it is in a working state.


