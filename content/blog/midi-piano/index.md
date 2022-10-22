---
title: "MIDI Piano controller"
date: "2020-02-21"
description: "This rugged MIDI piano was built to withstand daily abuse from a classroom of toddlers. It was built with modularity and repairability in mind as well to allow future upgrades like a sustain pedal."
cover:
  src: ./front.jpg
  caption: Keyboard top
---

 I made this project for my partners work in childcare. She has a classroom of toddlers and while they enjoy the musical toys they have, some of them are not robust enough for long term use. In addition most musical toys are limited to simpler instruments that translate well into a small toy. To make this controller robust I have used standard arcade buttons rated for ten million presses and the case will be constructed from 1/2 inch plywood. The controller is using the QMK firmware to easily implement NKRO and MIDI signals.

![Back of keyboard](back.jpg "Keyboard back")

 Connections between keys and the controller use quick disconnect terminals for ease of use when replacing parts in the controller. The diodes required for the NKRO are populated on a peice of perf board that has connections for each note and octave to create a switch matrix. Firmware is loaded on an ATMega32u4 microcontroller via the onboard programmer.

![Wirng of one octave on keyboard](back_octave.jpg "Keyboard octave wiring")
![ProMicro clone used as keyboard controller](controller.jpg "Keyboard controller")
![A closer look at the wiring of the controller board](controller_close.jpg "Keyboard controller closeup")

 I have planned to add a seperate multi function pedal to the project using an industrial foot switch and some toggle switches. It will use its own microcotroller running QMK to simplify the setup and allow the two controllers to work as standalone tools.

![Parts to build a midi pedal controller](pedal_parts.jpg "Pedal parts")
