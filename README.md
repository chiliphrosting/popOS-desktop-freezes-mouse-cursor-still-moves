# BACKGROUND
_This is being revised on the fly, so please excuse some of the typos, etc as I am trying to resolve the issue while documenting the process._


The Desktop for PopOs and sometimes the VMs, themselves, are locking up. When accessing the pc remotely via `ssh` sometimes the shell freezes and other times, operates fine. Using `htop` shows system is running normal.   

Some of the solutions listed in this __README.md__ may resolve the issue(s). Results may vary since the configurations from everyones' machines are different. 

As of this writing (_18Aug23_), I am still investigating solutions since the issue still persists. As long as I am __not__ using a browser on the host machine. The browser seems to "__delay__" the desktop from freezing.   

The origin of the desktop freezing seemed to have happened after both a recent `update` and `upgrade`. Below is a list of symptoms when the desktop freezes:


* Occurs much faster when using a browser, that happens "faster" with Chromium based ones, in the host computer, especially when many tabs are open, YouTube is playing, and/or having a busy website open in one of the tabs.
* The freezing Doesn't occur during the screen.
* Seems to occur on `gnome` desktops.
* PERFORMANCE
	- No observable reduction in performance when `ssh` into machine when the desktop freezes. 
* The issue may be a combination of issues.
* The fan speed does increase when the screen freezes, but with no noticable increase in processes consuming sofware or hardware resources. 

## WARNING

__THE DESKTOP COULD POSSIBLE FREEZE WHILE YOU ARE `update/upgrade` AND YOU SHOULD WAIT UNTIL THE PROCESS FINISHES BEFORE YOU CONSIDER REBOOTING. WAITING A LITTLE AFTER THE FREEZE OCCURS DOESN'T HURT.'__

# ROOT CAUSE
These are the potential causes of the issue:
- RAM
- swap
- Harddrive
- GNOME
- VM (recently updated)
- Additional Attached Hardware

__ERROR WHEN ISSUE ARISES FROM system logs__ (I redacted some info):
```
DATE-TIME USER kernel: [ num ] i915 0000:00:02.0: [drm] *ERROR* [CRTC:131:pipe B] flip_done timed out
DATE-TIME USER /usr/libexec/gdm-x-session[ num ]: (II) event8  - Logitech Trackball: SYN_DROPPED event - some input events have been lost.
DATE-TIME USER kernel: [ num ] i915 0000:00:02.0: [drm] *ERROR* flip_done timed out
DATE-TIME USER kernel: [ num ] i915 0000:00:02.0: [drm] *ERROR* [CRTC:131:pipe B] commit wait timed out
```
# STEPS

## INITIAL TESTS IF ISSUE IS FROM RAM or HD

[Check System76 system logs and test harddrive.](LOGS-NVME.md)

## HARDWARE DISCONNECT
[Disconnecting the additional monitor.](HW.md)

## UFW BLOCK
[UFW BLOCK could be the reason why the desktop is freezing!](UFW-BLOCK.md)

## SYSTEM CONTROL STATUS CHANGE 
[Restart gdm3 in system control.](SYSTEMCTL-STATUS.md)

## GNOME DESKTOP RESET
[Killall gnome-shell processes](GNOME-SHELL.md)

## GNOME-EXTENSIONS
[Disable all gnome extensions.](GNOME-EXTENSIONS.md)

## GRAPHICS CARD DRIVER UPDATE

[Update the Intel integrated graphics card.](GRAPHICS-CARD.md)

## Xorg DISABLING
[Shutoff Xorg](XORG.md)
- `xset s off`

## SETTINGS CHANGE
[Disable notifications and HIDPI.](HIDPI.md)

## GDM-X-SESSION
[kill process gdm-x-session](GDM-X-SESSION.md)

## IF DESKTOP FROZEN
_This is the last resort_:
[Soft reboot the PC.](REISUB.md)

### reference:
* [https://support.system76.com/articles/freezing-behavior/](https://support.system76.com/articles/freezing-behavior/)
* [https://github.com/pop-os/pop/issues/1069](https://github.com/pop-os/pop/issues/1069)
* [https://github.com/pop-os/pop/issues/959](https://github.com/pop-os/pop/issues/959)

# CONCLUSION

___

<!--
draft 16Aug23
-->
