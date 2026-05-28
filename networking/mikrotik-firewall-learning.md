# MikroTik Firewall Learning

## Overview

This writeup documents my learning while configuring and troubleshooting a MikroTik hEX S router in my homelab network.

The aim was to improve my understanding of routing, firewall rules, NAT, DNS, DHCP and general network security concepts through practical configuration and troubleshooting.

## Environment

- MikroTik hEX S router
- LAN subnet: `192.168.88.0/24`
- Pi-hole used as DNS server
- Proxmox host running multiple services
- Docker-based media and monitoring stack
- Splunk used for syslog monitoring

## Key Areas Practised

### DHCP and DNS

Configured the MikroTik router to provide DHCP while pointing clients toward Pi-hole for DNS filtering.

This helped me understand the relationship between:

- DHCP leases
- DNS servers
- Client network configuration
- Internal hostname resolution

### NAT

Worked with NAT rules to allow internal clients to reach the internet while keeping internal services separated from direct exposure.

### Firewall Rules

Practised reviewing firewall behaviour and understanding how rules affect traffic flow between clients, services and the internet.

### Troubleshooting Connectivity

Used tools such as:

```bash
ping
traceroute
nslookup
dig
curl
ip a
```

to troubleshoot DNS, routing and service access issues.

## Security Lessons Learned

- Router configuration has a direct impact on security and availability
- DNS and DHCP misconfiguration can break client connectivity
- Firewall rules should be reviewed carefully before changes are applied
- Logging is important for visibility and troubleshooting
- Small network changes should be tested step-by-step

## What I Would Improve Next

- Build a cleaner firewall rule baseline
- Create a network diagram
- Document important NAT rules
- Forward more logs into Splunk
- Practise VLAN segmentation in a controlled way

## Interview Talking Point

This project gave me practical networking experience beyond university coursework by forcing me to troubleshoot real routing, DNS and firewall behaviour inside my own network.
