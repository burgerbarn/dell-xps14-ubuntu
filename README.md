# Dell XPS 14 (2026) with Ubuntu: sold as certified, broken on Dell's own image

Dell announced an Ubuntu version of the 2026 XPS 14 (DA14260), sold it from June 2026, and got two configurations certified by Canonical. By late October 2026 you cannot buy one pre-configured with Linux: every preset on Dell's XPS 14 page is Windows 11 Home, and Ubuntu is only available by custom-building, where it costs more than Windows. On Dell's own Ubuntu image, basic hardware on this laptop still does not work.

## My take

I've run Red Hat since 1995 and owned hundreds of computers. I know what support looks like, and this isn't it. I bought this XPS because Dell sold it as a certified Ubuntu laptop. That purchase was misleading. That's my opinion; the rest of this page is the record.

This is what keeps ordinary people off Linux. They buy the laptop that says "certified for Ubuntu", the basics break, and they blame Linux, not the vendor. Vendors count on Linux users to shrug and fix things ourselves. Holding them to what they sold is on us.

Charging more for the Linux build of identical hardware looks like a way to extract extra money from people who refuse to pay Microsoft.

Am I overreacting, or is this abuse?

Everything below is either a dated link or the output of a command run on my XPS 14 on 2026-10-30. Raw outputs are in [evidence/](evidence/).

## Background: Dell used to stand behind Linux on the XPS

