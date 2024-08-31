# Kolkata Call Centre

This is a cisco packet tracer project I made which simulates the call centre in Kolkata which the workers used to scam people around the world.

![Alt text](./Scammer%20Room.jpg "Scammer Room")
###### The CCTV image of the scammers

I tried to remake how their setup would have been on one specific floor which was captured on the CCTV image above.

![Alt text](./Scammer%20design.png "Reegan's design")
###### My recreation of that image

In this project I used cisco packet tracer in physical mode, the setup is as follows:

- 31 PCs seperated into 2 networks
(192.168.1.0/24 and 192.168.2.0/24)
- 2 Cisco Catalyst 2950T switches
- 1 Cisco 2901 router
- 1 DSL modem

![Alt text](./Packet%20Tracer.png "Packet Tracer")
###### PC arrangement and Wiring Closet

The 31 PCs are seperated into 2 networks, the top 14 PCs are connected to switch 1 and the remaining PCs are connected to switch 2

The g0/0 port of Switch 1 is connected to interface g0/1 of the router
The g0/0 port of Switch 2 is connected to interface g0/2 of the router

![Alt text](./Wiring%20Closet.png "Wiring Closet")
###### Inside the wiring closet

## Router IP interfaces:
Interface | IP-Address | OK? | Method | Status | Protocol
--- | --- | --- | --- | --- | ---
GigabitEthernet0/0 | 192.168.0.254 | YES | manual | up | up 
GigabitEthernet0/1 | 192.168.1.254 | YES | manual | up | up 
GigabitEthernet0/2 | 192.168.2.254 | YES | manual | up | up 
Vlan1 | unassigned | YES | unset | administratively down | down

## IP Routes
Gateway of last resort is 0.0.0.0 to network 0.0.0.0

- 192.168.0.0/24 is variably subnetted, 2 subnets, 2 masks

C       192.168.0.0/24 is directly connected, GigabitEthernet0/0
L       192.168.0.254/32 is directly connected, GigabitEthernet0/0

- 192.168.1.0/24 is variably subnetted, 2 subnets, 2 masks

C       192.168.1.0/24 is directly connected, GigabitEthernet0/1
L       192.168.1.254/32 is directly connected, GigabitEthernet0/1

- 192.168.2.0/24 is variably subnetted, 2 subnets, 2 masks

C       192.168.2.0/24 is directly connected, GigabitEthernet0/2
L       192.168.2.254/32 is directly connected, GigabitEthernet0/2

- S*   0.0.0.0/0 is directly connected, GigabitEthernet0/0

## IP DHCP pool
#### Pool switch1 :
 Utilization mark (high/low)    : 100 / 0
 Subnet size (first/next)       : 0 / 0 
 Total addresses                : 254
 Leased addresses               : 17
 Excluded addresses             : 3
 Pending event                  : none

 1 subnet is currently in the pool
 Current index        IP address range                    Leased/Excluded/Total
 192.168.1.1          192.168.1.1      - 192.168.1.254     17   / 3     / 254

#### Pool switch2 :
 Utilization mark (high/low)    : 100 / 0
 Subnet size (first/next)       : 0 / 0 
 Total addresses                : 254
 Leased addresses               : 14
 Excluded addresses             : 3
 Pending event                  : none

 1 subnet is currently in the pool
 Current index        IP address range                    Leased/Excluded/Total
 192.168.2.1          192.168.2.1      - 192.168.2.254     14   / 3     / 254

 ## Takeaways:
 In this project I gained a good understanding of the following skills:

 - Using physical mode in Packet Tracer
 - Setting up a realtime network
 - Configuring router interface ip addresses
 - Configuring ip routes
 - Setting up DHCP pool