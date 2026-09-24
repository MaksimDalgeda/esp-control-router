# ESP Control for RutOS

## Overview

This repository contains OpenWRT/RutOS packages required to control ESP microcontrollers through the ubus interface.

## Packages

### esp-control-daemon

Daemon service responsible for:

- Discovering connected ESP devices
- Exposing ubus methods
- Communicating with ESP microcontrollers over serial

### vuci-app-esp-control

VuCI API package used to interact with the ESP control daemon.

## Supported UBUS Methods

- `devices` - list connected ESP devices
- `on` - enable a pin
- `off` - disable a pin
- `get` - read sensor data

## Features

- Support for multiple ESP devices
- JSON responses using blobmsg
- Automatic service startup after router reboot
- Integration with OpenWRT/RutOS
