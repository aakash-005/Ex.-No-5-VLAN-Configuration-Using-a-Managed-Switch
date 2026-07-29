## Ex. No: 5  VLAN Configuration Using a Managed Switch
# Date:29/07/2026
# Name : Agash G
# Reg no : 212223060011
________________________________________
# Objective
To configure Virtual Local Area Networks (VLANs) on a managed switch and verify that hosts within the same VLAN can communicate while others cannot.
________________________________________
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Managed Switch (e.g., 2960)<br>
•	4 PCs<br>
•	Straight-through Ethernet cables<br>
________________________________________
# Network Topology Diagram
Description:<br>
•	PC0 and PC1 are assigned to VLAN 10.<br>
•	PC2 and PC3 are assigned to VLAN 20.<br>
•	All PCs are connected to different ports on the same switch.<br>
(Insert screenshot of your Packet Tracer setup here)<br>
________________________________________
# IP Addressing Table
Device	VLAN	IP Address	Subnet Mask	Port<br>
PC0	10	192.168.10.1	255.255.255.0	FastEthernet0/1<br>
PC1	10	192.168.10.2	255.255.255.0	FastEthernet0/2<br>
PC2	20	192.168.20.1	255.255.255.0	FastEthernet0/3<br>
PC3	20	192.168.20.2	255.255.255.0	FastEthernet0/4<br>
________________________________________
# Procedure
1.	Open Cisco Packet Tracer and add 4 PCs and 1 Switch.<br>
2.	Connect PC0–PC3 to switch ports FastEthernet0/1 to FastEthernet0/4 respectively.<br>
3.	Assign static IP addresses to each PC as per the IP table.<br>
4.	Enter the Switch CLI and create two VLANs:<br>
o	VLAN 10 for PC0 and PC1<br>
o	VLAN 20 for PC2 and PC3<br>
5.	Assign the respective switch ports to their VLANs.<br>
6.	Use the ping command from PC0 to PC1 (should succeed).<br>
7.	Try pinging from PC0 to PC2 (should fail — different VLANs).<br>
________________________________________
# Commands Used (Switch CLI)
bash<br>
CopyEdit<br>
Switch> enable<br>
Switch# configure terminal<br>

Switch(config)# vlan 10<br>
Switch(config-vlan)# name STAFF<br>
Switch(config-vlan)# exit<br>

Switch(config)# vlan 20<br>
Switch(config-vlan)# name STUDENTS<br>
Switch(config-vlan)# exit<br>

Switch(config)# interface range fastethernet0/1 - 2<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 10<br>
Switch(config-if-range)# exit<br>

Switch(config)# interface range fastethernet0/3 - 4<br>
Switch(config-if-range)# switchport mode access<br>
Switch(config-if-range)# switchport access vlan 20<br>
Switch(config-if-range)# exit<br>
________________________________________
# Output (Screenshots)
<img width="1918" height="1078" alt="Screenshot 2026-07-29 133641" src="https://github.com/user-attachments/assets/c23a1869-4151-4a06-8b1e-ca3204a1d302" />

<img width="1920" height="1080" alt="Screenshot 2026-07-29 133714" src="https://github.com/user-attachments/assets/d168c542-407f-4c33-a6fa-45527bbf7f15" />

<img width="1920" height="1080" alt="Screenshot 2026-07-29 133831" src="https://github.com/user-attachments/assets/b286e588-dcf7-4c75-828c-35feb55b4f23" />

<img width="1920" height="1080" alt="Screenshot 2026-07-29 134222" src="https://github.com/user-attachments/assets/e7208d78-72a6-4a62-9083-34a5bd7b597d" />

<img width="1920" height="1080" alt="Screenshot 2026-07-29 151658" src="https://github.com/user-attachments/assets/1f76128b-aba7-49b8-9ff6-f7f0f6a1555c" />



•	VLAN configuration on switch<br>
•	PC IP settings<br>
•	Successful ping between PCs in the same VLAN<br>
•	Failed ping between PCs in different VLANs<br>
________________________________________
# Result
Successfully created and configured VLANs on a managed switch. Verified that only PCs within the same VLAN could communicate with each other.

