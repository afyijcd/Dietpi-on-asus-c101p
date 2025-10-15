# Dietpi-on-asus-c101p
How to get dietpi running on an old Asus flipbook


Install Velvet OS on an ASUS C101 - use the install script or you'll get uuid conflicts

use nmtui to connect to internet if necessary

- Extend rootfs (see /scripts).
- Set root password: `sudo passwd root`.
- Connect via Ethernet.
- Install DietPi / Download / Other.

choose Generic device when prompted

(Optionally create a DietPi image from the SD card on another computer.)

Create a file in /etc/udev/rules.d

nano 10-network.rules

Paste the following into it (with the correct MAC address that you find using the command `ip link`):
SUBSYSTEM=="net", ACTION=="add", ATTR{address}=="aa:bb:cc:dd:ee:ff", ATTR{dev_id}=="0x0", NAME="wlan0"

#this ensures that mlan0 is renamed to wlan0 — otherwise Wi‑Fi will not work on the ASUS

Optionally, you can create a DietPi image with the Imager. You still need to export the variables. Git owner is ‘MichaIng’ and git branch is ‘master’.

Boot up and finalize the DietPi installation/configuration.
