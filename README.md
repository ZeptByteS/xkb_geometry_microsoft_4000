















  /usr/share/X11/xkb/rules/evdev
.
.
.
152! model		layout	=	geometry  
153  thinkpad     us              =       thinkpad(us)
154
155! model		=	geometry
156  microsoft4000_usb = microsoft(4000) // add this line
157  microsoftelite	=	microsoft(elite)
158 $msmodels	=	microsoft(natural)
.
.
.



/etc/default/keyboard
XKBMODEL="microsoft4000_usb"





reboot.
