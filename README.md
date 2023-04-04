# Fix Gnome "Your native host connector do not support following APIsv6"


```console
op@rhel ~]$ uname -a
Linux rhel 5.14.0-162.6.1.el9_1.x86_64 #1 SMP PREEMPT_DYNAMIC Fri Sep 30 07:36:03 EDT 2022 x86_64 x86_64 x86_64 GNU/Linux
[op@rhel ~]$ 
```
### Install gnome-browser-connector

## Buiding From Source

```console
[op@rhel ~]$ git clone https://gitlab.gnome.org/GNOME/gnome-browser-connector.git && cd gnome-browser-connector/
[op@rhel ~]$ meson --prefix=/usr builddir
[op@rhel ~]$ cd builddir/ 
[op@rhel ~]$ meson install

```

You may have to install `meson` as root with `sudo pip3 install meson` If any error, delete the directory `builddir` and rebuild as root.

## Restart gnome with 

```console
[op@rhel ~]$ killall -3 gnome-shell
```

or if you don't wanna log out, Just do

```console
[op@rhel ~]$ gnome-browser-connector -c
```

Refresh the browser and make sure `Disable all extensions` is unchecked at https://extensions.gnome.org/local/
