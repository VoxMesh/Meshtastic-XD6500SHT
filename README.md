# Meshtastic XD6500SHT — experimental firmware

Unofficial experimental Meshtastic firmware for ProMicro nRF52840 with the XD6500SHT (SX1262) radio module.

## Firmware

Prepared UF2 and DFU ZIP packages for Meshtastic **2.7.26** and **2.8.2** are available in GitHub Releases.

Choose the package supported by your device's bootloader.

## RF switch fix

The dedicated `nrf52_promicro_xd6500sht` build disables RXEN/TXEN control and holds P0.17 HIGH using `SX126X_ANT_SW`.

DIO2 RF switching and the 1.8 V TCXO configuration remain unchanged. Standard ProMicro builds are unaffected.

The 2.7.26 experimental build excludes BME680/BME688 sensor support.

## Source

| Meshtastic version | Upstream revision | Patch |
| --- | --- | --- |
| 2.7.26 | [54e0d8d](https://github.com/meshtastic/firmware/commit/54e0d8d0ab2ff56b3a9ce967e53f79e49af560fb) | [Patch](patches/xd6500sht-2.7.26.patch) |
| 2.8.2 | [61f60df](https://github.com/meshtastic/firmware/commit/61f60dff5a27d21a305f473065c97a222e6f72f6) | [Patch](patches/xd6500sht-2.8.2.patch) |

Matching source archives accompany each binary release.

## Testing

**These builds have not been hardware-tested.** They are intended for community testing on matching hardware.

Back up settings and keys before flashing. Switching between Meshtastic 2.7 and 2.8 may change the node number or discard stored data.

Test reports are welcome in GitHub Issues. Please include the board and radio module, firmware version, and transmission results compared with the standard firmware.

Related MeshCore firmware: [MeshCore-XD6500SHT](https://github.com/VoxMesh/MeshCore-XD6500SHT).

## License

Based on [Meshtastic firmware](https://github.com/meshtastic/firmware), licensed under GPL-3.0. See [LICENSE](LICENSE). Third-party components retain their respective licenses.
