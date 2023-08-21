# BACKGROUND

"Restarts" the desktop and only logs out from the desktop  without rebooting.

# ITEM
- `ssh`: `ssh` into the machine that is freezing.
- `htop`: remote monitor system activities.

<!-- ## Scripts -->




## <span style="color:red">Warning</span>
_<span style="color:red">Running this will stop child processes.</span>_

# STEPS
_Currently, I am testing whether or not it stops restarting the process vs killing the process is "more effective " before the computer freezes._

1. `ssh` into the machine that froze. 
2. Check running processes: `ps -ef | grep gnome`
3. `sudo systemctl restart gdm3` # will log out without rebooting.

# CONCLUSION


<!--
drafted: 
21Aug23
-->


