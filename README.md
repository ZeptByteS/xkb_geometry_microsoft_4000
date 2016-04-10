#xkb geometry for  
#Microsoft Natural Ergonomic Keyboard 4000

![](https://github.com/ZeptByteS/xkb_geometry_microsoft_4000/blob/master/xkb_geometry_natural_ergonomic_4000_large.png)  
  
#**Problems**  
* Keyboard layout chart window crash when resize window with mouse drag / maximize vertically.  
  
 I don't know why, maybe key shapes are too complex to resize. 

* Some keys don't blink.  
  
  Function lock: do not send a scan code.  
  Keys that have same scan code with other keys.  


#Add rules  
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
  

#Change model
/etc/default/keyboard  
`XKBMODEL="microsoft_ergo_4000"`
  
#Clear XKB's cache  
`cd /var/lib/xkb`  
`sudo rm *.xkm`
  
#reboot.  