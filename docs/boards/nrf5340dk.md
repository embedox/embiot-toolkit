<div align="center">

<img src="../img/logo.svg" alt="EMBEDOX" height="40">

# nRF5340 DK

[Overview](../../README.md) &nbsp;·&nbsp; [Download board firmware](https://github.com/embedox/embiot-toolkit/releases)

</div>

---

Nordic **nRF5340** development kit.

| | |
|---|---|
| <img src="../img/boards/nrf5340dk.png" alt="nRF5340 DK" width="300"> | **SoC** nRF5340, application and network core<br>**Debugger** on‑board SEGGER J‑Link (debug USB port)<br>**Pairing button** Button 2<br>**Power button** Button 1, hold 3 s<br>**Wake button** Button 1<br>**First‑time install** J‑Link, two `.hex` files<br>**Release files** `peripheral-nrf5340dk-<ver>.hex` · `peripheral-nrf5340dk-<ver>-net.hex` |

## Capabilities in EMBIoT Toolkit

| BLE | Controls | Power | IMU | Sensors | Camera | Firmware | Configuration |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| ✓ | ✓ | ✓ | — | — | on request | ✓ | ✓ |

**Camera** needs an [Arducam Mega SPI camera](../camera.md) and the camera‑enabled firmware, which is not part of the standard release; request the firmware from support@embedox.com.

## First‑time install

1. Download `peripheral-nrf5340dk-<ver>.hex` and `peripheral-nrf5340dk-<ver>-net.hex` from [Releases](https://github.com/embedox/embiot-toolkit/releases).
2. Connect the DK's debug USB port (the on‑board J‑Link).
3. **nRF Connect for Desktop → Programmer:** **Add file** both `.hex` files → **Erase all & write**. The Programmer places each file on its core by address.

   Or from the command line:

   ```bash
   nrfutil device program --firmware peripheral-nrf5340dk-<ver>-net.hex --core network --options chip_erase_mode=ERASE_ALL
   nrfutil device program --firmware peripheral-nrf5340dk-<ver>.hex --core application --options chip_erase_mode=ERASE_ALL,reset=RESET_SYSTEM
   ```
4. Done when the LED blinks green slowly. Continue with **Connect** in the [README](../../README.md#connect): press the pairing button and pair the client device.

## Release files

| File | Contains | Goes in with |
|---|---|---|
| `peripheral-nrf5340dk-<ver>.hex` | MCUboot + application image | application core, J‑Link |
| `peripheral-nrf5340dk-<ver>-net.hex` | network core image (ipc_radio) | network core, J‑Link |

All files are under [Releases](https://github.com/embedox/embiot-toolkit/releases) with a `SHA256SUMS.txt`.

## Board notes

- The DK's LEDs are all green: **LED1** lights for the 🔴 red states, **LED2** for the 🟢 green ones and **LED3** for the 🔵 blue ones; a color picked on the **Controls** page dims the three together.
