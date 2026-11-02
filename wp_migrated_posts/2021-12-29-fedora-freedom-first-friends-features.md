---
title: "Fedora  - freedom, first, friends, features"
date: 2021-12-29
categories: 
  - "fedora-linux"
coverImage: "fedora-34-offical-wallpaper-image.jpeg"
---

![](images/fedora-35-blog-image-000-edit-title-.jpg)

## Introduction

**Hi!, i'm lwalinux**, and welcome to my journey into the new world of revolving doors in the Fedora Linux distribution community, as I embark on a 12 Month Mission critical project to run, work, deploy, create everything on Fedora 35 "WorkStation / SilverBlue" on (bare metal hardware) Toshiba z30 / Microsoft Surface Pro... But in the mean time, here are my views on the latest Fedora 35 editions.

## **Polished Fedora Linux 35**

True to Fedora foundations of “First” & “Features,” the release includes

- new **GNOME 41**,
- updated developer tools,
- new programming languages,
- new power management profiles,
- parental controls,
- and improvements in the management of other third-party apps.

The release cycle also includes "**Fedora Kinoite**", a new edition based on **"Fedora Silverblue’s OSTree"** technologies. In addition, the edition features the **KDE Plasma desktop**.

_**Fedora Linux 35**_

Fedora Linux 35 is all about the polish. True to its [four foundations](https://docs.fedoraproject.org/en-US/project/) of “**Freedom**,” “**Features**,” “**First**,” & “**Friends**,” Fedora 35 focuses on extending existing features, refinements, and improved support. The Fedora community seeks to create a desktop PC with bleeding-edge technologies to level up the experience of using Fedora Linux. Whether you use Fedora as a Workstation, a cloud-based image, or a Linux container image, you’ll find improvements that make Fedora 35 a nice upgrade.

You can get Fedora Workstation 35 from the [official website](https://getfedora.org/workstation/download/). You can also upgrade your existing Fedora through the terminal with **dnf system-upgrade** or using GNOME Software.

<figure>

![](images/screenshot-2021-12-29-at-01.38.27.png)

<figcaption>

Fedora 35 Gnome Desktop & Dock

</figcaption>

</figure>

## Desktop features & environments

![](images/screenshot-2021-12-29-at-01.52.06.png)

**Fedora 35 Workstation** now ships with **GNOME 41**. It brings new changes like improved multitasking, a Mobile network connections Settings panel, a new remote desktop client (Connections app). Its redesigned and improved software center makes it easier to browse and discover applications. And that’s not all GNOME 41 also includes touchpad gestures, power profiles, and other performance enhancements.

Additionally, the horizontal workflow introduced in GNOME 40 (shipped in [Fedora 34](https://www.fosslinux.com/46272/things-to-do-after-installing-fedora-workstation.htm)) features new design enhancements to improve user experience.

## Gnome 41 redesigned sofware centre

![](images/screenshot-2021-12-29-at-02.28.09.png)

## Gnome 41 Power Profiles

![](images/screenshot-2021-12-29-at-02.37.12.png)

## Gnome 41 Music centre

![](images/screenshot-2021-12-29-at-02.37.44.png)

## Fedora's Desktop Environments

**Improved support for third-party application and software repositories**

The redesigned Software store includes improved support for Flatpak containers. In addition, Fedora 35 contains a new set of applications from Flathub in the third-party repositories. However, you have to enable them after you install Fedora 35. The apps are provided by a Flathub remote curated by Fedora Project contributors. Select apps include Bitwarden, Discord, Postman, Microsoft Teams, Skype, Zoom, and Minecraft.

I bet you the Fedora team will expand the list. I expect to see more Flatpaks in future releases. Moreover, you can get a complete set of Flathub apps by adding the [Flathub remote](https://flatpak.org/setup/Fedora/).

Note that Flatpak applications run in containers that are separate from your system. Containers increase security since the apps don’t have unfettered access to the entire system.

You can, of course, also still install programs with RPM.

**Pipe Wire**

PipeWire made its introduction in Fedora Workstation 34 as the default audio and video server for Fedora releases. It was a significant addition to Fedora 34, and it continues to mature with new releases. PipeWire in Fedora 35 features improved Bluetooth handling, bug fixes, support for pass-through of S/PDIF signals over optical and HDMI connections.

WirePlumber also makes an introduction as the new and advanced session manager to replace PipeWire Media Session. WirePlumber is more advanced with support for plugins and scripting with Lua.

**Improvements on Wayland on Nvidia**

Nvidia’s proprietary driver now includes massively enhanced support for Wayland, thanks to tight collaboration between the Red Hat, Nvidia teams, and Fedora. It enables users to run applications that don’t have native Wayland support to benefit from 3D support under NVIDIA drivers.

Moreover, libinput in Fedora 35 now includes support for high-resolution scrolling with mouse wheels.

**System-wide changes**

As custom in any Fedora release cycle, all Fedora editions and spins use a common base with updates on the Linux kernel, system libraries, developer tools, and much more. Some notable system-wide changes include the following:

- Adoption of a policy change allows packagers to make a technical case for using GCC or Clang/LLVM to build their packages
- GNU Toolchain update
- Firewalld 1.0 package update

**DNS over TLS (DoT) support**

Privacy is a critical aspect in this day and age. The Fedora project team has introduced support for DNS over TLS (DoT). This technology will attempt to send DNS requests over TLS. If you’ve chosen custom DNS servers that offer encryption, you can enjoy additional protection from passive network attacks.

In essence, this means that your ISP shouldn’t be able to spy on your browsing history or activities, which is a welcome for all.

## Developer Tools

As with every Fedora release cycle, developers get new programming languages and system library updates. The underlying packages and toolchain and get updates with the latest stable version.

- Python 3.10
- Node.js 16.x
- Perl 5.34
- PHP 8.0
- Binutils 2.36
- gcc 11
- glibc 2.34
- RPM 4.17
- binutils 2.37
- gdb 10.2
- LLVM 13

## **Linux Kernel 5.14**

The new Linux 5.14 kernel has found its way into Fedora 35. It has brought many ARM-specific improvements primarily related to GPUs (support on AMD Radeon graphics cards). It also features improved support for USB 4.

## **Fedora Server family**

**Fedora cloud**

A notable improvement in **Fedora 35 Cloud** images is the introduction of **hybrid BIOS+UEFI boot** support. In essence, if UEFI doesn’t work, you still have legacy BIOS support as a fallback.

**Btrfs** is now the default file system for **Fedora Cloud**. [Btrfs](https://btrfs.wiki.kernel.org/) was introduced as the default file system in Fedora Workstation 34 and will see increased adoption in the Fedora family. You can take advantage of transparent compression to save filesystem space or other [features of Btrfs](https://www.fosslinux.com/46315/btrfs-file-system-fedora-linux.htm).

## **Fedora Kinoite: A new Fedora KDE edition**

_**Fedora Kinoite**_

[Fedora Kinoite](https://kinoite.fedoraproject.org/) is the newest kid in the block. Fedora Linux 35 introduces Fedora Kinoite, a new edition based on Fedora Silverblue’s underlying technologies (Fedora Linux, Podman, RPM OSTree). It features KDE Plasma desktop by default, instead of GNOME.

Fedora project team describes Fedora kinoite as a next-generation operating system. It lets you manage everyday work, surf the web, manage files, and get productive without worrying about breaking your system.

Learn more about the project from Fedora Kinoite [official home page](https://kinoite.fedoraproject.org/) or [Download](https://kinoite.fedoraproject.org/download) either the X86\_64 or AArch64 architecture and give it a spin.

Get the complete list of changes from the official [changelist](https://fedoraproject.org/wiki/Releases/35/ChangeSet) or the [official Fedora 35 announcement](https://fedoramagazine.org/announcing-fedora-35/).

![](images/screenshot-2021-12-29-at-02.38.13.png)

## **Final Thoughts**

Fedora Linux 35 is all about the polish and refinement from Fedora 34. This release focuses on improvements to the Fedora Linux system. And true to its philosophy of “First,” the Fedora project team introduces all the latest packages, GNOME 41, and server technologies. You will notice improvements to your system with the introduction of Linux Kernel 5.14 and GNOME 41.

What it comes down too with any latest Fedora release, is that by default it is shipped with the latest versions of LibreOffice, Firefox, and other preinstalled apps to get started with your new operating system.

> lwalinux

## Freedom, First, Friends, Features.

<figure>

![](images/fedora-34-offical-wallpaper-image-1.jpeg)

<figcaption>

Fedora Linux

</figcaption>

</figure>
