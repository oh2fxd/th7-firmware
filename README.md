# TH7 Firmware (OTA Releases)

Precompiled firmware binaries, RGB565 regional map packs, and TrueType fonts for **TH7** — a 7-inch ESP32-S3 environmental, weather, and regional map dashboard.

## Overview
TH7 renders Finnish regional maps (`maps_r565/`), live weather telemetry, and sensor feeds on an 800×480 touch display. Includes automatic PSRAM-buffered downloading for map tiles and TTF fonts (`DejaVuSans.ttf`, `materialdesignicons-webfont.ttf`).

## Hardware Target
- **MCU**: ESP32-S3 (16 MB Flash, 8 MB Octal PSRAM)
- **Display**: 7-inch 800×480 RGB565 TFT + SD Card / LittleFS asset storage

## Downloads & Assets
- **Latest Version**: `v1.0.15`
- **OTA Binary**: [`th7.bin`](https://raw.githubusercontent.com/oh2fxd/th7-firmware/main/th7.bin)
- **OTA Manifest**: [`firmware.json`](https://raw.githubusercontent.com/oh2fxd/th7-firmware/main/firmware.json)
- **RGB565 Map Packs**: [`maps_r565/`](./maps_r565)
- **Fonts**: [`fonts/`](./fonts)
- **Changelog**: [`CHANGELOG.md`](./CHANGELOG.md)

## Flashing Instructions

### 1. Built-in OTA Update
Trigger OTA directly from the TH7 web interface (`http://<device-ip>/`) or on-screen settings. Map and font assets are automatically fetched on first boot if missing.

### 2. USB / Serial Flashing (`esptool.py`)
```bash
esptool.py --chip esp32s3 --port /dev/ttyACM0 --baud 921600 write_flash 0x10000 th7.bin
```

## License
Distributed under the [MIT License](./LICENSE). Copyright (c) 2026 OH2FXD.
