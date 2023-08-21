# BACKGROUND

System log shows a consistent number of `[UFW BLOCK]` right before the desktop freezes on __ALL__ my logs that I've reviewed. A device on the same network with `IP ADDRESS=x.x.x.x` and `MAC=some-mac-address` attempts to log in and fails. I am not confirming the result just yet, however, the suspect rogue device is a likely suspect as of writing this.  

# ITEM
- `ssh`: `ssh` into the :w:q
machine that is freezing.
- `htop`: remote monitor system activities.
- Rogue device 

<!-- ## Scripts -->

## WARNING 
__DO NOT POST THE IP ADDRESS AND MAC ADDRESS TO THE PUBLIC!__

# STEPS

1. Query `/[UFW BLOCK]` in the `syslog`.  
2. Locate the actual rogue device and disconnecting from the network.
3. `sudo systemctl restart gdm3` # will log out without rebooting.

# CONCLUSION

- `syslog` shows of `[UFW BLOCK]` has not appeared since removing the device (phone) from the network. 
- Unknown whether the device or an app is attempting to connecting to the pc. 
- "Different" `MAC` addresses show up in the `[UFW BLOCK]` over the course of monitoring for several days, could suggest the device is virtualizing the address. 
- Unknown if the `[UFW BLOCK]` is from the brand, model, or different applications. 


<!--
drafted: 
21Aug23
-->


