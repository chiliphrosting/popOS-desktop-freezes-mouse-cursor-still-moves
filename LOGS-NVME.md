# BACKGROUND
## WARNING


# ROOT CAUSE
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
- The gzip system76 log file(s) reviewed (24Aug23).




### reference:
* [https://support.system76.com/articles/freezing-behavior/](https://support.system76.com/articles/freezing-behavior/)
* [https://github.com/pop-os/pop/issues/1069](https://github.com/pop-os/pop/issues/1069)
* [https://github.com/pop-os/pop/issues/959](https://github.com/pop-os/pop/issues/959)

# CONCLUSION

___

<!--
draft 16Aug23
-->
