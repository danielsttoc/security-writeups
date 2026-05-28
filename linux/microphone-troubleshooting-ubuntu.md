# Ubuntu Microphone Troubleshooting

## Overview

This writeup documents troubleshooting steps used while diagnosing a microphone detection issue on Ubuntu Linux where the microphone device was visible to the operating system but audio input was not functioning correctly.

## Environment

- Ubuntu 24.04
- PipeWire
- WirePlumber
- TONOR TC40 USB microphone
- AMD-based desktop system

## Initial Problem

Symptoms included:

- Microphone detected by the system
- No input audio activity
- Applications unable to capture voice input
- Device visible in PipeWire and PulseAudio tools

## Troubleshooting Steps

### Verify Device Detection

Used:

```bash
arecord -l
```

and:

```bash
pactl list short sources
```

to confirm the operating system detected the microphone.

### Check PipeWire Services

Verified PipeWire and WirePlumber were running correctly:

```bash
systemctl --user status pipewire
systemctl --user status wireplumber
```

### Monitor Audio Devices

Used:

```bash
wpctl status
```

and:

```bash
pavucontrol
```

to inspect active audio sources and confirm the correct microphone profile was selected.

### Restart Audio Services

Restarted PipeWire services:

```bash
systemctl --user restart pipewire pipewire-pulse wireplumber
```

## What I Learned

- Linux audio troubleshooting workflow
- PipeWire and WirePlumber basics
- Verifying hardware detection separately from application input
- Importance of checking services, profiles and source selection
- Structured troubleshooting methodology

## Future Improvements

- Investigate audio profile conflicts
- Test alternative kernel/audio configurations
- Explore advanced PipeWire debugging tools
