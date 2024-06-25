# Banana Network Topology.md
Intro

Pending Update to Profile in Progress (as of 6/16/2024)

NEXT UPDATE PLANS:

I am planning on adding VLANS to the network so the Switch's SVI will be the one to hold onto the IP addresses for the switch.

Day 3 (6/24/2024)

Haven't had much time to work on this project, but I've noticed that I accidentally used a broadcast ip for one of the host devices (router0) therefore I switched it to be one IP lower (ip address 192.168.0.254 255.255.255.0 is now ip address 192.168.0.253 255.255.255.0)


_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

Day 2 (6/16/2024)

Apologies for late update. Was busy with IRL stuff but I managed to finish my basic router on a stick network topology (**Disregard the notes I left for myself on the diagram).

Here is what I did:

1. Configured Switch 0 to have a hostname: 

"
en
Conf t 
hostname Switch 0

"

**NOTE: Easy mistake, but as I was configuring the switch, I tried to assign it an IP address and got error messages. HOWEVER, I realized that since a switch is a L2 device, IP address should not get involved. At least not until SVI's are involved (will be configured later).


2. Configured router0 to have IP address on interface g0/1

 "
en
Conf t 
hostname Switch 0
ip address 192.168.0.254 255.255.255.0
"

**NOTE: I also had to put in the command "no shut" to interface g0/1 because by default, the Cisco router's interface will remain in a down/down unless I manually put it that command to put it in an UP/UP state from what I've noticed.

3. Configured PC to have an IP address and a default gateway of our Router 0:

![image](https://github.com/SteveHTrann/BananaNetworkTopology.md/assets/71569932/3fd33700-3dc8-4d89-93ed-444dee127d5c)
![image](https://github.com/SteveHTrann/BananaNetworkTopology.md/assets/71569932/2d9d82c9-e8f5-4212-ace0-43b02b7c8ada)


Progress so far:

The Banana's CEO PC can ping the Router in the network.
![image](https://github.com/SteveHTrann/BananaNetworkTopology.md/assets/71569932/8560efdd-3922-428c-aef7-8f550e04e04f)


Topology so far (notice how all the connections are green to indicate connectivity)

![image](https://github.com/SteveHTrann/BananaNetworkTopology.md/assets/71569932/9badfb5c-d8ec-44c2-be59-32a9e8730dfb)





_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________


Day 1 (6/5/2024): 

Scenario: A small startup (Banana) is trying to build its network infrastructure to eventually be able to scale up one day to be the best Tech company in the world.  Below is my update as I make tweaks and edits using Cisco Packet Tracer utilizing what I learn from obtaining my CCNA and continued self-education to build out the Diagram of this network topology.

Note: So far, the notes I leave will be very brief and not as full-out and fleshly Documented as I'm still working on building out this project.


We will start off using a Class C Network of Private IP Ranges: 192.168.0.0 to 192.168.255.255.  Since Banana HQ is a startup, we don't anticipate needing more than 254 hosts OR in other words, devices for our network in particular.


![image](https://github.com/SteveHTrann/README.md/assets/71569932/e3f2a736-38a4-48c9-87b0-185acc967951)

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
