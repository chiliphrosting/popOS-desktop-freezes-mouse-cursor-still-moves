# BACKGROUND

"Resets" the desktop and only logs out from the desktop  without rebooting.

# ITEM
- `ssh`: `ssh` into the machine that is freezing.
- `htop`: remote monitor system activities.

## Scripts
_If you want only the script:_
[gdm-x-session](scripts/gdm-x-session.sh)

# STEPS
_Currently, I am testing whether or not it stops the running processes after the computer freezes._

1. `ssh` into the machine that froze.
2. Check running processes: `ps -ef | grep gnome`
3. `killall -9 /usr/libexec/gdm-x-session` # will log out without rebooting.

# CONCLUSION


<!--
drafted: 
20Aug23
-->


