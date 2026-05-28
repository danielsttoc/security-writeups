# Docker Hardening Notes

## Overview

These notes document security concepts and hardening practices learned while working with Docker containers and completing SecureFlag Docker security labs.

## Why Docker Security Matters

Containers share the host kernel, meaning insecure configurations may allow attackers to:

- Escape containers
- Access sensitive host resources
- Abuse mounted volumes
- Escalate privileges
- Expose internal services

## Common Risks

### Exposed Docker Socket

Mounting:

```bash
/var/run/docker.sock
```

inside containers may allow administrative access to the Docker daemon.

### Privileged Containers

Using:

```bash
--privileged
```

can significantly weaken isolation between the container and host.

### Excessive Port Exposure

Exposing unnecessary ports increases attack surface.

### Running as Root

Containers running as root may increase the impact of exploitation.

## Hardening Practices

### Use Least Privilege

Avoid privileged containers unless absolutely required.

### Limit Port Exposure

Only expose services that are necessary.

### Use Non-Root Users

Where possible, configure containers to run with restricted permissions.

### Keep Images Updated

Use maintained base images and apply updates regularly.

### Monitor Logs

Review container logs for abnormal behaviour and troubleshooting.

## What I Learned

- Risks associated with insecure container configurations
- Importance of secure defaults
- Docker isolation limitations
- Practical container security concepts
- Basic secure DevOps principles

## Future Improvements

- Explore Falco runtime monitoring
- Learn container vulnerability scanning
- Integrate container logging into Splunk
- Practise Kubernetes security concepts
