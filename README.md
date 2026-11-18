Topology & Cabling

Devices: 1x Router (1941), 2x Switches (2960), 3x PCs (PC)
Cable Type: Copper Straight-Through between all devices
PC0 (Fa0) <-> Switch0 (Fa0/1)
PC1 (Fa0) <-> Switch0 (Fa0/2)
Switch0 (Gi0/1) <-> Router0 (Gi0/0)
Switch1 (Gi0/1) <-> Router0 (Gi0/1)
PC2 (Fa0) <-> Switch1 (Fa0/1)

IP Addressing (Desktop > IP Configuration > Static)

PC0: IP 192.168.1.10 | Mask 255.255.255.0 | Gateway 192.168.1.1
PC1: IP 192.168.1.11 | Mask 255.255.255.0 | Gateway 192.168.1.1
PC2: IP 192.168.2.10 | Mask 255.255.255.0 | Gateway 192.168.2.1

Router Configuration (CLI)

enable
configure terminal
interface gigabitEthernet 0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
interface gigabitEthernet 0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
end

Testing & Verification

PC (CMD): ping (test Layer 3 connectivity)
PC (CMD): ping -n 1 (send only 1 packet)
PC (CMD): tracert (show router hops to destination)
PC (CMD): arp -a (view local IP-to-MAC table)
PC (CMD): arp -d (clear ARP cache)
Switch (CLI): show mac address-table (view MAC addresses per port)
Router (CLI): show ip route (view routing table, C = Connected)

Simulation Mode

Switch from Realtime to Simulation (bottom right)
Click Show All/None > Edit Filters > check only ARP and ICMP
Send ping from PC and click Capture / Forward to step through the packets
Click the envelope to see how MAC addresses change at the router while IPs remain the same

![Network Topology](LAN_Routed_Network_1)
