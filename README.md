# GENESIS

**GEneral Nexus for Experimental Software and Informative Scripts** - Python utilities for computer vision, camera integration, and hardware interaction for the O.A.S.I.S. wearable computing platform.

## Overview

GENESIS is a collection of experimental software tools and informative scripts focused on computer vision, camera integration, and hardware interaction for Raspberry Pi and NVIDIA Jetson platforms. The repository provides ready-to-use solutions for various computer vision and streaming applications.

## Components

### Pi ChatGPT Vision Trigger

A sophisticated computer vision application that uses OpenAI's Vision API for GPIO control:
- Real-time image capture using libcamera
- Text detection via OpenAI's Vision API
- Configurable GPIO triggers based on detected text
- Live preview with pygame display
- Comprehensive logging system
- Rate limiting for API cost optimization
- Support for various GPIO devices (LEDs, relays, servos, etc.)

[Learn more](pi_chatgpt_vision_trigger/README.md)

### NVIDIA RTSP Server (WIP)

A flexible RTSP streaming server for NVIDIA Jetson platforms:
- Support for multiple camera types (CSI, USB, ZED)
- Configurable resolution, framerate, and bitrate
- H264 hardware encoding using NVIDIA encoders
- Easy-to-use command line interface
- Supports multiple camera configurations

### Simple PiCamera HUD

A lightweight heads-up display implementation for Raspberry Pi cameras:
- Real-time camera feed display
- FPS counter and system time overlay
- Support for different resolutions
- Rotation options and fullscreen toggle
- Clean shutdown capabilities

## Requirements

- Python 3.7+
- Appropriate hardware (Raspberry Pi or NVIDIA Jetson)
- Camera modules (specific requirements vary by component)

## Installation

Each component has its own installation requirements:

- [Pi ChatGPT Vision Trigger](pi_chatgpt_vision_trigger/README.md#installation)
- Jetson RTSP Server: See `jetson_rtsp_server` directory
- PiCamera HUD: Run directly with Python after installing dependencies

## Project Structure

```
genesis/
├── pi_chatgpt_vision_trigger/    # Vision API GPIO controller
│   └── pi_chatgpt_vision_trigger.py
├── jetson_rtsp_server/           # RTSP streaming server
│   └── rtsp_server.py
├── simple_picamera_hud.py        # Lightweight camera HUD
├── CLAUDE.md                     # LLM integration guide
├── CONTRIBUTING.md               # Contribution guidelines
└── LICENSE                       # GPLv3
```

## Related Projects

GENESIS is part of the [O.A.S.I.S. Project](https://github.com/The-OASIS-Project):

| Component | Purpose |
|-----------|---------|
| [MIRAGE](https://github.com/The-OASIS-Project/mirage) | HUD display system |
| [DAWN](https://github.com/The-OASIS-Project/dawn) | AI voice assistant |
| [SPARK](https://github.com/The-OASIS-Project/spark) | Hand/gauntlet firmware |
| [AURA](https://github.com/The-OASIS-Project/aura) | Helmet sensor firmware |
| [BEACON](https://github.com/The-OASIS-Project/beacon) | CAD models |

## Credits

- Author and Maintainer: Kris Kersey
- Original PiCamera HUD Concept: Jamie (@MrInquisitiveFace)
- Development Assistance: OpenAI's ChatGPT and Anthropic's Claude

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or any later version.

See [LICENSE](LICENSE) for full details.
