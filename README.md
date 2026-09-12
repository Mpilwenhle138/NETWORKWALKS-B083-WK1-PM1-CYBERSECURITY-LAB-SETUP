# NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
A setup of cybersecurity testing lab using host Visual Box to set up Kali Linux

# 🔐 Cybersecurity Virtual Lab

This project documents how I created a small virtual environment where I can safely learn networking, reconnaissance, vulnerability assessment, and penetration-testing concepts.

 #Project Overview

The goal of this project is to build a simple cybersecurity lab on a Windows computer.

The lab uses a virtual machine running Kali Linux and a private VirtualBox network. This allows me to practice cybersecurity skills without directly affecting my main operating system.

The setup can also be expanded later by adding other virtual machines as testing targets.

Similar GitHub projects commonly use Kali Linux with VirtualBox, isolated virtual networks, vulnerable target machines, and snapshots for safe experimentation.

---

## 🎯 Objectives

The main objectives of this project are to:

* Install VirtualBox.
* Install or import Kali Linux.
* Create a private virtual network.
* Configure Kali Linux networking.
* Assign a static IP address.
* Test network connectivity.
* Test DNS and internet access.
* Create a clean VM snapshot.


## 🖥️ Lab Environment

| Component             | Configuration        |
| --------------------- | -------------------- |
| Host Operating System | Windows 11           |
| Host RAM              | 20 GB                |
| Processor             | Intel Core i5        |
| Hypervisor            | VirtualBox 7.2       |
| Security VM           | Kali Linux           |
| Kali RAM              | 2048 MB              |
| Kali CPU              | 2 cores              |
| Network Type          | NAT Network          |
| Network               | 10.0.0.0/24          |
| Kali IP               | 10.0.0.2             |
| Gateway               | 10.0.0.1             |
| DNS                   | 10.0.0.1 / 8.8.8.8   |
| Future VM Range       | 10.0.0.3 – 10.0.0.99 |

---

# 🏗️ Lab Design

The basic lab looks like this:

```text
                 INTERNET
                    │
                    │
             ┌──────▼──────┐
             │  VirtualBox │
             │  NAT Network │
             │ 10.0.0.0/24 │
             └──────┬──────┘
                    │
              ┌─────▼─────┐
              │   Kali    │
              │  Linux    │
              │ 10.0.0.2  │
              └───────────┘
                    │
          Future Target Machines
          10.0.0.3 - 10.0.0.99
```

The idea is to keep the cybersecurity exercises inside the virtual environment.

---

# 🛠️ Tools Used

* VirtualBox
* Kali Linux
* 7-Zip
* Linux Terminal
* NetworkManager
* Ping
* Web browser

---

# 🚀 Lab Setup

## 1. Install 7-Zip

I installed 7-Zip so that I could extract the Kali Linux virtual machine files.

---

## 2. Install VirtualBox

I installed VirtualBox on my Windows 11 computer.

VirtualBox allows me to create and run virtual machines without replacing my main operating system.

---

## 3. Create the Virtual Network

I created a NAT Network in VirtualBox.

### Network Configuration

```text
Network Name: NatNetwork
IPv4 Network: 10.0.0.0/24
DHCP: Enabled
IPv6: Disabled
```

---

## 4. Import Kali Linux

I downloaded the Kali Linux virtual machine and imported it into VirtualBox.

The VM was configured with:

```text
CPU: 2 cores
RAM: 2048 MB
Network Adapter: Adapter 1
Network Type: NAT Network
Network Name: NatNetwork
```
<img src="IP Address.png" alt="IP Address" >


## 5. Configure Kali Linux Networking

I configured Kali Linux with a static IP address.


IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 10.0.0.1
Secondary DNS: 8.8.8.8
`
<img src="Kali Linux Desktop.png" alt="Kali Linux Desktop">


# 🌐 DNS Troubleshooting

One problem I experienced was that the Kali VM could ping Google's IP address but could not properly access websites.

This showed that the basic network connection was working, but DNS resolution was not working correctly.

I changed the DNS configuration and added:

```text
8.8.8.8
```

as a secondary DNS server.

After switching the network connection off and on again, I tested the connection.

The browser was then able to access websites such as Google and YouTube.

---

# 💾 VM Snapshot

After completing the basic configuration, I created a VirtualBox snapshot.

The snapshot provides a restore point for the lab.

For example:

```text
Clean Kali Setup
       │
       ▼
   Snapshot
       │
       ▼
Cybersecurity Exercises
       │
       ▼
Something Goes Wrong
       │
       ▼
Restore Snapshot
```

This is useful because I can experiment without worrying about permanently breaking the original setup.

---



Possible learning activities include:

* Network discovery
* Port scanning
* Service enumeration
* Vulnerability assessment
* Web application security
* Packet analysis
* Log analysis
* Basic exploitation in an authorized environment
* System hardening


---

# 📚 What I Learned

## Virtual Machines

I learned that a virtual machine allows me to run another operating system inside my computer.

This is useful for cybersecurity because I can create separate environments for testing.

## Virtual Networking

I learned how VirtualBox networking allows virtual machines to communicate with each other and, when configured appropriately, access the internet.

## Static IP Addresses

I learned how to give a virtual machine a fixed IP address.

This makes it easier to identify the machine during future lab exercises.

## DNS

I learned that DNS changes domain names such as:

```text
google.com
```

into IP addresses that computers can use.

I also learned that a computer can have internet connectivity while still having DNS problems.

## Snapshots

I learned that snapshots are useful before performing experiments.

If something goes wrong, the VM can be restored to its previous state.

## Troubleshooting

I learned that troubleshooting a network problem should be done step by step:

```text
1. Check network adapter
        ↓
2. Check IP address
        ↓
3. Check gateway
        ↓
4. Ping gateway
        ↓
5. Ping external IP
        ↓
6. Test DNS
        ↓
7. Test browser
```

---

# 🔗 Resources

* 7-Zip
* VirtualBox
* Kali Linux
* VirtualBox documentation
* Kali Linux documentation

---

# 👤 Author

**Mpilwenhle Sibibi**

Cybersecurity Intern – B083

LinkedIn: [www.linkedin.com/in/mpilwenhle-sibibi-7b40bb233](http://www.linkedin.com/in/mpilwenhle-sibibi-7b40bb233)

---

# 📅 Project Information

| Information   | Details                       |
| ------------- | ----------------------------- |
| Program       | Cybersecurity at Networkwalks |
| Project       | Cybersecurity Virtual Lab     |
| Week          | 01                            |
| Level         | Beginner                      |
| Main Platform | VirtualBox                    |
| Security OS   | Kali Linux                    |

---

## ⭐ Conclusion

This project gave me a practical introduction to building a cybersecurity laboratory.

I learned how to create a virtual machine, configure networking, troubleshoot DNS, use snapshots, and document my work.

The lab can now be expanded with additional virtual machines and security exercises as I continue learning cybersecurity.
