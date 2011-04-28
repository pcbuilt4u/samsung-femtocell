Some femtocells might have a different serial connector that isn't hdmi in this case, you will have to solder very carefully two pins under the board.  If you happen to have this kind of board,
you can contact me at cbalkeATcharter[DOT]net for more information until I get around to taking pictures of the pinout and connections. Replace the AT with the "@", and replace the [DOT] with a dot.
Using u-boot might brick your device with the wrong commands, and this will void your warranty if you haven't already opened it up.
Follow the directions on the wiki to get into u-boot, using the sys[enter] combination.
then type these commands.

setenv runlevel S
setenv watchdog_off 1

Finally type "boot" without the quotes.
When it asks you to press ctrl-d to enter normal mode, press enter instead.
copy ane paste between the lines into the serial terminal after following the above directons.

---------------------------------------------------------------------------------
echo this may only work on some femtocells.
sleep 5
echo after this script is done, and you want to reboot, type [break][s] then [break][b].
sleep 5
echo also, after this script is done, to make sure that it worked, type strings /mnt/mdoc/security/passwd. If this gives an error, type /etc/rc.d/extract_rfs.sh and press enter.  After that wait for it to reboot, and run this script again.
sleep 5
/etc/rc.d/extract_rfs.sh
/etc/rc.d/USER_MODE/S60USER_MODE.sh start
cd /ubin
./uimhx &
----------------------------------------------------------------------------------------

after this, type "/usr/local/bin/dshx" to get into the debug utility shell.
Next type "CMB".  
type help, and you should get a list of commands that you can type.
If you have any trouble, I might be able to help but there is no guarantee that I will be able to help you.


There may be new updates in this file.
If this doesn't work, or if there are any typos, please notify me.