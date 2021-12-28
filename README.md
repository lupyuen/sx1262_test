# LoRa Test App for Semtech SX1262 and Apache NuttX OS

Read the articles...

-   ["LoRa SX1262 on Apache NuttX OS"](https://lupyuen.github.io/articles/sx1262)

To add this repo to your NuttX project...

```bash
cd nuttx/apps/examples
git submodule add https://github.com/lupyuen/sx1262_test
```

Next update the Makefiles and Kconfig...

-   ["Update Makefiles and Kconfig"](https://lupyuen.github.io/articles/sx1262#update-makefiles-and-kconfig)

Then update the NuttX Build Config...

```bash
## TODO: Change this to the path of our "incubator-nuttx" folder
cd nuttx/nuttx

## Preserve the Build Config
cp .config ../config

## Erase the Build Config and Kconfig files
make distclean

## For BL602: Configure the build for BL602
./tools/configure.sh bl602evb:nsh

## For ESP32: Configure the build for ESP32.
## TODO: Change "esp32-devkitc" to our ESP32 board.
./tools/configure.sh esp32-devkitc:nsh

## Restore the Build Config
cp ../config .config

## Edit the Build Config
make menuconfig 
```

In menuconfig, enable the SX1262 Test App under "Application Configuration" → "Examples".
