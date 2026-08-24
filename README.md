<div align="center">

# ⚡ FearverkDPI

**High-Performance Native DPI Bypass & Real-Time TUI Network Engine for Windows**

[![Language](https://img.shields.io/badge/Language-C%2B%2B17-blue.svg?style=for-the-badge&logo=c%2B%2B)](https://en.wikipedia.org/wiki/C%2B%2B)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0078D6.svg?style=for-the-badge&logo=windows)](https://microsoft.com)
[![Driver](https://img.shields.io/badge/Driver-WinDivert%202.2%2B-red.svg?style=for-the-badge)](https://reqcrypt.org/windivert.html)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
[![Speed](https://img.shields.io/badge/Speed-100%25%20Direct%20Line-brightgreen.svg?style=for-the-badge)](#)

[English](#-english) • [Русский](#-русский)

</div>

---

## 🌐 English

### 📖 Overview
**FearverkDPI** is a native, low-latency DPI circumvention engine built in modern C++ with `WinDivert`. Unlike slow commercial VPNs, FearverkDPI does **not** route your traffic through foreign servers. It operates locally on raw packet streams to fragment TLS SNI records, drop QUIC/UDP streams, and inject fake TCP packets with short TTL directly in kernel space.

### ✨ Key Features
* 🚀 **Zero-Lag & Full Bandwidth:** 100% direct connection speed without third-party proxy bottlenecks.
* 🎬 **Instant 4K YouTube Playback:** Automatic UDP 443 (QUIC) drop to force browsers into resilient TCP mode.
* 🛡️ **Advanced TLS De-synchronization:** Real-time ClientHello SNI splitting and low-TTL fake packet injection.
* 🎮 **Full Gaming & Voice Support:** Fixes voice channels in Discord, connection drops in Roblox Studio (Team Create), and blocked web endpoints.
* 📊 **Terminal User Interface (TUI):** Built-in telemetry tracking latency, live packet mutations, and domain hit rates.

---

### 📂 Directory Structure

```text
FearverkDPI/
├── bin/
│   └── FearverkDPI.exe       # Precompiled core binary
├── libs/
│   ├── windivert.h           # Header files
│   ├── WinDivert.lib         # Import library
│   ├── WinDivert.dll         # User-mode library
│   └── WinDivert64.sys       # Signed kernel driver
├── src/
│   └── FearverkDPI.cpp       # Main C++ engine source
├── general.bat               # Auto Mode (Fastest node selection)
├── general_jp.bat            # Japan profile preset
├── general_us.bat            # USA profile preset
└── general_de.bat            # Germany/EU profile preset
