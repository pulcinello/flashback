---
title: "Sway"
date: 2020-11-07T14:55:29+08:00
draft: true
---

## Screenshots
grim allows you to grab images, slurp allows you to select a region of the screen.

wl-clipboard gives you utilities for working with the clipboard like wl-copy and jq is a json parser, these two are dependencies of a script that we will use for simpler screenshotting: grimshot

Install all of these with apt and make sure to have the grimshot script executable:
```bash
sudo apt install wl-clipboard
sudo apt install grim
sudo apt install slurp
sudo apt install jq
```

I have modified this line to have better naming of the saved screenshots:

All that's left is adding these commands to the sway config ~/.config/sway/config.

Here I have grimshot as an executable under ~/.local/bin/grimshot

```bash
set $grimshot ~/.local/bin/grimshot

bindsym Print exec $grimshot --notify save screen
bindsym Shift+Print exec $grimshot --notify copy screen
bindsym Ctrl+Print exec $grimshot --notify save area
bindsym Ctrl+Shift+Print exec $grimshot --notify copy area
```
And you are set! With these settings you will have:

Print - saves the entire screen
<Shift> + Print - copy the entire screen
<Ctrl> + Print - select an area and save it
<Shift>+<Ctrl> + Print - select an area and copy it
You will find the saved screenshot in your ~/Pictures folder.


## Refferences
* [Sway on Ubuntu](https://llandy3d.github.io/sway-on-ubuntu/)
* [sway_config](https://github.com/snakedye/sway_config)
