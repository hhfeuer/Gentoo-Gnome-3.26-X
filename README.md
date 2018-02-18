Unofficial Gentoo Gnome 3.26 on Xorg overlay
--------------------------------------------

Versions
--------

 - Gnome 3.26 (stable)

General information
-------------------

 - All ebuild are keyworded amd64
 - Only contains dependencies for and tested with USE="-wayland"
 - Updated games not (yet) included
 - Portions taken from the Heather Gnome overlay
 - ebuilds derived from the 3.22/24 official Gentoo portage ebuilds

Usage
-----

## via local overlays

Create a `/etc/portage/repos.conf/Gnome-3.16-X.conf` file containing

```
[Gnome-3.26-X]
location = /usr/local/portage/Gnome-3.26-X
sync-type = git
sync-uri = https://hhfeuer@github.com/hhfeuer/Gentoo-Gnome-3.26-X.git
priority=9999
```

Then run emerge --sync

## via layman

Add via layman:

	layman -o https://raw.github.com/hhfeuer/Gentoo-Gnome-3.26-X/master/repositories.xml -f -a Gnome-3.26-X
