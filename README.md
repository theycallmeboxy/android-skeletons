# Android Skeletons
Android skeletons from my closet

## Rclone + Fuse
Compiled for Android.  I use it for mounting SMB shares system wide.

https://github.com/NewFuture/rclone-fuse3-magisk

## Root Instructions for MagicX One 35
***ALL DATA WILL BE DESTROYED IN THIS PROCESS***

1. Enable Developer Options (tap Build Number 7x), turn on USB Debugging + OEM Unlocking
2. `adb shell getprop ro.boot.slot_suffix` — note whether you're on `_a` or `_b`
3. `adb shell dd if=/dev/block/by-name/boot_a of=/sdcard/boot.img` (substitute slot from step 2)
4. `adb pull /sdcard/boot.img ./`
5. `adb install magisk.apk`
6. `adb push boot.img /sdcard/Download/`
7. On device: Magisk → Install → Select and Patch a File → pick boot.img → Let's Go
8. `adb pull /sdcard/Download/magisk_patched-*.img ./`
9. `adb reboot bootloader`
10. `fastboot flashing unlock` (confirm on device — **wipes all data**)
11. `fastboot flash boot_a magisk_patched-XXXXX.img` (substitute slot from step 2)
12. `fastboot reboot`
13. On device: Connect to wifi and run Magisk to re-download the full Magisk Manger
14. Magisk → Install → Direct Install → Let's Go
15. Confirm version numbers are visible for both App and Magisk.
