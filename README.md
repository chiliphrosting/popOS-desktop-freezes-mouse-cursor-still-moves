# BACKGROUND
The Desktop for PopOs and sometimes the VMs, themselves, are locking up. When remote via `ssh` sometimes the shell freezes and other times it operates fine. Using `htop` shows system is running normal.   

__ISSUE__: [https://github.com/pop-os/pop/issues/1069](https://support.system76.com/articles/freezing-behavior/)

# ROOT CAUSE
These are the potential causes of the issue:
- RAM
- swap
- Harddrive
- GNOME

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

## IF DESKTOP FROZEN
Press Alt + Print Sceen + REISUB. 

This does not resolve the issue but only does a soft reboot of the system. 

### reference: 
[https://support.system76.com/articles/freezing-behavior/](https://support.system76.com/articles/freezing-behavior/)
https://github.com/pop-os/pop/issues/1069

# CONCLUSION

___

<!--
draft 16Aug23
-->
