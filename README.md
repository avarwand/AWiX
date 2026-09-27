<div align="center">

# A Windows Installer XML 1.4.55.1

</div>

A **powerful, modern GUI tool** for **turning any Windows program into a professional installer** (**MSI** or **EXE**), with a **fully designable setup wizard**, **clean uninstall**, and **reusable configurations**. Fast, safe, and without writing a single line of installer code.

> _No XML | No command line | Full control_

---

## What's New in v1.1.32

- **Wizard Page Texts**: Change the title and text of the start and finish pages (*Welcome*, *Interrupted*, *Error*, *Completed*), with a **Default** button to restore the originals
- **Installed Name**: The installed program is always named after the **Application Name in lower case** (e.g. `AFTS Portable.exe` → `afts.exe`), whatever the input file is called
- **Much faster**: The window opens instantly, WiX extensions are cached, and themed wizard artwork is generated several times faster
- **Info window** with a **live search**: type the first letters of a word, every match is marked and the matching lines are listed
- **Export / Import Config**: Save all settings, including icon, logo and banner images, in **one `.awix` file**

---

## Main Features
- **Create MSI or EXE installers** from a single `.exe` or a complete program folder  
- **Deep program folders supported** (thousands of files, sub-folders like `_internal`)  
- **Per-machine or per-user installation**, chosen by the end user in the wizard  
- **Clean default folders**: `Program Files\<Company>\<AppName>` or `%LOCALAPPDATA%\<Company>\<AppName>`  
- **Optional Desktop and Start Menu shortcuts**, selectable in the wizard  
- **Complete uninstall**: removes the program folder, including files the program created itself  
- **Automatic upgrades**: a newer version replaces an older one in place  
- **"Open With" registration** for your file extensions  
- **Fully designable setup wizard**: layouts, themes, logo, banner, fonts, texts  
- **Reusable configurations** (`.awix`) with embedded images  
- **Progress bar and detailed build log**  
- **Dark-mode GUI** with clean layout  
- **Fully GUI-based**: no XML or command-line knowledge required  

---

## Setup Wizard Design

Shape the installation wizard your users will see:

- **Two layouts**:
  - *Classic*: License page with shortcut options and an **Advanced Options** button → scope → folder → ready
  - *Single page*: License, shortcuts, **"Just for me" / "All users of this PC"** and the install folder, all on **one page**
- **Themes**: Presets like *Midnight Violet*, *Ocean Blue*, *Emerald Night*, *Sunset Orange*, *Crimson Dark*, *Light Clean*, or your **own colours** (Background, Primary, Secondary, Text, Secondary text)
- **Wizard Logo**: PNG / GIF / BMP with transparency, **per-page selection** with an **individual opacity** for each page, optional **reverse colour**
- **Banner**: your own banner image with **opacity**, **blur**, and **reverse colour**
- **Tick Box Style**: frameless Windows tick boxes, clickable labels, or themed image tick boxes
- **Texts**: Window title, start / finish page texts, license font and size, page font and size
- **Artwork Sharpness**: crisp images for any display scaling (100 % – 200 %)

---

## Configurations

Build the same installer again in seconds:

- **Export Config** saves all package details and every wizard setting into **one `.awix` file**
- The **icon, logo, banner and dialog images are embedded**, no loose files needed
- **Import Config** restores everything, and unpacks the images next to the configuration file

---

## Build Process

- **One click**: *Generate + Build Installer*
- **Progress bar** with a status line for every step, **red** with the reason if something fails
- **Detailed build log** with Copy and Clear
- **Generate .wxs only**: create the installer source without building
- **Automatic output path and file name**: `<AppName>-<Version>-Setup-x64.msi`
- Temporary build files are removed automatically (or kept, on request)

---

## System Requirements

- **OS**: Windows 10 / Windows 11 (64-bit)  
- **WiX Toolset** v4 or newer (the `wix` command must be available)  
  ```powershell
  dotnet tool install --global wix
  ```
  WiX v7 or newer: accept the WiX *Open Source Maintenance Fee* EULA (checkbox in AWiX, see [wixtoolset.org/osmf](https://wixtoolset.org/osmf))

The required WiX extensions are added automatically.

---

## How to Use

1. Download the [desired Version here...](https://github.com/avarwand/AWiX/releases)
2. Unzip it > Start **AWiX.exe** (or install it, _for the installer version_)
3. **Package Options**: enter name, version, publisher, company, and choose icon, license and your program
4. **Wizard Design** *(optional)*: choose layout, theme, logo, banner and texts
5. Click **Generate + Build Installer**
6. Watch the progress → **Done!** Your installer is in the output folder

Also available in the footer:

- **INFO**: Complete documentation with search
- **IMPORT CONFIG / EXPORT CONFIG**: Load or save all settings

---

## Safety Notes

* Your original program files are **never modified**, they are only read and packed
* Uninstall removes the full program folder **only when its name matches the application**, so an existing folder chosen by mistake is never wiped
* The **empty** company folder is removed on uninstall, never one that still contains other programs
* Installers are built in a separate temporary folder, which is never packed into the installer itself
* Every build is logged in detail, errors are shown clearly
* Please **test every installer** before distributing it

---

## Good to Know

Setup wizards of MSI installers are drawn by Windows Installer, which sets a few limits:

* No hover effects on buttons
* Clickable elements get a thin frame drawn by Windows
* The license box and the folder field keep the Windows look
* The colour of the wizard's title bar is set by Windows, only its text can be changed

---

## Use Cases

* Publishing your own tools with a **professional installer**
* Offering an **MSI package for companies and IT departments** (Group Policy, Intune, SCCM, silent install)
* Turning **portable applications** into installable programs with shortcuts and a clean uninstall
* **Branding** the setup wizard with your own colours, logo and texts
* Rebuilding installers for **new versions** in seconds with saved configurations

---

## Contributing

This project is released as **freeware**.

While primarily maintained by the author, suggestions, bug reports, and improvement ideas are welcome via email.

Pull requests are currently not accepted.

---

## License

**AWiX is freeware**, released under a custom End User License Agreement (EULA) by **Avarwand**. *(Freeware describes the price, free of charge; the EULA is the agreement that sets the terms below.)*

In short, you are free to:

* **Use** AWiX free of charge, for both personal and commercial purposes
* **Create and distribute installers** with AWiX for your own or your clients' software, free or commercial, the installers you create belong to you
* **Share** AWiX with anyone, redistributing, hosting, mirroring, and promoting it is welcome, as long as it is passed on **complete and unmodified**, **free of charge**, and with clear credit to **Avarwand**

And you may not:

* Sell AWiX, monetize access to it, or lock it behind paywalls, donations, surveys, registration walls, or paid bundles
* Reverse engineer, decompile, or modify it (except to the limited extent permitted by applicable law)
* Claim it as your own work, or remove its copyright and branding notices

AWiX is provided **"as is"**, without warranty of any kind. The WiX Toolset is a separate product of its own authors, with its own license.

*This summary is for convenience only. The legally binding terms are in the [LICENSE](LICENSE.md) file included with every release and in this repository.*

---

**Developed by Avarwand Software**  
**Latest Update: September 2026**  
**Initial Release: September 2026**  

---

## Contact

**Avarwand Support**  
📧 [avarwand@yahoo.com](mailto:avarwand@yahoo.com)  
🌐 [github.com/avarwand](https://github.com/avarwand/)

© 2026 Avarwand. All rights reserved.

---
