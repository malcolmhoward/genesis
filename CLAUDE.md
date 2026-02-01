# CLAUDE.md - LLM Integration Guide

## Project Overview

**GENESIS** (GEneral Nexus for Experimental Software and Informative Scripts) is a collection of Python utilities for the O.A.S.I.S. wearable computing platform. It provides experimental tools for computer vision, camera integration, and hardware interaction on Raspberry Pi and NVIDIA Jetson platforms.

---

## Repository Structure

```
genesis/
├── pi_chatgpt_vision_trigger/    # Vision API GPIO controller
│   ├── pi_chatgpt_vision_trigger.py
│   └── README.md
├── jetson_rtsp_server/           # RTSP streaming server
│   └── rtsp_server.py
├── simple_picamera_hud.py        # Lightweight camera HUD
├── CLAUDE.md                     # This file
├── CONTRIBUTING.md               # Contribution guidelines
└── LICENSE                       # GPLv3
```

---

## Components

### Pi ChatGPT Vision Trigger

| Aspect | Details |
|--------|---------|
| Platform | Raspberry Pi |
| Dependencies | libcamera, pygame, OpenAI API |
| Purpose | Vision-based GPIO control via LLM |

Key features:
- Real-time image capture
- OpenAI Vision API integration
- Configurable GPIO triggers
- Rate limiting for API costs

### Jetson RTSP Server

| Aspect | Details |
|--------|---------|
| Platform | NVIDIA Jetson |
| Dependencies | GStreamer, NVIDIA encoders |
| Purpose | RTSP video streaming |

Key features:
- Multiple camera support (CSI, USB, ZED)
- H264 hardware encoding
- Configurable stream parameters

### Simple PiCamera HUD

| Aspect | Details |
|--------|---------|
| Platform | Raspberry Pi |
| Dependencies | picamera, pygame |
| Purpose | Lightweight camera display |

Key features:
- FPS counter, time overlay
- Resolution/rotation options
- Fullscreen toggle

---

## Working with This Codebase

### When Modifying Scripts

1. **Test on target hardware** - Pi scripts need Pi, Jetson scripts need Jetson
2. **Preserve API key handling** - Never hardcode credentials
3. **Maintain logging** - Keep comprehensive logging for debugging
4. **Consider resource limits** - Embedded systems have limited RAM/CPU

### Code Style

- Python 3.7+ compatible
- Use type hints where practical
- Document hardware-specific code
- Keep scripts self-contained where possible

### Common Tasks

| Task | Approach |
|------|----------|
| Add new utility | Create new script or directory with README |
| Modify GPIO handling | Update pin configurations, test on hardware |
| Change camera settings | Modify resolution/framerate parameters |
| Add API integration | Follow existing pattern for key handling |

---

## Hardware Considerations

### Raspberry Pi

- GPIO access requires root or gpio group membership
- Camera requires `libcamera` on newer Pi OS versions
- Display output may need framebuffer configuration

### NVIDIA Jetson

- GStreamer pipelines for video handling
- NVIDIA encoder plugins for hardware acceleration
- CSI cameras require specific driver configuration

---

## Integration Points

### O.A.S.I.S. Ecosystem

| Component | Relationship |
|-----------|--------------|
| **MIRAGE** | HUD concepts shared with simple_picamera_hud |
| **DAWN** | Vision trigger can interface with AI assistant |
| **AURA** | Jetson RTSP server can stream sensor data |

### S.C.O.P.E. Coordination

- **Meta-repo**: [malcolmhoward/the-oasis-project-meta-repo](https://github.com/malcolmhoward/the-oasis-project-meta-repo)
- **Documentation**: Aggregated in S.C.O.P.E. coordination docs

---

## Commands

```bash
# Pi ChatGPT Vision Trigger
cd pi_chatgpt_vision_trigger
python pi_chatgpt_vision_trigger.py

# Simple PiCamera HUD
python simple_picamera_hud.py

# Jetson RTSP Server
cd jetson_rtsp_server
python rtsp_server.py --camera csi --width 1920 --height 1080
```

---

## License

GENESIS is licensed under **GPLv3**. See LICENSE for details.

## Branch Naming Convention

**Critical**: Branch names must include the GitHub issue number being addressed.

### Format
```
feat/<component>/<issue#>-<short-description>
```

### Before Creating a Branch

1. **Identify the issue** you're working on (check GitHub Issues)
2. **Use that issue's number** in the branch name
3. **Verify** the issue number matches the work being done

### Examples
```bash
# Check available issues first
gh issue list --repo malcolmhoward/genesis

# Create branch with correct issue number
git checkout -b feat/genesis/<issue#>-description
```

### Common Mistake
❌ Using arbitrary numbers or the wrong issue number
✅ Always check `gh issue list` or GitHub Issues before creating a branch
