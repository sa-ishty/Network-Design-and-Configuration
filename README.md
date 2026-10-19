# Network Design and Configuration

Hands-on networking labs from my BSc in CSE (Networking major) at American International University-Bangladesh (AIUB), built and tested in **Cisco Packet Tracer**. They go from a direct PC-to-PC link up to multi-switch VLAN networks with inter-VLAN routing, static routing, DHCP, application servers and SSH-secured devices.

## Skills shown

- **Switching:** VLANs, trunk links (802.1Q), access ports, switch management interface
- **Routing:** inter-VLAN routing (router-on-a-stick), static routing between multiple routers
- **IP services:** DHCPv4, stateless and stateful DHCPv6, DNS, web and email servers
- **Addressing:** IPv4 subnetting and VLSM, IPv6 addressing
- **Device security:** enable secret, console/VTY passwords, local user database, password encryption, SSH v2 only access, MOTD banners
- **Operations:** saving and backing up configs (startup-config, TFTP), verifying with `show` commands

## Labs

### Computer Networks lab report ([`CN Lab Report.docx`](CN%20Lab%20Report.docx))

| Lab | Experiment |
|---|---|
| 1 | Direct connection between 2 PCs |
| 1 | 3 PCs connected through a hub |
| 1 | Two hubs connected together |
| 2 | Two switch networks connected through a bridge |
| 2 | Two switch networks connected through a router (two subnets) |
| 3 | Router-connected networks with a DHCP server, dynamic and static addressing |
| 3 | Wired and wireless clients on a Wi-Fi router |
| 3 | Two routers, each with its own PCs and switch network |
| 4 | Three routers (including a Wi-Fi router) connected with static routing |

### Final lab report ([`CN_final lab report .docx`](CN_final%20lab%20report%20.docx))

| Lab | Experiment |
|---|---|
| 1 | DHCP, web, DNS and email servers in a two-switch LAN |
| 1 | Three VLANs across two switches with inter-VLAN routing |
| 2 | Four VLANs across three switches with inter-VLAN routing |
| 2 | Controlling IoT devices remotely with addresses from a DHCP server |

Example: router-on-a-stick for three VLANs (from the final lab report)

```text
! Switch0
vlan 10
vlan 20
vlan 30
interface fa0/1
 switchport mode trunk
interface range fa0/3 - 4
 switchport mode access
 switchport access vlan 10
interface range fa0/5 - 6
 switchport mode access
 switchport access vlan 20

! Router
interface fa0/0
 no shutdown
interface fa0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
interface fa0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
interface fa0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0
```

### CCNA practice ([`ccna/`](ccna))

| File | What it covers |
|---|---|
| [`Basic_config_IMPORTANT.txt`](ccna/Basic_config_IMPORTANT.txt) | Step-by-step baseline router hardening and IPv4/IPv6 addressing |
| [`Router-Config.txt`](ccna/Router-Config.txt) | Router setup with local user database and in-band authentication |
| [`switch-config.txt`](ccna/switch-config.txt) | Router and switch setup, SSH v2 only access, config backup to TFTP |
| [`DHCP.txt`](ccna/DHCP.txt) | DHCPv4 pool, stateless and stateful DHCPv6, with verification output |
| [`dhcp.pkt`](ccna/dhcp.pkt), [`pratice-ccna1.pka`](ccna/pratice-ccna1.pka), [`ccna1sm (2).pka`](ccna/ccna1sm%20(2).pka) | Packet Tracer files (open with Cisco Packet Tracer) |
| [`vlsm_practice.doc`](ccna/vlsm_practice.doc), [`vlsm_practice_solution.pdf`](ccna/vlsm_practice_solution.pdf) | VLSM subnetting practice and solution |
| [`ipv6_is_easy.pdf`](ccna/ipv6_is_easy.pdf), [`wireshark.pdf`](ccna/wireshark.pdf) | IPv6 and Wireshark study notes |

The passwords in these practice files are classroom lab examples, not real credentials.

## Tools

Cisco Packet Tracer · Cisco IOS CLI · Wireshark

## Author

**Shahriar Adnan Ishty**, BSc in Computer Science and Engineering (Networking), AIUB · Network Engineer Intern, AIUB IT Department · [LinkedIn](https://www.linkedin.com/in/shahriar-adnan-ishty-382028196/)
