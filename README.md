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

Create a `/etc/portage/repos.conf/Gnome-3.26-X.conf` file containing

```
[Gnome-3-26-X]
location = /usr/local/portage/Gnome-3-26-X
sync-type = git
sync-uri = https://github.com/hhfeuer/Gentoo-Gnome-3.26-X.git
priority=9999
```

Then run emerge --sync

## via layman

Add via layman:

	layman -o https://raw.github.com/hhfeuer/Gentoo-Gnome-3.26-X/master/repositories.xml -f -a Gnome-3-26-X
	Then run layman -s Gnome-3-26-X

Quirks
------
needs package.unmask
	=app-text/libgepub-0.5.2

needs package.keywords/accept_keywords
	=app-text/libgepub-0.5.2 ~amd64
	=media-plugins/grilo-plugins-0.3.5 ~amd64

due to bug in folks needs package.use
	dev-libs/folks -tracker

depending on kernel config might need package.use
	sys-apps/bubblewrap suid

if portage is complaining about blocks concerning glib and gdbus-codegen, run first
	emerge -1 glib gdbus-codegen



