XLibre Xserver
===============

Xlibre is a fork of the Xorg Xserver, with lots of code cleanups
and enhanced functionality.

This fork of the X11Libre xserver was created to mitigate the divisive nature of the original project by removing any upstream politics and keeping the code. Please do not argue about politics here unless you want your issue to become locked.

I'm not making any major code changes versus upstream, so send your bug reports there. Issues on here should only be used for meta-discussions.

Upgrade notice
--------

* Module ABIs have changed - drivers MUST be recompiled against this Xserver
  version, otherwise the Xserver can crash or fail to start up correctly.

* If your console is locked up (no input possible, not even VT switch), then
  most likely the input driver couldn't be loaded due to a version mismatch.
  When unsure, it's best be prepared to ssh into your machine from another one
  or set a timer that's calling `chvt 1` after certain time, so you don't
  need a cold reboot.

* Proprietary Nvidia drivers might break: they still haven't managed to do
  do even simple cleanups to catch up with Xorg master for about a 
  All attempts to get into direct mail contact have failed. We're trying to
  work around this, but cannot give any guarantees.

* Most Xorg drivers should run as-is (once recompiled!), with some exceptions.
  See `.gitlab-ci.yml` for the versions/branches built along with Xlibre.


Driver repositories
-------------------

Since Redhat had deleted and banned all X11Libre repositories from freedesktop.org,
the driver repositories are now moved to github:

| Driver | Git repository 
| --- | --- |
| xf86-input-elographics:   | https://github.com/X11Libre/xf86-input-elographics    |
| xf86-input-evdev:         | https://github.com/X11Libre/xf86-input-evdev          |
| xf86-input-joystick:      | https://github.com/X11Libre/xf86-input-joystick       |
| xf86-input-keyboard:      | ard       |
| xf86-input-libinput:      | https://github.com/X11Libre/xf86-input-libinput       |
| xf86-input-mouse:         | https://github.com/X11Libre/xf86-input-mouse          |
| xf86-input-synaptics:     | https://github.com/X11Libre/xf86-input-synaptics      |
| xf86-input-vmmouse:       | https://github.com/X11Libre/xf86-input-vmmouse        |
| xf86-video-amdgpu:        | https://github.com/X11Libre/xf86-video-amdgpu         |
| xf86-video-apm:           | https://github.com/X11Libre/xf86-video-apm            |
| xf86-video-ark:           | https://github.com/X11Libre/xf86-video-ark            |
| xf86-video-ast:           | https://github.com/X11Libre/xf86-video-ast            |
| xf86-video-ati:           | https://github.com/X11Libre/xf86-video-ati            |
| xf86-video-chips:         | https://github.com/X11Libre/xf86-video-chips          |
| xf86-video-cirrus:        | https://github.com/X11Libre/xf86-video-cirrus         |
| xf86-video-dummy:         | https://github.com/X11Libre/xf86-video-dummy          |
| xf86-video-fbdev:         | https://github.com/X11Libre/xf86-video-fbdev          |
| xf86-video-freedreno:     | https://github.com/X11Libre/xf86-video-freedreno      |
| xf86-video-geode:         | https://github.com/X11Libre/xf86-video-geode          |
| xf86-video-i128:          | https://github.com/X11Libre/xf86-video-i128           |
| xf86-video-i740:          | https://github.com/X11Libre/xf86-video-i740           |
| xf86-video-i740:          | https://github.com/X11Libre/xf86-video-i740           |
| xf86-video-intel:         | https://github.com/X11Libre/xf86-video-intel          |
| xf86-video-mach64:        | https://github.com/X11Libre/xf86-video-mach64         |
| xf86-video-mga:           | https://github.com/X11Libre/xf86-video-mga            |
| xf86-video-neomagic:      | https://github.com/X11Libre/xf86-video-neomagic       |
| xf86-video-nested:        | https://github.com/X11Libre/xf86-video-nested         |
| xf86-video-nouveau:       | https://github.com/X11Libre/xf86-video-nouveau        |
| xf86-video-nv:            | https://github.com/X11Libre/xf86-video-nv             |
| xf86-video-omap:          | https://github.com/X11Libre/xf86-video-omap           |
| xf86-video-qxl:           | https://github.com/X11Libre/xf86-video-qxl            |
| xf86-video-r128:          | https://github.com/X11Libre/xf86-video-r128           |
| xf86-video-rendition:     | https://github.com/X11Libre/xf86-video-rendition      |
| xf86-video-s3virge:       | https://github.com/X11Libre/xf86-video-s3virge        |
| xf86-video-savage:        | https://github.com/X11Libre/xf86-video-savage         |
| xf86-video-siliconmotion: | https://github.com/X11Libre/xf86-video-siliconmotion  |
| xf86-video-sis:           | https://github.com/X11Libre/xf86-video-sis            |
| xf86-video-sisusb:        | https://github.com/X11Libre/xf86-video-sisusb         |
| xf86-video-suncg14:       | https://github.com/X11Libre/xf86-video-suncg14        |
| xf86-video-suncg3:        | https://github.com/X11Libre/xf86-video-suncg3         |
| xf86-video-suncg6:        | https://github.com/X11Libre/xf86-video-suncg6         |
| xf86-video-sunffb:        | https://github.com/X11Libre/xf86-video-sunffb         |
| xf86-video-sunleo:        | https://github.com/X11Libre/xf86-video-sunleo         |
| xf86-video-suntcx:        | https://github.com/X11Libre/xf86-video-suntcx         |
| xf86-video-tdfx:          | https://github.com/X11Libre/xf86-video-tdfx           |
| xf86-video-trident:       | https://github.com/X11Libre/xf86-video-trident        |
| xf86-video-v4l:           | https://github.com/X11Libre/xf86-video-v4l            |
| xf86-video-vesa:          | https://github.com/X11Libre/xf86-video-vesa           |
| xf86-video-vmware:        | https://github.com/X11Libre/xf86-video-vmware         |
| xf86-video-voodoo:        | https://github.com/X11Libre/xf86-video-voodoo         |
| xf86-video-wsfb:          | https://github.com/X11Libre/xf86-video-wsfb           |
| xf86-video-xgi:           | https://github.com/X11Libre/xf86-video-xgi            |


Contact
-------

|  |  |
| --- | --- |
| Mailing list:                     | https://www.freelists.org/list/xlibre |
| Telegram channel:                 | https://t.me/x11dev |
| Matrix room (mirror of tg group): | https://matrix.to/#/#xlibre:matrix.org |
