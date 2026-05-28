# Splunk MikroTik Log Monitoring

## Overview

This writeup documents how I configured MikroTik syslog forwarding into Splunk within my Proxmox homelab environment to practise centralized logging, monitoring and basic SIEM workflows.

## Technologies Used

- Proxmox
- Debian Linux
- Splunk Enterprise
- MikroTik hEX S
- Syslog
- Docker

## Objective

The goal of this project was to:

- Centralize router logs
- Improve network visibility
- Practise SIEM-style workflows
- Investigate network and authentication events
- Learn log filtering and search queries

## Environment

- Splunk running inside a Debian LXC container
- MikroTik configured to forward syslog events
- Internal LAN with Docker-based services
- Pi-hole used for DNS filtering

## Key Learning Areas

### Syslog Integration

Configured MikroTik logging actions to forward logs directly into Splunk for centralized ingestion.

### Search Queries

Practised using:

```spl
index=main sourcetype=syslog
```

to filter router-generated logs and review network events.

### Monitoring and Visibility

Learned how centralized logs improve troubleshooting and security visibility by allowing multiple systems to be monitored from one location.

## What I Learned

- Basic SIEM workflows
- Log ingestion pipelines
- Search and filtering in Splunk
- Network troubleshooting through logs
- Importance of centralized monitoring
- Visibility into router-generated events

## Future Improvements

- Create custom alerts
- Simulate failed login attempts
- Build dashboards for authentication monitoring
- Add threat detection logic
- Expand logging to additional systems
