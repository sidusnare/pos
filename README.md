pos
===

PPP over SSH VPN
Programs
==
vpn - The main vpn script, all the magic happens here.
vpn_fixmetrics - The scripts depend on metrics, and specifically them not being zero. My systems have this baked in but this script adjusts them based on good guesses if they arent as expected.
vpn_gaurd - A simple perl infinite loop, watches for a pid and restarts the vpn if something bad happens.
vpn_watch - A wrapper for, makes things easier
vpn_route - A wrapper script that uses location awareness to launch other routing scripts. I talk about my location awareness ideas in sskel ( https://github.com/sidusnare/sskel )
vpn_route_all - Routes everything over the VPN

localarmor - Buttons everything down on the interface specified
localarmor_ssh - Buttons everything down on the interface specified except ssh
pos_vpn - a bare init script
redns - restarts DNS in case DNS info you couldnt access was cached at bad values


Installing
==
For now, it would be best to read and understand the code, adjusting it for your own needs. 
Some notes on this:
I have the local systems config in /etc/pos_vpn.conf and the configuration of the seperate remote servers in /etc/pos_vpn.d
Not included are that ssh keys are used for authentication between the client and server, so this can all be in the background and automatic as you see fit.
You will need to put the server scripts into sudoers, make sure to lock them down to 0700 so you dont get hacked.

Notes
==
This is a prelimiary revision, better layout and documentation to come
