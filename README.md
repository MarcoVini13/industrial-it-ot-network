# Industrial IT/OT Network Topology & Security Simulation
## 📌 Project Overview
This repository contains a professional simulation of a secure manufacturing plant network architecture designed in Cisco Packet Tracer. The primary objective is to demonstrate robust IT/OT convergence, network segmentation, inter-VLAN routing, and industrial cybersecurity practices tailored for modern automated manufacturing environments (such as automotive assembly plants).

🏗️ Architecture & Network Design
The topology simulates a complete industrial plant infrastructure, segregating corporate administrative traffic from critical operational technology (OT) and enterprise servers.
Network Scheme: Class A IP addressing (`10.0.0.0/24`)
Routing Device: Cisco ISR 4331 Integrated Services Router (`Router0`)
Switching Device: Cisco Catalyst 2960 Layer 2 Switch (`Switch0`)
VLAN Segmentation & Addressing Table
| VLAN ID | Name | Subnet / Mask | Gateway | Assigned Devices | Description |
| 10 | `Administracion\_IT` | `10.0.10.0/24` | `10.0.10.1` | PC0, PC1 | Corporate & IT Administration offices |
| 20 | `Linea\_Ensamble\_OT` | `10.0.20.0/24` | `10.0.20.1` | MCU0 (Microcontroller) | Operational Technology / Assembly line automation |
| 30 | `Servidores\_Corp` | `10.0.30.0/24` | `10.0.30.1` | Server0 (Database/ERP) | Enterprise servers and core databases |
| 99 | `Management` | `10.0.99.0/24` | `10.0.99.1` | Switch / Router interfaces | Native VLAN / Out-of-band management |

⚙️ Key Technical Implementations
Inter-VLAN Routing (Router-on-a-Stick):
Configured physical interface `GigabitEthernet0/0/1` on the router as an 802.1Q trunk link.
Established logical subinterfaces (`.10`, `.20`, `.30`, `.99`) to handle gateway routing across isolated VLAN segments.
Industrial Cybersecurity (Access Control Lists - ACLs):
Implemented standard/extended IP access control lists (ACL `100`) on the core router.
Zone Isolation Rule: Explicitly blocked unauthorized traffic from the IT administration network (`10.0.10.0/24`) into the critical OT assembly line network (`10.0.20.0/24`), protecting industrial machinery assets while preserving corporate connectivity.

Hardware Integration:
Configured modular IoT microcontrollers (`MCU-PT`) with FastEthernet modules (`PT-IOT-NM-1CFE`) to simulate smart factory sensors/actuators integrated into the industrial network.
🚀 How to Open and Run the Simulation
1. Ensure you have Cisco Packet Tracer installed on your system.
2. Clone or download this repository.
3. Open the `.pkt` project file inside Packet Tracer.
4. Use the CLI of `Router0` or `Switch0` to review running configurations (`show running-config`).
5. Use the Command Prompt on `PC0` or `PC1` to test connectivity or verify ACL security rules (`ping 10.0.20.50`).

Developed by Marco Vinicio (IT Engineering Student at UPSLP) as part of an industrial portfolio targeting automotive IT/OT infrastructure roles.
