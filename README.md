# Electronics

This repository contains Tuya device descriptions and configurations for two platform variants:

* BK7231N
* ECR6600

The files are organized by platform directory. Each folder contains the extracted configuration, the Tuya dump, and related artifacts used to identify the module, map pins, and locate Tuya data offsets.

## Available Modules

### BK7231N

This section describes a device based on a CBU module with BK7231N. The mapping from `BK7231N/info.txt` is:

* Button (channel 1) - P17
* LED (channel 1) - P9
* Bridge Relay On (channel 1) - P7
* Bridge Relay Off (channel 1) - P8
* WiFi LED - P15

Conclusion from the configuration: this is a simple switching module with a button, status LED, and separate relay control lines.

Files in `BK7231N/`:

* `info.txt` - short hardware summary and pin map.
* `tuya_config.json` - extracted Tuya configuration.
* `OpenBK_config.json` - OpenBeken configuration for this module.
* `readResult_BK7231N_QIO_2026-15-8-12-54-25.bin` - binary readout used during extraction.
* `FL_M101_V2_front.png` - front photo of the board.
* `FL_M101_V2_rear.png` - rear photo of the board.

### ECR6600

This section describes the second platform variant, identified in the data as `eswin_ecr6600` / `ECR6600`. The mapping from `info.txt` is:

* BL0937 SEL - P15
* Button (channel 1) - P24
* LED (channel 1) - P0
* BL0937 VI (CF1) - P20
* WiFi LED - P22
* BL0937 ELE (CF) - P14
* Relay (channel 1) - P25

Conclusion from the configuration: this is an energy-monitoring module based on BL0937, with one relay channel and a separate WiFi LED.

Files in `ECR6600/`:

* `info.txt` - short hardware summary and pin map.
* `tuya_config.json` - extracted Tuya configuration.
* `OpenECR_config.json` - OpenBeken configuration for this module.
* `readResult_ECR6600_2026-14-8-18-18-32.bin` - binary readout used during extraction.

## Configuration Files

* `BK7231N/tuya_config.json` - full Tuya configuration dump for the BK7231N device.
* `BK7231N/info.txt` - summary extracted from the BK7231N variant configuration.
* `BK7231N/OpenBK_config.json` - OpenBeken configuration for BK7231N.
* `ECR6600/tuya_config.json` - full Tuya configuration dump for the ECR6600 device.
* `ECR6600/info.txt` - summary extracted from the ECR6600 variant configuration.
* `ECR6600/OpenECR_config.json` - OpenBeken configuration for ECR6600.

## Notes

* For ECR6600, the Tuya section starts at address `0x1D5000`, which matches the default offset for RTL8720C and ECR6600.
* For BK7231N, the Tuya section starts at address `0x1EE000`.
* Both platform directories now contain their own configuration artifacts, so the root directory only keeps this README.


