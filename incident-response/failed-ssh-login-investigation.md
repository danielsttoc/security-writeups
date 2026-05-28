# Failed SSH Login Investigation

## Overview

This writeup documents a basic incident investigation workflow focused on identifying and reviewing failed SSH login attempts within a Linux environment.

The goal was to practise:

- log analysis
- event investigation
- security monitoring
- troubleshooting workflows

## Scenario

A Linux server generated multiple failed SSH authentication attempts.

The objective was to identify:

- source IP addresses
- usernames targeted
- frequency of failed attempts
- indicators of brute-force behaviour

## Investigation Steps

### Review Authentication Logs

Used:

```bash
sudo journalctl -u ssh
```

and:

```bash
sudo grep "Failed password" /var/log/auth.log
```

to identify failed login attempts.

### Identify Source Addresses

Reviewed repeated IP addresses associated with failed attempts.

### Review Usernames

Checked whether attackers targeted:

- root
- default accounts
- service users

### Assess Severity

Looked for indicators such as:

- repeated failures in short timeframes
- multiple usernames from the same source
- scanning-style behaviour

## What I Learned

- Linux authentication log locations
- SSH troubleshooting basics
- Importance of centralized logging
- Basic brute-force indicators
- Structured investigation workflow

## Potential Improvements

- Forward logs into Splunk
- Create alerting rules
- Implement fail2ban
- Restrict SSH exposure
- Use key-based authentication

## Defensive Recommendations

- Disable password authentication where possible
- Restrict SSH access
- Use MFA where supported
- Monitor authentication logs regularly
- Apply least privilege principles
