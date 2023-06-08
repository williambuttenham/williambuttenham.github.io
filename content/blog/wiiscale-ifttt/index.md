---
title: "WiiScale IFTTT"
date: "2021-09-19"
description: "A simple NodeJS app to translate JSON between an old Mac OS X app and IFTTT "
---

Using the old WiiScale app on a Mac, I wanted to send the weight data to IFTTT
(and further on the Apple Health). [IFTTT](https://ifttt.com/) only accepts JSON
in a certain format, so I wrote a [simple app to translate the data](https://github.com/williambuttenham/wiiscale-ifttt).

##### 2023 Update

The version of [WiiScale](https://snosrap.com/wiiscale/) I use was last updated
in 2013, and it's not clear if it still works on the latest version of macOS.
I'm using it on macOS 10.14.6 but on my newer computer it is not working. I am
looking into switching to a Linux based solution, either running on a Raspberry Pi
near the scale or on my Proxmox server. Switching to Apple Shortcuts instead of IFTTT
seems possible now as well, avoiding another web account.
