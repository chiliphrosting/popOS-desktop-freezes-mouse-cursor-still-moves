# BACKGROUND
The Desktop for PopOs and sometimes the VMs, themselves, are locking up. When remote via `ssh` sometimes the shell freezes and other times it operates fine. Using `htop` shows system is running normal.   

Some of the solutions listed in this __README.md__ may resolve the issue(s). Results may vary since the configurations from everyones' machines are different. 

As of this writing (_18Aug23_), I am still investigating solutions since the issue still persists. As long as I am __not__ using a browser on the host machine, it seems to "__delay__" the desktop from freezing.   

The issue seemed to have happened after both a recent `update` and `upgrade`. 

* Occurs much faster when using a browser in the host computer, especially when many tabs are open.
* Doesn't occur when locking the screen.
* Seems to occur on `gnome` desktops.
* PERFORMANCE
	- No observable reduction in performance when `ssh` into machine when the desktop freezes. 
* The issue may be a combination a combination of issues. 

# ROOT CAUSE
These are the potential causes of the issue:
- RAM
- swap
- Harddrive
- GNOME
- VM (recently updated)

__ERROR WHEN ISSUE ARISES FROM system logs__ (I redacted some info):
```
DATE-TIME USER kernel: [ num ] i915 0000:00:02.0: [drm] *ERROR* [CRTC:131:pipe B] flip_done timed out
DATE-TIME USER /usr/libexec/gdm-x-session[ num ]: (II) event8  - Logitech Trackball: SYN_DROPPED event - some input events have been lost.
DATE-TIME USER kernel: [ num ] i915 0000:00:02.0: [drm] *ERROR* flip_done timed out
DATE-TIME USER kernel: [ num ] i915 0000:00:02.0: [drm] *ERROR* [CRTC:131:pipe B] commit wait timed out
```
# STEPS

## INITIAL TESTS IF ISSUE IS FROM RAM or HD

```bash

gzip -d system76-logs.tgz

free -h # checks the amount of free space on the device

sudo apt update 

sudo apt install memtester # checks available memory
sudo memtester

 
sudo apt install nvme-cli # for nvme drive 
sudo nvme list 
sudo nvme smart-log /dev/nvme0n1
```
- The above returns no errors, they are not ruled out as being the culprit. The frequency of the occurance happens "faster" when several applications are running simultaneously. 
- Correction: The gzip system76 log file(s) have not been reviewed yet

## GNOME DESKTOP RESET
[Killall gnome-shell processes](GNOME-SHELL.md)

## GNOME-EXTENSIONS
[Disable all gnome extensions.](GNOME-EXTENSIONS.md)

## GRAPHICS CARD DRIVER UPDATE
_using Intel integrated graphics_ 

- `sudo apt-get install xserver-xorg-video-intel # updates the intel integrated graphics drivers` 
- `sudo apt autoremove # removes unused packages`

## Xorg DISABLING
- `xset s off`

## SETTINGS CHANGE

- Disable notifications
- Disable HIDPI

## GDM-X-SESSION
[kill process gdm-x-session](GDM-X-SESSION.md)

## IF DESKTOP FROZEN
_This is the last resort_:
Press Alt + Print Sceen + REISUB. 

This does not resolve the issue but only does a soft reboot of the system. 

### reference: 
* [https://support.system76.com/articles/freezing-behavior/](https://support.system76.com/articles/freezing-behavior/)
* [https://github.com/pop-os/pop/issues/1069](https://github.com/pop-os/pop/issues/1069)

# CONCLUSION

___

<!--
draft 16Aug23
-->
