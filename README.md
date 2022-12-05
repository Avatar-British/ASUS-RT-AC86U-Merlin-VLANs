# ASUS-RT-AC86U-Merlin-VLANs
ASUS RT-AC86U (Merlin) VLANs enable test script

The source of the script is coming from the link https://virtualize.link/asus-vlans/
I intend to record down the modified script in case I forgot what I did on the router.

=================================== (Start) Copy from the web origin ===================================
Reasons for using an Asus router:

    - Not cloud connected
    - Doesn't require a controller
    - Supports mesh, wpa3
    - Cheap for a 2x2 Wi-Fi 6 AP with 5 LAN ports and VLAN support
    - Can act as a backup router if needed
    - Has a great community around it with asus-merlin


Steps 
(Tested on the Asus RT-AX58U but could work on any asus-merlin router) :

    - Install Asus-Merlin on the router
    - Set the router to AP mode
    - Enable Administration > System > Enable JFFS custom scripts and configs
    - Set the router to a static IP instead of DHCP
    - Create all needed guest networks, in this example there will be Guest 2.5Ghz and Guest 5Ghz
    - Save the script to /jffs/scripts/services-start after it's done
    - Set chmod a+x /jffs/scripts/services-start
    - Reboot the router to apply changes


Discovery
(Before editing the script we need to figure out the interface names, disconnect all ethernet cables except one and run ip a to check which interface is UP, keep switching between ports and running ip a to map all ports.)

For example:

    - eth0 - LAN 1
    - eth1 - LAN 2
    - eth2 - LAN 3
    - eth3 - LAN 4
    - eth4 - WAN
    - eth5 - Main wifi 2.4Ghz
    - eth6 - Main wifi 5Ghz
    - wl0.1 - Guest wifi 2.4Ghz
    - wl1.1 - Guest wifi 5Ghz


Recovery
If the router doesn't boot after making the changes, you can revert it to factory defaults on most models by following these steps:

    1. Power off the router
    2. Hold the WDS button on the back
    3. Turn the router on while still holding the WDS button
    4. Wait for the power led to turn off
    5. Reboot the router normally



=================================== (End) Copy from the web origin ===================================
