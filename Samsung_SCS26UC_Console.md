# Using a Serial Cable #
See HDMISerialCable for making your cable

One you have a serial cable, just plug it in, and fire up screen or your terminal of choice.  You will need to connect at 57600,8n1.

As soon as you see the boot prompt, type
`sys<enter>`
You will now be at the u-boot prompt.  Type:
```
setenv runlevel S
setenv watchdog_off 1
```
You're now in maintenance mode!

To get back to normal, type:
```
setenv runlevel
setenv watchdog_off 0
```

## Booting to a usable environment ##
Once you are at the maintenance mode prompt, you are in an essentially unusable environment.  To get all the commands and the like you need, do the following:
```
/etc/rc.d/extract_rfs.sh
cd /ubin/
/etc/rc.d/USER_MODE/S60USER_MODE.sh start
```

## Entering the libdus debug utility shell ##
```
./uimhx &
/usr/local/bin/dshx
CMB
help
```

## VPN Commands ##
Show Contents of VPN config file
```
/app/vpn/vpn -show
```