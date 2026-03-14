# WARNING: THIS REPO IS NOT READY FOR PUBLIC USE AT THIS TIME, IT MAY BRICK YOUR DEVICE.

# ESPHome-Config-for-localbytes-bulb-9w-rgbct
ESPHome configuration for the LocalBytes RGB+CT smart bulb.

This repo contains an ESPHome config for the [Localbytes Bulb](https://www.mylocalbytes.com/products/smart-bulb-9w-rgbct).

The repo also contains an installer tool which may be useful to some and there is more information about below.

## Why do this

I prefer ESPHome to Tasmota for its customisability, Consistency, And more simple integration with Home Assistant as it does not require MQTT.

There is no official configuration from LocalBytes.

There is a Repo By [JamesSwift](https://github.com/JamesSwift) located [HERE](https://github.com/JamesSwift/localbytes-bulb-9w-rgbct) however this repo is older and gas not been updated to a modern version of ESPHome. I also had some issues with the release binaries.

Therefore I decided to put together a modern config setup with newer features that builds without issue on a more up to date version of ESPHome.

These bulbs are solid and are one of the few easy to get, reasonably priced, and customisable options that come in a B22 Version which is very common in the UK.

## The Device
Whilst labled as a RGB+CT bulb, It is actually RGBWW Bulb and is a pretty standard device which we can build ESPhome targeting the ESP8266 (Specific board version: ESP8285).

## Features
- Wi-Fi Provisioning.
- IPv6 Support.
- Full compatibility with Home Assistant without any other setup.
- Full colour control as either RGB or as white with temperature control 3000-6000k.
- Brightness control.
- Lighting Effects:
    - Pulse
    - Fast Pulse
    - Slow Pulse
    - Asymmetrical Pulse
    - Random
    - Strobe
    - Flicker
- Power on default state can be set as:
    - Always Off
    - Always On
    - Restore Power Off State
- WebUI for direct control and OTA flashing.
- Device status diagnostic sensors.
- Factory Reset by power cycling 7 times within 10 seconds of each cycle.

## Install Instructions
- Connect Bulb to your wifi network
- Flash to tasmota-minimal
- Flash to ESPHome

# The Bulb Installer Tool
Also In This Repo is a tool which once installed allows for you to download a selection of things on the device itself. This tool can also easily be flashed to from thee bulb's web interface on the ESPHome configuration above.

Currently you can download and install:
- The latest version fo the tool itself.
- The latest version of the Bulb Firmware found in this repo
- Tasmota Lite (15.3.0 as of time of writing)

This is a handy way of having spare bulbs and such ready to go and when you pull them out you can select what you want to do and easily get the latest version of either the ESPHome setup or updating the installer and getting the most recently added version of Tasmota. Tasmota is not pointed at "latest" as I am yet to find an easy way to to get MD5 hashes of the releases but this may change later.

## Why did I do this?
I orginally wanted to have an update entity built into the bulb firmware but it proved difficult due to the storage space limitations of the `ESP8285N08` in the bulb. However with optimisations and breakthroughs happening all the time in the ESPHome world... This may be addressed in the future.

## Ideas for other things that I could add to the list of options?

Raise an issue and I will have a look.

## Limitations
I was pretty limited with what could be done due to the space limitations of the device. I ended up turning off logging to save space. There is a text sensor which offers some information and feedback however it is limited which may effect troubleshooting options if you have any problems.

I also turned off the HomeAssistant API connection to save space so this tool needs to be operated from a browser only.

If there are issues safe mode is active so if ESPHome can it will go into safe mode and still connect to the network. You can then use the ESPHome tools to OTA firmware changes using their protocol which is enabled.

## What made this possible now?
ESPHome on the ESP8266 chip family had issues with retrieving files from HTTPS due to fixed size buffers which were not big enough. However in 2026.3 [THIS](https://github.com/esphome/esphome/pull/14009) PR was merged and released. This allows for the buffer to be configured. it was previously fixed at 512 bytes but now can be set up to 16384 bytes.

This makes it pretty easy (although it takes a bunch of firmware space) to install OTA updates via HTTPS requests now.

## Credits
- LocalBytes - For making/whitelabeling/selling the [Bulb](https://www.mylocalbytes.com/products/smart-bulb-9w-rgbct).
- ESPHome Team and the Open Home Foundation - For making [ESPHome](https://esphome.io/).
- JamesSwift - For their [Repo](https://github.com/JamesSwift/localbytes-bulb-9w-rgbct) which helped give me a start.
- Athom-Tech - For their [Configs](https://github.com/athom-tech/athom-configs) of simalar devices that helped inspire large sections of this project.