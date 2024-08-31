# Startup Team Home Network

This is a scenario based cisco packet tracer project I made, the scenario and solution both are created by me and the scenario is explained below.

## Scenario:
A group of 9 friends have planned to start their own startup.

They have split themselves into 5 teams.

One guy is the Administrator ensuring that the progress is moving in the right direction.

A trio of developers having the most powerful PCs to build their website.

Two members take care of advertising, marketing and fund raising for the project.

Two testers, one white box and other black box.

And the last man is the System Administrator who should take care of the networking side of things.

They are all staying in admin's home each picking their own place to work.

![Alt text](./Startup%20Room.png "Startup room")
###### Admin's room floor plan

The Sysadmin had a Cisco Catalyst 2950 24 port router with him and one of the 3 developers bought an old Cisco 1941 series router with him, the Admin had a DSL modem in his home.

Now the problem is to build a network such that each team gets their individual sub network and the router has only 2 ports and one must be connected to the DSL modem.

![Alt text](./Wiring%20Closet.png "Wiring Closet")
###### Network Table

In this project I used cisco packet tracer in physical mode, the setup is as follows:

- 9 PCs seperated into 5 networks with a CIDR of /27 (255.255.255.224)
- 1 Cisco Catalyst 2950-24 switch
- 1 Cisco 1941 router
- 1 DSL modem

![Alt text](./Packet%20Tracer.png "Packet Tracer")
###### PC arrangement and Wiring Closet

## Network Description
This network is 192.168.0.0/27 <br>
Subnet mask: 255.255.255.224

Router interface g0/0 192.168.1.254/24 <br>
Router interface g0/1 
- g0/1.10 192.168.0.30/27
- g0/1.20 192.168.0.62/27
- g0/1.30 192.168.0.94/27
- g0/1.40 192.168.0.126/27
- g0/1.50 192.168.0.158/27

Default gateway 192.168.1.254 <br>
DNS Server 1.1.1.1

Switch Interface:

Admin: (192.168.0.0) (192.168.0.31)
- vlan 10
    - f0/1 (192.168.0.1)

Development: (192.168.0.32) (192.168.0.63)
- vlan 20
    - f0/2 (192.168.0.33)
    - f0/3 (192.168.0.34)
    - f0/4 (192.168.0.35)

Marketing: (192.168.0.64) (192.168.0.95)
- vlan 30    
    - f0/5 (192.168.0.65)
    - f0/6 (192.168.0.66)

Testing: (192.168.0.96) (192.168.0.127)
- vlan 40
    - f0/7 (192.168.0.97)
    - f0/8 (192.168.0.98)

Networking: (192.168.0.128) (192.168.0.159)
- vlan 50
    - f0/9  (192.168.0.129)

## Switch VLAN:
VLAN |Name |                            Status |   Ports
--- | --- | --- | ---
1    |default    |                      active |   Fa0/10, Fa0/11, Fa0/12, Fa0/13, Fa0/14, Fa0/15, Fa0/16, Fa0/17, Fa0/18, Fa0/19, Fa0/20, Fa0/21, Fa0/22, Fa0/23
10  | VLAN0010  |                       active  |  Fa0/1
20   |VLAN0020     |                    active  |  Fa0/2, Fa0/3, Fa0/4
30   |VLAN0030      |                   active  |  Fa0/5, Fa0/6
40   |VLAN0040    |                     active  |  Fa0/7, Fa0/8
50   |VLAN0050   |                      active  |  Fa0/9
1002 |fddi-default  |                   active    
1003 |token-ring-default   |            active    
1004 |fddinet-default  |                active    
1005 |trnet-default    |                active 

## Router IP interface:
Interface |             IP-Address  |    OK? | Method |Status     |           Protocol 
--- | --- | --- | --- | --- | --- 
GigabitEthernet0/0  |   192.168.1.254 |  YES | manual |up        |            up 
GigabitEthernet0/1  |   192.168.0.254 |  YES| manual | up    |  up 
GigabitEthernet0/1.10 | 192.168.0.30  |  YES| manual |up            |        up 
GigabitEthernet0/1.20 | 192.168.0.62  |  YES| manual |up        |            up 
GigabitEthernet0/1.30 | 192.168.0.94  |  YES| manual |up         |           up 
GigabitEthernet0/1.40 | 192.168.0.126  | YES| manual |up           |         up 
GigabitEthernet0/1.50 | 192.168.0.158 |  YES| manual |up        |            up 
Vlan1   |               unassigned   |   YES| unset  |administratively down |down

 ## Takeaways:
 In this project I gained a good understanding of the following skills:

 - Understanding subnetting
 - Vlan assignment
 - Vlan trunking
 - IEEE 802.1Q encapsulation
 - ROAS configuration
