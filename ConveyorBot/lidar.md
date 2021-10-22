#### &uarr;[top](https://ubiquityrobotics.github.io/ConveyorBot_learn/)

# LiDAR

## Assemble the LiDAR on ConveyorBot

TODO

## LiDAR N301 network setup

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
