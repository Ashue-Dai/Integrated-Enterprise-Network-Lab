🏢 Integrated Enterprise Network Lab

📌 Project Overview
This project demonstrates a segmented enterprise network using GNS3.  
The goal is to simulate standard corporate IT infrastructure with VLAN segmentation, inter-VLAN routing, DHCP configuration, and server deployment.

📄 [Project Report](Screenshots/Docs/Integrated_Enterprise_Report.pdf)

🏗️ [Topology](Screenshots/topology.png)

* Routers: Inter-VLAN routing & subinterfaces  
* Switches: VLAN segmentation & trunking  
* Servers: DNS, Web, FTP  
* PCs: Client devices for testing connectivity  

⚙️ Tools Used
* GNS3 (Network simulation)  
* Cisco Router Images (IOSv)  
* Switches (vIOS-L2)  
* Windows/Linux VMs for server farm  

📝 Configurations

🔹 VLAN & Switch Configuration
* VLANs: 10, 20, 30, 35, 99, 100  
* Switchports assigned to respective departments  
* 802.1Q trunk ports configured  
  - [VLAN Config](Screenshots/sw1vlan_config.png)  
  - [VLAN Config](Screenshots/sw2vlan_config.png)  
  - [VLAN Config](Screenshots/sw3vlan_config.png)  

🔹 Router / Inter-VLAN Routing
* Subinterfaces on routers configured for VLAN routing  
* Routing enabled between all internal VLANs  
* Guest VLAN isolated with ACLs  
  - [Routing Config](Screenshots/routing_config.png)  
* Subinterfaces on routers configured for VLAN routing  
* Routing enabled between all internal VLANs  
* Guest VLAN isolated with ACLs  
* Access Control Lists (ACLs) implemented:  
  - VLAN 10 & 20 cannot access the server farm  
  - VLAN 99 cannot access any other VLAN  
  - [Routing Config](Screenshots/vlan10&20acl_config.png)  
  - [Routing Config](Screenshots/R1vlan99acl_config.png)  
  - [Routing Config](Screenshots/R2vlan99acl_config.png)  

🔹 DHCP Configuration
* DHCP pools created for dynamic VLANs  
* Static IPs reserved for servers and management devices  
* ip helper-address configured where DHCP is centralized  
  - [DHCP Config](Screenshots/dhcp_config.png)  

🔹 Connectivity Test
* Ping and file transfer tested between VLANs and servers  
  - [Connectivity Test](Screenshots/pc1connectivity_test.png)  
  - [Connectivity Test](Screenshots/pc2connectivity_test.png)  
  - [Connectivity Test](Screenshots/pc3connectivity_test.png)  
  - [Connectivity Test](Screenshots/winserverconnectivity_test.png)  
  - [Connectivity Test](Screenshots/pc4connectivity_test.png)  
  - [Connectivity Test](Screenshots/pc5connectivity_test.png)  

🔄 Results / Observations
* VLAN segmentation successfully isolates departments  
* Inter-VLAN routing enables communication where allowed  
* Guest VLAN remains isolated after  
* DHCP pools dynamically assign IP addresses correctly  
* Server farm accessible by authorized VLANs only  

✅ Advantages
- Clear VLAN segmentation improves network organization and security  
- Inter-VLAN routing ensures controlled communication between departments  
- DHCP pools simplify IP address management  
- Server farm setup (DNS, Web, FTP) provides realistic enterprise simulation  
- Easy to expand for additional services or devices in the future  

⚠️ Problems Faced / Challenges
- Linux Web Server & Ubuntu FTP Server Connectivity: Could not connect to main network despite multiple reinstallations. Working on resolving interface and routing issues.  
- pfSense Installation: Only one interface was active; adding a second interface failed, so the full firewall setup was not completed.  
- General GNS3 challenges: Ensuring proper routing and trunk configurations between multiple VLANs and devices.  

 

 Author:  Ashue-Dai  
 LinkedIn: [https://www.linkedin.com/in/ashue-daisy-1b6b88294](https://www.linkedin.com/in/ashue-daisy-1b6b88294)  
 Email: ashuedaisy9@gmail.com  

