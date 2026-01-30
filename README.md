# Enterprise-Topology-Implementation
Technical design and implementation of a middle-scale Enterprise LAN. Focuses on network scalability, departmental isolation, and the deployment of core network services (DHCP/DNS/Web).

 📖 Project Overview
This project showcases a middle-scale Local Area Network (LAN) designed using a Star-Bus topology within Cisco Packet Tracer. The primary goal was to create a resilient, scalable, and manageable network environment for an enterprise with multiple operational segments.  
By leveraging a Star-Bus architecture, the design ensures that a failure in one workstation or "spoke" does not disrupt the entire network, while providing a centralized point for management and troubleshooting at the core. 

​🏗️ Network Architecture
​The network is logically divided into three primary segments connected via high-speed Gigabit Ethernet trunk links:  
​Core Segment: The backbone of the network, housing the Gateway Router, Enterprise Server (DNS, DHCP, Web), and the Administrator terminal.  
​Expansion Segment A: A dedicated area for general workstations (PC0, PC1, PC2), acting as a standard departmental access layer.  
​Expansion Segment B: A secure segment for sensitive departments (HR and Secretary), allowing for isolated traffic and specific Quality of Service (QoS) policies. 

🛠️ Implemented Services
​The Enterprise Server (192.168.1.10) provides three critical network services:  
​DHCP: Automatically assigns IP addresses from a pool of 51 addresses (.100 to .150) to workstations.  
​DNS: Provides centralized name resolution, allowing users to reach the intranet via the FQDN www.central.com.  
​HTTP: Hosts a localized company intranet landing page for internal communication and announcements.  

​🔐 Security Hardening
​To protect the network core, the Gateway Router has been hardened with the following measures:
​Privileged Exec Security: An encrypted Enable Secret password to prevent unauthorized administrative changes.  
​Console & VTY Security: Password protection for both physical console access and remote management (Telnet/SSH).  
​Global Encryption: The service password-encryption command is active to obfuscate all plain-text passwords within the configuration files. 

✅ Connectivity Verification
The following tests were performed to validate the design:  
ICMP Echo (Ping): Verified end-to-end connectivity between departments (e.g., PC0 to PC-HR) and access to the gateway.  
Service Validation: Confirmed that the PC-Secretary could successfully resolve www.central.com and load the HTTP intranet page.  
Inter-Segment Routing: Monitored traffic flow through the router to ensure proper distribution across different broadcast domains. 
