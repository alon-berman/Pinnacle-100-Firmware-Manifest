# Pinnacle 100 Firmware Manifest Repo

## Using the Firmware

See the user guide for the firmware [here](https://lairdcp.github.io/guides/ble-gateway-firmware/1.0/Introduction.html)

## Cloning Firmware

> **WARNING:** On Windows do not clone into a starting folder path longer than 12 characters or else the firmware will not build.

This is a Zephyr `west` manifest repository. To learn more about `west` see [here](https://docs.zephyrproject.org/latest/guides/west/index.html).

To clone this repository properly use the `west` tool. To install `west` you will first need Python3.

Install `west` using `pip3`:

```
# Linux
pip3 install --user -U west

# macOS (Terminal) and Windows (cmd.exe)
pip3 install -U west
```

Once `west` is installed, clone this repository using `west init` and `west update`:

```
# Checkout the latest manifest on main
west init -m https://github.com/LairdCP/Pinnacle-100-Firmware-Manifest.git --mr main

# OR checkout the 6.2.0 release
west init -m https://github.com/LairdCP/Pinnacle-100-Firmware-Manifest.git --mr v6.2.0

# Now, pull all the source described in the manifest
west update
```

## Preparing to Build

If this is your first time working with a Zephyr project on your computer you should follow the [Zephyr getting started guide](https://docs.zephyrproject.org/latest/getting_started/index.html#) to install all the tools.

The firmware uses zephyr 2.6.99 (2.7.0 dev branch), so GCC 10 is recommended.
[GNU Arm Embedded Toolchain: 10.3-2021.07](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) is recommended.

See here to [setup the GNU ARM Embedded tools](https://docs.zephyrproject.org/2.7.0/getting_started/toolchain_3rd_party_x_compilers.html)

If using Linux or macOS, v0.13.1 of the Zephyr SDK is recommended.

## Building the Firmware

> **WARNING:** Before building the firmware, be sure to install all dependencies using the `nrf/scripts/requirements-fixed.txt`

From the directory where you ran `west update`, issue the following command:

```
# Linux
pip3 install --user -r nrf/scripts/requirements-fixed.txt

# macOS and Windows
pip3 install -r nrf/scripts/requirements-fixed.txt
```

See [here for build commands](https://lairdcp.github.io/guides/ble-gateway-firmware/1.0/docs/readme_aws.html#building-the-firmware).
