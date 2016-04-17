(Ubuntu) xkb geometry for
Microsoft Natural Ergonomic Keyboard 4000
------

![](https://github.com/ZeptByteS/xkb_geometry_microsoft_4000/blob/master/microsoft_ergo_4000.png)  
  
Problems
------

Keyboard layout chart window crashed when resize window horizontally with mouse drag / maximize vertically.

I don't know why, maybe key shapes are too complex to resize. 

Some keys are not blinking.  
Function lock: do not send a scan code.  
Keys that have same scan code with other keys.(PageUp, PageDown in Editing, Keypad Backspace)  
So Function lock and Keypad backspace are just solid shapes, not allocated any scancode.  


Add rules  
------
/usr/share/X11/xkb/rules/evdev  


    .
    .
    .
    152! model		layout	=	geometry
    153  thinkpad     us              =       thinkpad(us)
    154
    155! model		=	geometry
    156  microsoft_ergo_4000 = microsoft(4000) // add this line
    157  microsoftelite	=	microsoft(elite)
    158 $msmodels	=	microsoft(natural)
    .
    .
    .
  

Change model
------
/etc/default/keyboard  
`XKBMODEL="microsoft_ergo_4000"`
  
Clear XKB's cache  
------
`cd /var/lib/xkb`  
`sudo rm *.xkm`
  
And reboot.  
