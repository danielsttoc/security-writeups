# Pi-hole DNS Filtering

## Overview

This project documents my experience deploying and managing Pi-hole within my homelab environment for DNS-based ad and tracking blocking.

The objective was to improve privacy, visibility and network-wide filtering while learning more about DNS infrastructure and troubleshooting.

## Environment

- Pi-hole running on Linux
- MikroTik router providing DHCP
- Pi-hole configured as primary DNS server
- Internal LAN with multiple Linux and Docker services

## Key Features

- Network-wide DNS filtering
- Advertisement and tracker blocking
- DNS query visibility
- Local DNS entries for internal services
- Integration with homelab infrastructure

## What I Learned

### DNS Fundamentals

Improved understanding of:

- DNS requests
- Recursive lookups
- Local DNS resolution
- DNS-based filtering
- Client DNS behaviour

### Blocklists

Configured and managed multiple DNS blocklists to improve filtering coverage.

### Local DNS Records

Created local DNS records for internal services such as:

- Jellyfin
- Dashy
- Proxmox
- Pi-hole

This improved usability and helped simulate enterprise-style internal name resolution.

### Troubleshooting

Used tools such as:

```bash
nslookup
dig
ping
curl
```

to troubleshoot DNS resolution and service access.

## Security Benefits

- Reduced tracking and advertising traffic
- Improved visibility into DNS requests
- Better understanding of network behaviour
- Centralized DNS management

## Future Improvements

- Add DNS-over-HTTPS
- Expand logging and monitoring
- Integrate additional alerting
- Explore DNS security monitoring in Splunk
