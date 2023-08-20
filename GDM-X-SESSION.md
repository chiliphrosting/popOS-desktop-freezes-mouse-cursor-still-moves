# BACKGROUND

# ITEM
- `ssh`: `ssh` into the machine that is freezing.
- `htop`: remote monitor system activities.

# STEPS
1. `ssh` into the machine that froze. 
2. Check running processes: `ps -ef | grep gnome`
3. `killall -9 /usr/libexec/gdm-x-session`: will log out without rebooting.

# CONCLUSION


<!--
drafted: 
20Aug23
-->


