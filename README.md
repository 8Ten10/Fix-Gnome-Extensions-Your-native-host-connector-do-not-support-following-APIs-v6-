# Fix Gnome-Extensions "Your native host connector do not support following APIsv6"


```
op@rhel ~]$ uname -a
Linux rhel 5.14.0-162.6.1.el9_1.x86_64 #1 SMP PREEMPT_DYNAMIC Fri Sep 30 07:36:03 EDT 2022 x86_64 x86_64 x86_64 GNU/Linux
[op@rhel ~]$ 
```
### Install gnome-browser-connector

## Buiding From Source
```
[op@rhel ~]$ git clone https://gitlab.gnome.org/GNOME/gnome-browser-connector.git && cd gnome-browser-connector/
[op@rhel ~]$ meson --prefix=/usr builddir
[op@rhel ~]$ cd builddir/ 
[op@rhel ~]$ meson install

```

You may have to install `meson` as root with `sudo pip3 install meson` if you encounter any error on the last comment. You will then have to delete `builddir` and rebuild as root.

## Restart gnome with 
```
[op@rhel ~]$ killall -3 gnome-shell
```

or if you don't wanna log out, Just type
```
[op@rhel ~]$ gnome-browser-connector -c
```

refresh your browser, and make sure `Disable all extensions` is uncheck at https://extensions.gnome.org/local/
