---
title: "Pulseaudio Noise Suppression"
date: 2022-11-05T20:57:21+08:00
tags: ["Pulseaudio", "Noise Suppression"]
categories: ["Audio"]
# cover:
    #image: "https://imgur.com/F81KgJz.png" # image path/url
   # alt: "Tetu" # alt text
    #caption: "Fusion operates on the NovaNetwork and Fantom Network" # display caption under cover
    #relative: false # when using page bundles set this to true
    hidden: false # on
---

## How To Enable Noise Cancellation For Microphone on Linux
Linux has built in noise cancellation,, it just needs to be activated and configured
The command to get to the file that you need to add couple  lines.
```
sudo nano /etc/pulse/default.pa
```
These are the lines that are needed to be added at the end of the file

```
load-module module-filter-heuristics
load-module module-filter-apply 
load-module module-echo-cancel aec_args="analog_gain_control=0 digital_gain_control=0"
```
This only works for pulseaudio