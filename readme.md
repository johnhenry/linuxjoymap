# linuxjoymap
  
Originally forked from: https://sourceforge.net/projects/linuxjoymap/ under GPLv2

## Instructions
1) Make sure that the module uinput is loaded,
     I have
        rmmod ehci_hcd
        rmmod ohci_hcd
        rmmod uinput
        modprobe uinput
        /sbin/reserve_js
        modprobe ehci_hcd
        modprobe ohci_hcd
    in /etc/rc.d/rc.local. This ensures that js0 through 16 are reserved
    for the program. The program /sbin/reserve_js waits 10 seconds
    before releasing js0 through 16.

2) You need permissions on /dev/uinput and /dev/input/event*
3) The uinput device can now be specified with --uinput_dev,
   and the event device prefix with --event_dev
4) Run the program loadmap with your script, it will continue running
   and provide the joystick events programmed until the program is
   terminated.
5) Joystick selection by number is broken, the vendor and product
   identifier must be used
