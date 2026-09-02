Secure Small-Business Network Design & Security Lab

📌 Project Overview

This project demonstrates the design and implementation of a segmented and security-focused small-business network using Cisco Packet Tracer.

The network was designed for a fictional organization, JHAYYS DIGITAL SERVICES, with separate network segments for Staff, Guest users, IT/Admin, and Servers.

The project focuses on network segmentation, access control, secure management, DHCP, inter-VLAN routing, and security validation.

⸻

🏗️ Network Architecture

Core Router → Core Switch → Access Switch

Network Components

* Cisco 2911 Core Router
* Cisco 2960 Core Switch
* Cisco 2960 Access Switch
* Staff workstations
* IT/Admin workstations
* Guest workstations
* Internal server

⸻

🔐 VLAN Design

VLAN	Name	Network	Gateway
10	STAFF	192.168.10.0/24	192.168.10.1
20	GUEST	192.168.20.0/24	192.168.20.1
30	IT-ADMIN	192.168.30.0/24	192.168.30.1
40	SERVERS	192.168.40.0/24	192.168.40.1

⸻

🛡️ Security Controls

VLAN Segmentation

Separate VLANs were implemented to isolate Staff, Guest, IT/Admin, and Server traffic.

Access Control Lists

ACLs were configured to enforce the following security policy:

* ✅ Staff → Servers: Allowed
* ❌ Staff → IT/Admin: Blocked
* ✅ IT/Admin → Servers: Allowed
* ❌ Guest → Servers: Blocked
* ❌ Guest → IT/Admin: Blocked
* ✅ Guest → Internet: Permitted by policy

Secure Network Management

SSH was configured on:

* Core Router
* Core Switch
* Access Switch

Management access was restricted to the IT/Admin VLAN.

Telnet was disabled by allowing SSH-only VTY access.

⸻

🌐 Routing & DHCP

Router-on-a-stick was implemented on the Core Router using 802.1Q subinterfaces.

The router provides DHCP services for:

* STAFF
* GUEST
* IT-ADMIN

The server uses a static IP address:

192.168.40.10

⸻

🧪 Security Validation

Connectivity tests were performed to verify the security controls.

Successful Tests

* Staff → Server
* IT/Admin → Server
* IT/Admin → Core Router via SSH
* IT/Admin → Core Switch via SSH
* IT/Admin → Access Switch via SSH

Blocked Tests

* Guest → Server
* Guest → IT/Admin
* Staff → IT/Admin
* Guest → Core Router SSH
* Guest → Core Switch SSH
* Guest → Access Switch SSH

ACL match counters were also reviewed to confirm that the configured restrictions were actively processing traffic.

⸻

📸 Evidence

Screenshots documenting the implementation and testing are included in the project documentation.

Evidence includes:

* Network topology
* VLAN configuration
* Trunk configuration
* Router subinterfaces
* DHCP assignments
* ACL configuration and hit counters
* SSH management testing
* Successful connectivity tests
* Blocked connectivity tests

⸻

🧠 Skills Demonstrated

* Cisco Packet Tracer
* VLAN configuration
* 802.1Q trunking
* Router-on-a-stick
* Inter-VLAN routing
* DHCP
* Extended ACLs
* Network segmentation
* SSH configuration
* Secure network management
* Network troubleshooting
* Security validation
* Technical documentation

⸻

🎯 Lessons Learned

This lab provided practical experience designing a network around least-privilege access and segmentation rather than relying solely on connectivity.

Testing both permitted and denied traffic demonstrated how network security controls can be validated using observable results rather than configuration alone.

⸻

⚠️ Disclaimer

This project was created entirely in a simulated Cisco Packet Tracer environment for educational and portfolio purposes.
