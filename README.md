# GlitchBand

**GlitchBand** is a wearable cybersecurity and emergency communication device embedded into an ultra-thin, flexible PCB. Designed for hostile, infrastructure-deprived environments, it detects wireless threats, blocks USB-based intrusions, and creates an offline local Wi-Fi network during outages — all from your wrist.

> *Jack in. Stay secure. Broadcast when no one else can.*

---

## 🔐 Features

- **Wireless Threat Detection**
  - Scans for rogue Wi-Fi access points and BLE trackers (e.g. AirTags)
  - Silent scan mode alerts user without external signals

- **USB Intrusion Defense**
  - Detects when USB ports attempt unauthorized data connections
  - Alerts before enumeration, data sniffing, or payload injection occurs

- **Secure Plug-In Authenticator**
  - Acts as a physical 2FA key using HID emulation (like a YubiKey)
  - OTP-style login from a wearable device

- **Beacon Mode**
  - Hosts “GlitchNet” — an offline Wi-Fi AP that serves emergency HTML pages
  - Share critical maps, contacts, or mesh chat even during internet/power failure

- **Cyberpunk Hardware Design**
  - Built on a custom ultra-thin flexible PCB
  - Features a round LCD display, RGB status ring, and USB-C edge connector

---

## ⚙️ Hardware Stack

| Component | Role |
|----------|------|
| ESP32-S3FN8 | MCU with Wi-Fi, BLE, USB-OTG |
| GC9A01 1.28” Round LCD | Touchscreen UI |
| USB-C Gold Finger Edge | Host plug-in interface |
| WS2812B LEDs | RGB status indicators (Scan, Beacon, Alert) |
| TP4056 + 3.7V LiPo | Charging + battery system |
| 2-Layer Flex PCB | Embedded circuit + curved form factor |

---

## 💻 Software Stack

- **ESP-IDF** (C, FreeRTOS)
- **LVGL** for UI rendering
- **TinyUSB** for USB detection and HID emulation
- **SPIFFS / LittleFS** to serve offline HTML from flash
- **SoftAP Mode** for offline Wi-Fi “GlitchNet” access
