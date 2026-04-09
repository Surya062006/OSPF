# OSPF
This project demonstrates the implementation of OSPF (Open Shortest Path First) routing protocol using Cisco Packet Tracer. The topology consists of three routers connected in a triangular structure, each serving a separate LAN.


OSPF is used to dynamically exchange routing information between routers and ensure efficient path selection.


Network Topology
3 Routers (Router1, Router2, Router3)
3 Switches
3 PCs (one in each LAN)
Serial links between routers forming a triangle
🌐 IP Addressing Scheme
Device	Interface	IP Address
Router1	G0/0	192.168.1.1
Router2	G0/0	192.168.3.1
Router3	G0/0	192.168.2.1
PC0	-	192.168.1.2
PC1	-	192.168.3.2
PC2	-	192.168.2.2
🔗 Serial Links
Router1 ↔ Router3 → 10.0.0.0/30
Router3 ↔ Router2 → 11.0.0.0/30
Router1 ↔ Router2 → 12.0.0.0/30
⚙️ OSPF Configuration
🔹 Router1
enable
configure terminal
router ospf 1
router-id 1.1.1.1
network 192.168.1.0 0.0.0.255 area 0
network 10.0.0.0 0.0.0.3 area 0
network 12.0.0.0 0.0.0.3 area 0
end
write memory
🔹 Router2
enable
configure terminal
router ospf 1
router-id 2.2.2.2
network 192.168.3.0 0.0.0.255 area 0
network 11.0.0.0 0.0.0.3 area 0
network 12.0.0.0 0.0.0.3 area 0
end
write memory
🔹 Router3
enable
configure terminal
router ospf 1
router-id 3.3.3.3
network 192.168.2.0 0.0.0.255 area 0
network 10.0.0.0 0.0.0.3 area 0
network 11.0.0.0 0.0.0.3 area 0
end
write memory
✅ Features
Dynamic routing using OSPF
Full connectivity between all LANs
Efficient path selection
Scalable and fast convergence
🔍 Verification Commands
show ip ospf neighbor
show ip route ospf
show ip protocols
📸 Output
