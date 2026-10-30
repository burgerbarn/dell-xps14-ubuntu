# Command outputs, Dell XPS 14 DA14260, 2026-10-30

Installed from `XPS14DA14260_A00_Ubuntu2404_Recovery.iso`, fully updated.

## System

```
$ lsb_release -ds; uname -r; cat /sys/class/dmi/id/product_name /sys/class/dmi/id/bios_version
Ubuntu 24.04.5 LTS
7.0.0-42-generic
XPS 14 DA14260
1.12.0
```

## Dell / OEM packages and archives

```
$ grep -h ^deb /etc/apt/sources.list.d/*oem* /etc/apt/sources.list.d/*somerville*
deb http://dell.archive.canonical.com/ noble somerville
deb http://dell.archive.canonical.com/ noble somerville-hypno
deb http://oem.archive.canonical.com/ noble hwe
deb http://oem.archive.canonical.com/ noble nantou

$ apt list --upgradable 2>/dev/null | grep -vc Listing
0

$ fwupdmgr get-updates
No updates available

$ dpkg -l | grep -E "oem-somerville|linux-oem-24.04d" | awk '{print $2,$3}'
linux-oem-24.04d 7.0.0-28.28~24.04.1
oem-somerville-factory-hypno-meta 24.04ubuntu13
oem-somerville-factory-meta 24.04ubuntu1
oem-somerville-hypno-meta 24.04ubuntu13
oem-somerville-meta 24.04ubuntu1

$ apt-cache depends linux-image-oem-24.04d | grep Depends
  Depends: linux-image-generic-hwe-24.04
```

## Hardware video decode (VA-API)

```
$ LIBVA_MESSAGING_LEVEL=2 LIBVA_DRIVER_NAME=iHD ffmpeg -v verbose -init_hw_device vaapi=va:/dev/dri/renderD128 -f lavfi -i nullsrc -t 0.04 -f null -
libva: VA-API version 1.20.0
libva: User environment variable requested driver 'iHD'
libva: Trying to open /usr/lib/x86_64-linux-gnu/dri/iHD_drv_video.so
libva: Found init function __vaDriverInit_1_20
libva: /usr/lib/x86_64-linux-gnu/dri/iHD_drv_video.so init failed
libva: va_openDriver() returns 18

$ apt-cache policy intel-media-va-driver-non-free | grep Candidate
  Candidate: 24.1.0+ds1-1
```

Intel's Ubuntu 24.04 repository (`repositories.intel.com/gpu/ubuntu`, `noble/unified`), newest `intel-media-va-driver`: `25.2.4-1146~24.04`.

Panther Lake (PTL) in Intel's media-driver README: absent in `intel-media-25.2.4`, present in `intel-media-25.3.4` and later.

The same test inside a Flatpak app (`org.kde.kdenlive`, with `org.freedesktop.Platform.VAAPI.Intel` installed):

```
libva: va_openDriver() returns 0
Initialised VAAPI connection: version 1.22
VAAPI driver: Intel iHD driver for Intel(R) Gen Graphics - 26.3.5 ().
```

## Headphone jack (headphones plugged in)

```
$ amixer -c0 contents | grep -A2 "cs42l45.*Jack" | grep -E "name=|: values" | paste - -
name='cs42l45 IT 31 Microphone Jack'	  : values=off
name='cs42l45 IT 33 Headset Jack'	  : values=off
name='cs42l45 OT 43 Headphone Jack'	  : values=off
name='cs42l45 OT 45 Headset Jack'	  : values=off

$ wpctl status | grep -E "Headphones|Speaker"
 │      53. sof-soundwire Headphones            [vol: 1.00]
 │  *   54. sof-soundwire Speaker               [vol: 0.40]
```

## IR camera

```
$ grep -h HIMX /sys/bus/acpi/devices/*/hid
HIMX1092

$ readlink /sys/bus/i2c/devices/i2c-HIMX1092:00/driver
(no output: no driver bound)

$ modinfo hm1092
modinfo: ERROR: Module hm1092 not found.
```

For comparison, the RGB camera sensor next to it binds:

```
$ basename $(readlink /sys/bus/i2c/devices/i2c-OVTI08F4:00/driver)
ov08x40
```
