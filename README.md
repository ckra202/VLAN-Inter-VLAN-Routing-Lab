# VLAN-Inter-VLAN-Routing-Lab

## Objective
Simulate a basic office network with two VLANs (HR and IT) and configure inter-VLAN routing using Router-on-a-Stick in Cisco Packet Tracer.

## Topology
- 2 PCs (PC1 in VLAN 10, PC2 in VLAN 20)
- 1 Switch (2960)
- 1 Router (e.g., 2911)
- 1 Trunk Port (Fa0/24)
- Subinterfaces: G0/0.10, G0/0.20

## Network Design
| VLAN | Subnet           | Gateway IP       |
|------|------------------|------------------|
| 10   | 192.168.10.0/24  | 192.168.10.1     |
| 20   | 192.168.20.0/24  | 192.168.20.1     |

## Commands Used

### Switch:
'''bash
vlan 10
vlan 20
interface fa0/1
 switchport mode access
 switchport access vlan 10
interface fa0/2
 switchport access vlan 20
interface fa0/24
 switchport mode trunk

### Router
'''bash
interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
interface g0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
interface g0/0
no shutdown

## Results
- Successful ping between PC1 and PC2 across VLANs
- Both PCs can ping their default gateway
- Trunk and access ports configured properly

## Screenshots
![diagram](https://github.com/user-attachments/assets/5d92b786-87e4-4a12-86d3-0a3490060f2e)

### VLAN Config Output
![COnfig1](https://github.com/user-attachments/assets/139ecde7-33ce-4099-81d1-d88d8929a862)

![config2](https://github.com/user-attachments/assets/bdfe0730-7a2d-40ad-8600-c37b5c79374b)

### Ping
![ping output1](https://github.com/user-attachments/assets/1ac031fd-bd9c-4670-9308-82285bfc1ab0)

![ping output2](https://github.com/user-attachments/assets/1feee2e5-76c0-4de0-868b-81757800d4bb)










