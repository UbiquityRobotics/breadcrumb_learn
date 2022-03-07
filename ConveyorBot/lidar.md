#### &uarr;[top](https://ubiquityrobotics.github.io/ConveyorBot_learn/)

# LiDAR

## Assemble the LiDAR on ConveyorBot

TODO

## LiDAR N301 network setup  on Ubuntu 16.04

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

## LiDAR N301 network setup  on Ubuntu 20.04

Ubuntu changed the way to set static IPs when they upgraded to 20.04. 
To assign a static IP using netplan create/edit the following:

- `/etc/systemd/network/10-eth-dhcp.network`:

		[Match]
		Name=eth0

		[Link]
		RequiredForOnline=no

		[Network]
		ConfigureWithoutCarrier=true
		Address=192.168.42.125/24

- `/etc/netplan/01-netcfg.yaml` (create it if not already present):

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
       
This will flag anyy errors in your file (yaml is space sensitive).       
Check to see if things are correct with 

	ifconfig 
       
and ping to 192.168.42.222 to see if there is a successful transfer of packets:

	ping 192.168.42.222



Also make sure the parameters in the `/breadcrumb_bringup/launch/lidar.launch` are correct:

	<node pkg="lslidar_n301_driver" type="lslidar_n301_driver_node" name="lslidar_n301_driver_node" output="screen">
	    <param name="frame_id" value="laser_link"/>
	    <param name="device_ip" value="192.168.42.222"/>
	    <param name="msop_port" value="2368"/>
	    <param name="difop_port" value="2369"/>
	    <param name="add_multicast" value="false"/>
	    <param name="group_ip" value="224.1.1.2"/>
	  </node>

You can then launch, by using:

	roslaunch breadcrumb_bringup lidar.launch
