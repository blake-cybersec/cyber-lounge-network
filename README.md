
# Cyber Lounge Network
## _A Live Network used for a College Class Room_


Cyber Lounge Network is a comprehensive network configuration project focusing on Cisco devices, Dell servers and virtualization software, tailored to meet diverse computing and networking needs. Central to the design is the deployment of Cisco 1941 Series Routers. These routers are acclaimed for their robust security features and efficient traffic management, ensuring reliable and secure network operations. Complementing these routers are the Cisco Catalyst 2960-X Series Switch. Known for their scalability and energy efficiency, these switch facilitate streamlined network management and adaptability to evolving network demands.

At the core of the network architecture is a Dell rack server, serving as the primary platform for a variety of virtualized environments. This server runs on Proxmox, a cutting-edge open-source platform equipped with a Level 1 hypervisor. This setup offers a user-friendly interface and optimizes the performance of the virtual machines it manages. Among the virtualized environments, there is a Windows Server 2019 VM, which supports crucial Windows-based applications and services. In parallel, an Ubuntu server VM hosts a Nextcloud environment, providing a secure, private cloud access system. Additionally, the network includes a Security Onion ELK stack on Proxmox, enhancing the network's monitoring capabilities. This stack is pivotal for real-time network security surveillance and analysis, contributing significantly to the overall health and security of the network. This project, thus, represents a comprehensive, scalable, and secure network infrastructure, capable of supporting a wide range of tasks and workflows in a dynamic computing environment.






![Network](https://i.imgur.com/S3HlhDa.png)

---

## Cisco Router Configuration
Here are some basic commands and configurations for Cisco 1941 Series Routers:

### Factory Reset
```bash
router> enable
router# write erase
router# reload
```
_Ask "no" to any prompted questions during reload._

### Base Configuration
```bash
enable
configure terminal
hostname <insert hostname>
interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
ip default-gateway 192.168.1.254
```
_Replace `<insert hostname>` with your desired hostname, e.g., `hostname R1`._

### Configure DHCP
```bash
enable
configure terminal
service dhcp
ip dhcp pool <insert pool name>
network 192.168.1.0 255.255.255.0
default-router <router IP address>
dns-server <dns server ip address>
```
_Ensure to replace placeholders with actual values._

---

## Cisco Switch Configuration

This document provides configuration details and commands for Cisco Catalyst 2960-X Series Switches.

## Base Configurations


```
enable
configure terminal
hostname <hostname>
interface vlan 1
ip address 192.168.1.2 255.255.255.0
no shutdown
interface g1/0/1
switchport mode access
switchport access vlan 1
```
_Ensure to replace placeholders with actual values._

## Factory Reset

1. Connect to the switch using a console cable and terminal emulation software such as PuTTY or HyperTerminal.
2. Power on the switch.
3. During the boot-up process, press and hold the "Mode" button until the "SYST LED" turns solid green.
4. Release the "Mode" button and wait for the switch to finish booting up.
5. Once the switch has finished booting up, enter the following command: `erase startup-config` and press enter.
6. You will be prompted to confirm the action. Type `yes` and press enter.
