# i3-xsettings-dpi-patch

Patch i3-gaps so it acquires DPI not from Xresources, but from Xsettings.

This way, DPI can be changed dynamically without restarting the whole i3. Dynamic DPI via Xsettings already works with gvim, termite, chromium, but not with i3 and firefox. So, I wanted to fix that for i3.

Auto-reloading isn't included, so you need to run `i3-msg reload` for changes to apply. Example usage:
```shell
$ xfconf-query -c xsettings -p /Xft/DPI -s 168
$ i3-msg reload
```

i3bar DPI won't change (for now), you need to restart it. Everything else, including window titles, should work fine.

To compile you need to install `xsettings-client` library.
