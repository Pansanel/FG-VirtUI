FG-VirtUI
=========
The FG-VirtUI appliance aims to be a simple way to use the French Grid
Infrastructure, by providing a preconfigured set of Grid-Enabled software.
This appliance is based on the Scientific Linux 6.6 OS and the UMD-3 UI
software suite. It provides also the iRODS-3.3 clients. All security updates
until the 4th of December 2014 have been applied.

For more informations, please read the following documentations:
* https://github.com/Pansanel/FG-VirtUI/wiki 
* https://forge.in2p3.fr/projects/france-grilles-documentation/wiki/Utiliser_la_ligne_de_commandes_EMI
* https://forge.in2p3.fr/projects/france-grilles-documentation/wiki/Utiliser_le_service_iRODS

Notes
=====
The password for the root user is 'virtui'
The user account is 'ui-user'. The password is 'ui-user'.
The passwords should be changed as soon as possible.

Troubleshooting
===============
In some cases, it has been observed that the clock of the guest does not
synchronize correctly with the ntp servers. First, you should ensure that the
guest can access the ntp servers listed in the /etc/ntp.conf file. If the
issue is not fixed, use the following commands on the VirtualBox host:
VBoxManage guestproperty set "FG-VirtUI" "/VirtualBox/GuestAdd/VBoxService/--timesync-interval" 1000
VBoxManage guestproperty set "FG-VirtUI" "/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold" 1000
