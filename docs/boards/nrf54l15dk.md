<div align="center">

<img src="../img/logo.svg" alt="EMBEDOX" height="40">

# nRF54L15 DK

[Overview](../../README.md) &nbsp;·&nbsp; [Download board firmware](https://github.com/embedox/embiot-toolkit/releases)

</div>

---

Nordic **nRF54L15** development kit.

| | |
|---|---|
| <img src="../img/boards/nrf54l15dk.png" alt="nRF54L15 DK" width="300"> | **SoC** nRF54L15<br>**Debugger** on‑board SEGGER J‑Link (debug USB port)<br>**Pairing button** Button 1<br>**Power button** Button 0, hold 3 s<br>**Wake button** Button 0<br>**First‑time install** J‑Link, one `.hex` file<br>**Release files** `peripheral-nrf54l15dk-<ver>.hex` |

## Capabilities in EMBIoT Toolkit

| BLE | Controls | Power | IMU | Sensors | Camera | Firmware | Configuration |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| ✓ | ✓ | ✓ | — | — | on request | ✓ | ✓ |

**Camera** needs an [Arducam Mega SPI camera](../camera.md) and the camera‑enabled firmware, which is not part of the standard release; request the firmware from support@embedox.com.

## First‑time install

1. Download `peripheral-nrf54l15dk-<ver>.hex` from [Releases](https://github.com/embedox/embiot-toolkit/releases).
2. Connect the DK's debug USB port (the on‑board J‑Link).
3. **nRF Connect for Desktop → Programmer:** **Add file** `peripheral-nrf54l15dk-<ver>.hex` → **Erase all & write**. Alternatively, copy the file onto the `JLINK` USB drive the DK mounts.

   Or from the command line:

   ```bash
   nrfutil device program --firmware peripheral-nrf54l15dk-<ver>.hex --options chip_erase_mode=ERASE_ALL,reset=RESET_SYSTEM
   ```
4. Done when the LED blinks green slowly. Continue with **Connect** in the [README](../../README.md#connect): press the pairing button and pair the client device.

## Release files

| File | Contains | Goes in with |
|---|---|---|
| `peripheral-nrf54l15dk-<ver>.hex` | MCUboot + application image | J‑Link |

All files are under [Releases](https://github.com/embedox/embiot-toolkit/releases) with a `SHA256SUMS.txt`.

## Board notes

- The DK's LEDs are all green: **LED0** lights for the 🔴 red states, **LED1** for the 🟢 green ones and **LED2** for the 🔵 blue ones; the **Controls** page shows them as the **Failure**, **Status** and **BT** switches.