- 2012-11-29: Dell ships the XPS 13 with Ubuntu 12.04 LTS, from its "Project Sputnik" effort, as a "developer edition" ([PCWorld](https://www.pcworld.com/article/455849/dell-ships-lightweight-xps-13-laptop-with-ubuntu-linux.html)).
- 2018-07-27: the XPS 13 Developer Edition ships with Ubuntu 18.04 LTS pre-installed, which Dell calls its "seventh generation XPS 13 developer edition" ([Canonical](https://www.ubuntu.com/blog/dell-xps13-developer-edition-ships-with-ubuntu-18-04-lts-pre-installed)).
- 2020: the XPS 13 developer edition ships with Ubuntu 20.04 LTS ([TechRadar](https://www.techradar.com/news/dell-xps-13-for-developers-comes-with-ubuntu-2004-lts-pre-loaded)).
- 2020-09-28: Dell says Windows XPS 13 owners can move to its certified Ubuntu image even if they didn't buy Ubuntu, and that doing so "will not affect warranty or support conditions" ([GamingOnLinux](https://www.gamingonlinux.com/2020/09/dell-announce-new-xps-13-laptop-models-will-support-moving-from-windows-to-ubuntu/)).

The 2026 XPS 14 got a few months as an Ubuntu-first listing, and is now sold with Ubuntu as a −$10 option behind a Windows default.

## Timeline

| Date | What happened | Source |
|---|---|---|
| 2026-01-05 | Dell announces the new XPS 14 and 16; an Ubuntu version is "coming this year" | [OMG! Ubuntu](https://www.omgubuntu.co.uk/2026/01/new-dell-xps-2026-with-ubuntu) |
| 2026-05-12 | Canonical certifies two DA14260 configurations for Ubuntu 24.04 LTS (kernel 6.17.0-1011-oem, BIOS 1.3.1) | [202511-38075](https://ubuntu.com/certified/202511-38075) (Core Ultra X7 358H), [202511-38076](https://ubuntu.com/certified/202511-38076) (Core Ultra 5 325) |
| 2026-06-02 | XPS 14 goes on sale with Ubuntu 24.04 preinstalled, from $1,900, $100 less than Windows | [Liliputing](https://liliputing.com/dell-xps-14-laptop-is-now-available-with-ubuntu-linux/) |
| 2026-06-19 | Dell's configuration page `useda14260ucto01`: Ubuntu 24.04 LTS is the default OS, Windows 11 Home is a +$100 option, $1,899.99 | [Wayback capture](https://web.archive.org/web/20260619204610/https://www.dell.com/en-us/shop/dell-laptops/new-xps-14-laptop/spd/xps-da14260-laptop/useda14260ucto01) |
| 2026-08-20 | Same page still offers Ubuntu 24.04 LTS, $1,939.99 | [Wayback capture](https://web.archive.org/web/20260820153426/https://www.dell.com/en-us/shop/dell-laptops/new-xps-14-laptop/spd/xps-da14260-laptop/useda14260ucto01) |
| 2026-10-30 | Same page: Windows 11 Home only, no Ubuntu in its OS options, $1,989.99 | [Live page](https://www.dell.com/en-us/shop/dell-laptops/new-xps-14-laptop/spd/xps-da14260-laptop/useda14260ucto01), extract: [evidence/dell-ucto01-2026-10-30.txt](evidence/dell-ucto01-2026-10-30.txt). The Ubuntu configuration URL now redirects to the general XPS 14 page, which offers Windows 11 Home only and still says "Ubuntu OS will not support Wi-Fi 7" | [Wayback capture](https://web.archive.org/web/20261030161330/https://www.dell.com/en-us/shop/dell-laptops/spd/xps14da14260) |
| 2026-10-30 | Ubuntu is still for sale: on the `da14260_reg_01` configuration ($2,249.99 as configured), the Operating System options are Windows 11 Home (default), Windows 11 Pro (+$80) and Ubuntu Linux 24.04 LTS (−$10, available). No Wayback captures of this page exist, so I can't show whether this option was ever removed | [Live page](https://www.dell.com/en-us/shop/laptop-computers/spd/xps14da14260/da14260_reg_01), extract: [evidence/dell-reg01-2026-10-30.txt](evidence/dell-reg01-2026-10-30.txt) |
| 2026-10-30 | Same `da14260_reg_01` configuration built twice with identical listed hardware and options (X7 358H, 32 GB, 1 TB, 2K 120 Hz, Dell Care Plus): **Ubuntu 24.04 LTS $2,939.99, Windows 11 Home $2,619.99**. Ubuntu costs $320 more, though the OS selector lists it at −$10. The Ubuntu build's tech specs also list a Microsoft 365 trial and a McAfee+ Premium subscription, neither of which runs on Ubuntu. For comparison, I paid $2,099.99 at Micro Center on 2026-08-24 for the same X7 358H / 32 GB / 1 TB model (Windows, retail) | Screenshots: [Ubuntu](evidence/dell-config-ubuntu-2026-10-30.png), [Windows](evidence/dell-config-windows-2026-10-30.png) |
| 2026-10-30 | Dell's XPS 14 page lists three preset configurations: Ultra 5 325 ($1,989.99), X7 358H 2K non-touch ($2,619.99), X7 358H QHD+ touch ($3,149.99). All three are Windows 11 Home. None is sold with Ubuntu | [Live page](https://www.dell.com/en-us/shop/dell-laptops/spd/xps14da14260), [Wayback capture](https://web.archive.org/web/20261030161330/https://www.dell.com/en-us/shop/dell-laptops/spd/xps14da14260) |
| 2026-10-30 | I report the failures to Canonical's certification team, asking whether this configuration passes plug detection and whether the certification still stands | [Launchpad question #825565](https://answers.launchpad.net/ubuntu-certification/+question/825565) |
| 2026-10-30 | I open a Dell support case with the same evidence, asking Dell to fix these on the certified Ubuntu image or state in writing that this configuration is not supported on Ubuntu | Awaiting Dell's reply |
| 2026-10-30 | I send the findings to OMG! Ubuntu and Liliputing, who covered the Ubuntu launch | Tip forms, confirmed sent |

## What the certification does and does not cover

Canonical still runs automated regression tests on both certified configurations: the X7 358H one was last tested on 2026-09-22 (kernel 7.0.0-38-generic, BIOS 1.8.2), the Ultra 5 325 one on 2026-08-20 (6.17.0-1032-oem). The public pages give the test dates, not the results.

Canonical's [24.04 desktop coverage guide](https://certification.canonical.com/docs/programmes/desktop/Desktop_Coverage_Guide_24.04/) lists what a certified laptop must pass. Among the blocking tests: sound output on "3.5mm headphones" and "3.5mm headset", and "Plug detection: when a new audio line input or output is plugged in the system, it needs to be recognized." Internal webcams are tested "to be able to take static pictures and video". Hardware video decode and IR cameras are not in the guide.

The headphone jack below fails that plug-detection requirement. I tested it on the 7.0.0-42 kernel the image installs today, not on the 6.17.0-1011-oem kernel it was certified on.

## On Dell's own Ubuntu image, today

Install: Dell's factory recovery image `XPS14DA14260_A00_Ubuntu2404_Recovery.iso`, then all updates. Dell's archives (`dell.archive.canonical.com noble somerville`, `somerville-hypno`) are active and nothing is pending. `fwupd` reports BIOS 1.12.0 and all device firmware as current.

### Hardware video decode does not work

The Intel media driver (VA-API) fails to initialise on the Panther Lake GPU:

```
libva: Trying to open /usr/lib/x86_64-linux-gnu/dri/iHD_drv_video.so
libva: /usr/lib/x86_64-linux-gnu/dri/iHD_drv_video.so init failed
```

- Ubuntu 24.04 ships `intel-media-va-driver` 24.1.0. Intel's own Ubuntu 24.04 repository tops out at 25.2.4.
- Intel's media-driver README first lists PTL (Panther Lake) in release 25.3. No package for Ubuntu 24.04 is that new, from Ubuntu, Dell or Intel.
- Result: every native video player and ffmpeg decodes on the CPU. It works only in Flatpak apps, whose runtime ships media driver 26.3.5.

### The headphone jack is never detected

With headphones plugged in, every jack control on the cs42l45 codec stays `off`, so audio never switches to the headphones:

```
cs42l45 IT 31 Microphone Jack  : values=off
cs42l45 IT 33 Headset Jack     : values=off
cs42l45 OT 43 Headphone Jack   : values=off
cs42l45 OT 45 Headset Jack     : values=off
```

The same thing happened on Fedora 44. The only workaround is to stop the UCM profile from reading the jack sensor, so you can pick the headphones by hand.

### The IR (face login) camera has no driver

The Himax HM1092 IR sensor is present in ACPI (`HIMX1092:00`) but no driver binds to it, and the kernel has no HM1092 module. There is no face login on Linux.

### Dell's "OEM" kernel is now just the generic kernel

The OEM kernel metapackage Dell's image installs, `linux-image-oem-24.04d`, now depends on `linux-image-generic-hwe-24.04`. The machine boots generic 7.0.0-42, not the 6.17 OEM kernel line the configurations were certified on.

## Bottom line

Dell certified this laptop for Ubuntu and still sells it with Ubuntu. The image it ships can't decode video on its own GPU, can't detect headphones, and has no driver for its IR camera, and none of the updates available today fix any of that.

## My question to Dell and Canonical

What about this is "supported"? Did you give up?

## Reproduce

Commands and full outputs: [evidence/xps-outputs.md](evidence/xps-outputs.md).
