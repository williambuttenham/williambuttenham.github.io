---
layout: null
title: MIDI Piano controller
---
![Top of keyboard](/images/midi-piano/front.jpg "Keyboard top"){:width="50%"}.

 I made this project for my partners work in childcare. She has a classroom of toddlers and while they enjoy the musical toys they have, some of them are not robust enough for long term use. In addition most musical toys are limited to simpler instruments that translate well into a small toy. To make this controller robust I have used standard arcade buttons rated for ten million presses and the case will be constructed from 1/2 inch plywood. The controller is using the QMK firmware to easily implement NKRO and MIDI signals.

![Back of keyboard](/images/midi-piano/back.jpg "Keyboard back"){:width="50%"}.

 Connections between keys and the controller use quick disconnect terminals for ease of use when replacing parts in the controller. The diodes required for the NKRO are populated on a peice of perf board that has connections for each note and octave to create a switch matrix. Firmware is loaded on an ATMega32u4 microcontroller via the onboard programmer.

![Wirng of one octave on keyboard](/images/midi-piano/back_octave.jpg "Keyboard octave wiring"){:width="25%"}.
![ProMicro clone used as keyboard controller](/images/midi-piano/controller.jpg "Keyboard controller"){:width="25%"}.
![A closer look at the wiring of the controller board](/images/midi-piano/controller_close.jpg "Keyboard controller closeup"){:width="25%"}.

 I have planned to add a seperate multi function pedal to the project using an industrial foot switch and some toggle switches. It will use its own microcotroller running QMK to simplify the setup and allow the two controllers to work as standalone tools.

![Parts to build a midi pedal controller](/images/midi-piano/pedal_parts.jpg "Pedal parts"){:width="50%"}.
