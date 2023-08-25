# BACKGROUND
After removing rogue device from network, the pc still froze, only that this time when running `sudo systemctl restart gdm3`, the device screen would print out the `syslog i915 [drm] *ERROR*`. Several VMs and chromium based browser were open at the time of freezing.

# ITEM
- `ssh`: `ssh` into the :w:q
machine that is freezing.
- `htop`: remote monitor system activities.
- Other HDMI displays

<!-- ## Scripts -->

<!-- ## WARNING -->


# STEPS

1. Before starting PC, disconnecting any additional displays.  
2. Reboot if needed if you still have the additional display connected.


# CONCLUSION

- No `*ERRORS*` have occurred since unplugging the additional monitor at the time of this writing (25Aug23): PM.  
- No `*ERRORS*` have occurred since unplugging the additional monitor at the time of this writing (24Aug23): PM.  
- No `*ERRORS*` have occurred since unplugging the additional monitor at the time of this writing (23Aug23): PM.  
- No `*ERRORS*` have occurred since unplugging the additional monitor at the time of this writing (23Aug23): AM.  
- No `*ERRORS*` have occurred since unplugging the additional monitor at the time of this writing (22Aug23).  

After reviewing `syslog` over the course of the week, I can confirm the reason is from the additional HDMI display. This issue did not exist prior to the `update/upgrade` from ~3 weeks ago. Early on, after that update, the pc desktop did lock up but only a couple of times. When attached to the external HDMI display, the problem persisted as time passed, progressively worsened. 

<!--
drafted: 
22Aug23
-->


