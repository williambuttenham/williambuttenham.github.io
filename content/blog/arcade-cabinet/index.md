---
title: "3/5 Scale Arcade Cabinet"
date: "2018-06-21"
description: "My arcade cabinet built around a 14\" CRT TV, powered by a Raspberry Pi running Lakka with QMK controls"
cover:
  src: ./feature.jpg
---

I was inspired to create this by a [similar build](https://tinkerlog.com/2016/10/03/galaga-arcade-cabinet/)
by Alex Weber, featured on [Hackaday](https://hackaday.com/2016/10/06/galaga-cabinet-is-out-of-this-world/).
I wanted to build a small arcade cabinet that could be easily moved around, as I
had yet to move into my house. The authentic CRT feeling was essential for me and
the smaller 14 inch TVs are much easier to find than the larger sizes so Alex's
project was interesting. I found a 14 inch CRT TV at Value Village for $10 and
started building the cabinet around it.

The cabinet is based off drawings for a Galaga cabinet found [here](http://jakobud.com/cabinetPlans.php).
I altered the design to trim off the bottom 3 inches to accommodate some caster
wheels. Compared to Alex's build, my cabinet uses dado grooves or rabbets to hold
the middle panels and I used wood veneer edge banding to cover the exposed plywood
edges. I applied a black paint to the whole cabinet and I do have plans to add some
graphics to the sides. For now I have been using the cabinet as a collection spot
for all of my stickers.

The controls are directly connected to an ATmega32U4 development board loaded
with QMK firmware. The controller board is connected to the Raspberry Pi via USB
and the controls are mapped to the keyboard keys. The Raspberry Pi is running
[Lakka](https://www.lakka.tv/), a Linux distribution based on RetroArch. I chose
the Raspberry Pi because it has a builtin composite video output, which is required
for the CRT TV.

<https://github.com/williambuttenham/arcade-machine>
