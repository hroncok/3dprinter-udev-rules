# 3dprinter-udev-rules
Rules for udev to give regular users access to operate 3D printers.

Normally, when you connect a RepRap like 3D printer to a Linux machine by an USB cable, you need to be in `dialout` or similar group to be able to control it via OctoPrint, Printrun, Cura or any other control software. Not nay more.

Install this rule to grant all users read and write access to `/dev/ttyUSB[0-9]` and `/dev/ttyACM[0-9]`.

**Disclaimer:** Such device might not be a 3D printer, it my be an Arduino, it might be a modem and it might even be a blender. But normally you would add your user to `dialout` and get access to all of those and more anyway. So I guess be careful when some of the users should not get access to your blenders.

Install to `/etc/udev/rules.d/` if you are an administrator or `/usr/lib/udev/rules.d/` if you are a distribution package maintainer.

After installing, reload the rules by:

    (sudo) udevadm control --reload-rules
