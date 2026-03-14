# WARNING: THIS REPO IS NOT READY FOR PUBLIC USE AT THIS TIME, MAY BRICK YOUR DEVICE.

# ESPHome-Config-for-localbytes-bulb-9w-rgbct
ESPHome configuration for the LocalBytes RGB+CT smart bulb.

This repo contains an ESPHome config for the [Localbytes Bulb](https://www.mylocalbytes.com/products/smart-bulb-9w-rgbct).

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

## Credits
- LocalBytes - For making/selling the [Bulb](https://www.mylocalbytes.com/products/smart-bulb-9w-rgbct).
- ESPHome - For making [ESPHome](https://esphome.io/).
- JamesSwift - For their [Repo](https://github.com/JamesSwift/localbytes-bulb-9w-rgbct) which helped give me a start.
- Athom-Tech - For their [Configs](https://github.com/athom-tech/athom-configs) of simalar devices that helped inspire large sections of this project.