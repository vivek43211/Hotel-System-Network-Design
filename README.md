# 🏨 Hotel Management Network Configuration Project

## 📝 Case Study and Requirements
As a part of your end year networking project, you are required to design and implement Vic Modern Hotel network. The hotel has three floors; in the first floor there three departments (Reception, store and Logistics), in the second floor there are three departments (Finance, HR and Sales/Marketing), while the third floor hosts the IT and Admin. Therefore, the following are part of the considerations during the design and implementation;
There should be three routers connecting each floor (all placed in the server room in IT department).
All routers should be connected to each other using serial DCE cable.
The network between the routers should be 10.10.10.0/30,10.10.10.4/30 and 10.10.10.8/30.
Each floor is expected to have one switch (placed in the respective floor).
Each floor is expected to have WIFI networks connected to laptops and phones.
Each department is expected to have a printer.
Each department is expected to be in different VLAN with the following details;
1st Floor;
- Reception- VLAN 80, Network of 192.168.8.0/24
- Store- VLAN 70, Network of 192.168.7.0/24
- Logistics- VLAN 60, Network of 192.168.6.0/24
2nd Floor;
- Finance- VLAN 50, Network of 192.168.5.0/24
- HR- VLAN 40, Network of 192.168.4.0/24
- Sales- VLAN 30, Network of 192.168.3.0/24
3rd Floor;
- Admin- VLAN 20, Network of 192.168.2.0/24
- IT- VLAN 10, Network of 192.168.1.0/24

Use OSPF as the routing protocol to advertise routes.
All devices in the network are expected to obtain IP address dynamically with their respective router configured as the DHCP server.
All the devices in the network are expected to communicate with each other.
Configure SSH in all the routers for remote login.
In IT department, add PC called Test-PC to port fa0/1 and use it to test remote login.
Configure port security to IT-dept switch to allow only Test-PC to access port fa0/1 (use sticky method to obtain mac-address with violation mode of shutdown.)

## 📘 Overview
This project demonstrates the design and configuration of a **Hotel Management Network** using industry-standard Cisco technologies. It focuses on secure, segmented communication between departments while integrating wireless access for mobility and scalability.

---

## 📌 Project Objectives

- Design a functional, secure network for hotel operations.
- Implement inter-department communication using VLANs and OSPF routing.
- Enable secure remote access using SSH.
- Automate IP address distribution using DHCP.
- Provide wireless connectivity through Cisco Access Points.
- Configure port security to prevent unauthorized access.

---

## 🧩 Technologies Implemented

| Technology         | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Serial Interface** | Used for WAN inter-router communication.                                  |
| **Port Security**    | Applied on switches to prevent MAC spoofing and unauthorized devices.     |
| **SSH (Secure Shell)** | Enabled for secure remote configuration access.                          |
| **OSPF (Open Shortest Path First)** | Dynamic routing protocol implemented between routers.           |
| **DHCP**             | Configured on routers to assign dynamic IPs to host devices.              |
| **Access Points**    | Provide wireless connectivity to tablets and smartphones.                 |

---

## 🏢 VLAN Segmentation

| VLAN ID | Department         | Subnet             | Devices Included                                 |
|--------:|--------------------|---------------------|--------------------------------------------------|
| 10      | IT                 | 192.168.1.0/24       | PCs, Laptops, Printers, Wireless Devices         |
| 20      | Admin              | 192.168.2.0/24       | PCs, Printers                                    |
| 30      | Sales              | 192.168.3.0/24       | PCs, Printers, Access Points                     |
| 40      | HR                 | 192.168.4.0/24       | PCs, Printers                                    |
| 50      | Finance            | 192.168.5.0/24       | PCs, Printers                                    |
| 60      | Logistics          | 192.168.6.0/24       | PCs, Printers, Wireless Devices                  |
| 70      | Store              | 192.168.7.0/24       | PCs, Printers                                    |
| 80      | Reception          | 192.168.8.0/24       | PCs, Printers                                    |

---

## 🌐 Router Configuration Highlights

- **OSPF Configuration**
  - All routers participate in OSPF Area 0.
  - Loopback interfaces used as Router IDs.
- **DHCP Configuration**
  - Routers configured as DHCP servers for specific VLANs.
- **SSH Configuration**
  - Routers secured with local usernames and SSH enabled.

---

## 🔐 Security Features

- **Port Security**
  - MAC address filtering (Sticky) enabled on floor-3 switch edge ports so only F0/2.
  - Violation mode: shutdown.
- **SSH Access**
  - Only authorized admin can access router remotely.
  - Password and encryption enabled for secure sessions.

---

## 📶 Wireless Integration

- Cisco Access Points provide wireless access per floor:
  - Floor 1, 2, and 3 covered.
  - Devices like smartphones and tablets connected.
- APs are VLAN-aware and provide DHCP-relayed IPs.

---

## 🗺️ Network Topology

![Hotel Management Network Topology](./Hotel%20managment%20network%20project.png)

