Step-by-step guide to install Ubuntu 16.04. LTS 64-bit on a MacBook Pro Retina 15" Mid 2014 with i3wm.

## Overview

I finally switched to a Macbook Pro, and immediately found myself needing to get Ubuntu 16.04 and i3 installed. Here's a guide in the hopes that it's helpful.

## Required Downloads
- Ubuntu 16.04 Desktop 64-bit ISO:
  http://www.ubuntu.com/download/desktop

## Notes

- This installation should result in having Ubuntu dual-boot with MacOS.

- We'll use REFind https://sourceforge.net/projects/refind/ to manage booting between MacOS and Ubuntu.

- This guide will cover how to install and configure i3 window manager, but if you choose to not install i3 then Unity will work just fine!

- When you first boot into Ubuntu after installation, Wifi will not work. You'll need to either use an external Wifi card/usb, use a USB to Ethernet adapter, or copy `dkms` and `bcmwl-kernel-source` to a USB drive, and install those packages. This workaround is needed, as the Broadcom drivers required to get networking on the Macbook are not installed by default.

## Creating the bootable USB

#### From MacOS:
- Download the UNetbootin USB installer: http://unetbootin.github.io/
- Using Unetbootin and your downloaded ISO, create the bootable USB.
- Further instructions here: http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-mac-osx

#### From another Ubuntu Installation:
- Use a USB stick and the Startup Disk Creator to make a live disk with the Ubuntu 16.04 ISO you've downloaded.
- Further instructions on this on the Ubuntu website: http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-ubuntu

#### From Windows:
- Download Rufus USB installer: https://rufus.akeo.ie/
- Using Rufus and the downloaded ISO, create the bootable USB.
- Further instructions here: http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows

## Installing rEFind
- reFind is a useful tool for managing multiple OS booting on the Macbook.
- From MacOS, go install rEFind https://sourceforge.net/projects/refind/
- When you boot, you'll now see a new boot menu (if you have Windows through bootcamp, they'll show up here)
![rEFind Boot Screen][bootScreen]
[bootScreen]: https://a.fsdn.com/con/app/proj/refind/screenshots/refind.png "rEFind Boot Screen"

## Installing Ubuntu
- Plug in your Ubuntu USB drive, and boot while holding the `option` key.
- Select the `EFI USB` drive, and boot from it.
- Click the `Install Ubuntu` option, and install Ubuntu Alongside MacOS.
- Note: if you have an existing Windows partition like I did, you'll need to be careful making additional partitions, but triple-booting is beyond the scope of this guide :)
- Another Note: I suggest you keep Unity installed for now. Many i3wm guides suggest your remove it, but the GUIs for adding drivers and managing the system are often much easier from Unity than from i3. It's simple to remove Unity if you find you don't need it, but it can be useful.
- Congradulations! You have Ubuntu dual-booted on your Mac.
- Stop here if you're happy with Unity, and enjoy your new setup!

## Installing i3wm

![i3][i3Screen]
[i3Screen]: https://i3wm.org/screenshots/i3-1.png "i3 Screen"


#### Why i3?
- i3 is my Window Manager of Choice™, accept no substitutes!
- I use i3 because I like being able to tile and manage windows entirely from the keyboard. i3 has plaintext configuration files, and is incredibly customizeable.
- You can use i3 to bind keys to any terminal command, program, or script.
- More information can be found on their site: https://i3wm.org/

#### The installation
- From a terminal, run this command to install i3: `sudo apt-get install i3`
- Once you've installed i3, you can logout of Unity, and then switch to the i3 option for your desktop environment.

#### First run
- When you first run i3, you'll be prompted to generate your configuration file, and pick your modifier key. (I suggest the ⌘ key for your mod key on a Macbook)
- To keep you from getting lost if this is your first time with i3, here are some helpful default commands:

```
Mod+Enter            # Starts a terminal session
Mod+Shift+e          # Prompt to exit i3wm
Mod+d                # Brings up dmenu, which finds commands from your $PATH
```

#### i3 Configuration
- i3 works by using a modifier key (Mod) to bind keys to specific terminal or window commands.
- A good explanation of how window movement, customization, and nagivation works can be found on their user guide: https://i3wm.org/docs/userguide.html
- My configuration file is on GitHub: https://github.com/jordanwdunne/i3-configuration/blob/master/config

#### i3Status Configuration
- One of the first things you're likely to notice is the status bar on top of your screen. This is actually a configurable i3Status bar by default, and you can adjust it to show your networking, volume, VPN, battery, and other system information.
- In Ubuntu 16.04, this configuration file is located in `/etc/i3Status.conf`, and cand be edited to suit your needs.
- There are several good examples of functions on i3Status' page: https://i3wm.org/i3status/manpage.html
- You can also check out my 'i3Status.conf' file on GitHub: https://github.com/jordanwdunne/i3-configuration/blob/master/i3status.conf

## Have fun!
Thanks for reading my guide, I hope it was helpful. Ubuntu's great, and using i3 as the window manager is amazing for productivity.
