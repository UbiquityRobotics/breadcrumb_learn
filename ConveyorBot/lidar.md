#### &uarr;[top](https://ubiquityrobotics.github.io/ConveyorBot_learn/)

# LiDAR

## Assemble the LiDAR on ConveyorBot

TODO

## LiDAR N301 network setup  ***see below for Ubuntu 20.04 setuo

In order to make LiDAR work setup static IP
	
	sudo nano /etc/network/interfaces

and make the eth0 interface looks like

	auto eth0
		iface eth0 inet static
		address 192.168.42.125/24 #this IP may depend on your lidar settings
		gateway 0.0.0.0
		dns-nameservers 8.8.8.8

After that REBOOT the robot - for the changes to apply.

## Troubleshooting

Once network is setup, you should be able to see LiDAR scan points values by typing into the terminal (on robot):

	rostopic echo /scan
	
If you don't see any than, something is wrong.

*** 
Ubuntu changed the way to set static IPs when they upgraded to 20.04

to assign a static IP using netplan create/edit the following:

cd /etc/systemd/network/

sudo vi 10-eth-dhcp.network

# Run as DHCP client on all ethernet ports by default
[Match]
Name=eth0

[Link]
RequiredForOnline=no

[Network]
ConfigureWithoutCarrier=true
Address=192.168.42.125/24

then edit the file in /etc/netplan  usually called 01-netcfg.yaml

# This file describes the network interfaces available on your system
# For more information, see netplan(5).
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
     dhcp4: no
     addresses: [192.168.42.125/24]
     gateway4: 0.0.0.0
     nameservers:
       addresses: [8.8.8.8]
       
       Since netplan is being used we also need apply the changes:
       
       sudo netplan --debug apply
       
       this will flag anyy errors in your file -  yaml is space sensitive
       
       Check to see if things are correct with ipconfig or ip a
       
       ping to 192.168.42.222 to see if there are packets.

In the /lslidar_n301_decoder/launch/lslidar_n301.launch

make sure parameters are correct:

<node pkg="lslidar_n301_driver" type="lslidar_n301_driver_node" name="lslidar_n301_driver_node" output="screen">
    <param name="frame_id" value="laser_link"/>
    <param name="device_ip" value="192.168.42.222"/>
    <param name="msop_port" value="2368"/>
    <param name="difop_port" value="2369"/>
    <param name="add_multicast" value="false"/>
    <param name="group_ip" value="224.1.1.2"/>
  </node>

You can then launch, but be aware once the lidar is launched, your terminal session may become extremely slow.
