# JF Router Control Toolkit

Advanced modification and control methods for Jio Fiber ONT devices (JCOW404 / JCOW411)
# (c) 2026 Naitik1208. All rights reserved.
# This file is part of the JF-ROUTER project.
# Unauthorized copying or modification is strictly prohibited.

---

## Overview
This repository provides tested methods to gain deeper control over JF ONT routers.  
It consolidates multiple low-level techniques into a single structured resource.

---

## Capabilities

### Core Access
- **Root Access (Telnet)**  
  Gain full shell access to the device for system-level control.

- **Decrypt Config File**  
  Extract and analyze router configuration data.

### System Control
- **Disable TR-069 (Hard Disable)**  
  Removes or disables the TR-069 client binary.

  **Effect:**
  - ISP cannot initiate remote management sessions  
  - Firmware updates via TR-069 are no longer possible  
  - Remote configuration pushes are blocked  

  **Persistence:**
  - Remains effective until you manually flash a firmware

  **Implication:**
  - Full local control over device configuration  
  - No automatic ISP-side recovery or updates  

- **Run Custom Scripts**  
  Execute persistent scripts to modify router behavior.

### File & Storage Access
- **Filesystem Extraction to USB**  
  Copy internal router files directly to external storage.

- **Enable FTP Server (Root Access)**  
  Access entire filesystem over FTP with `/` as root.

### Firmware Management
- **Firmware Downgrade**  
  Revert to older firmware versions for compatibility or exploit access.

### Network Modifications
- **Run NextDNS (Ad Blocking)**  
  Apply network-wide DNS-level filtering directly on the router.

---

## Instructions

1. [Decrypt Config File](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Decrypt%20Config%20File.md)
2. [Get Root Access (Telnet)](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Get-Root-Access-JF-ONT.md)
3. [Enable Root FTP Access](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Enable%20Root%20FTP%20JF%20Router.md)  
4. [Run Custom Scripts on Router](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Run%20Custom%20Scripts%20On%20Your%20Router.md)
5. [Downgrade Firmware](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Downgrade%20Firmware.md)  
6. [Disable TR-069](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Disable%20TR-069.md)  
7. [Extract Filesystem to USB](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Way%20to%20get%20any%20file%20directly%20from%20your%20Jio%20Router's%20Filesystem%20to%20your%20pendrive.md)  
8. [Run NextDNS](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Run%20NextDNS.md)  

---

## Scripts
The `Scripts/` directory contains reusable scripts for:
- DNS control and overrides  
- Startup execution hooks  
- Router behavior modification  

Refer to individual scripts for usage.

---

## Tested Devices
- JCOW404  
- JCOW411  

---

## Warning
These methods involve low-level system modifications.

- Incorrect usage may brick your router  
- Proceed only if you understand the risks  
- Always keep a recovery option available  

---

## Notes
- Methods are tested but may break with firmware updates
---

## Contribution
Improvements and additional methods are welcome.

---

## License

**Copyright (c) 2026 Naitik1208. All Rights Reserved.**

This repository and its contents (including firmware, scripts, and documentation) are proprietary. 
- **Ownership:** All rights remain with Naitik1208.
- **Usage:** You may view and use this for personal use. 
- **Restrictions:** Redistribution, claiming authorship, or creating similar derivative works is strictly prohibited.
- **Contributions:** Pull Requests are welcome, but remain the property of the project owner. See the [LICENSE](./LICENSE) file for full terms.

---

If this repository helped you, consider starring it.
