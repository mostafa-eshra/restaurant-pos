# Restaurant POS Desktop Downloads

Official installer and update repository for the Restaurant POS desktop
applications.

The desktop application opens the restaurant POS web app and provides native,
silent receipt printing through printers installed in the operating system.
This repository contains compiled production releases only; the source code is
maintained in a private repository.

## Download

Download installers from the [latest release](../../releases/latest).

Choose the application assigned by your POS administrator:

| Application | Variant | Windows installer | Linux package |
| --- | --- | --- | --- |
| Innov8 POS | Standalone | `Innov8-POS-production-<version>-win-x64.exe` | `Innov8-POS-production-<version>-linux-x64.AppImage` |
| Menuv8 POS | SaaS | `Menuv8-POS-production-<version>-win-x64.exe` | `Menuv8-POS-production-<version>-linux-x64.AppImage` |

- Use **Innov8 POS (Standalone)** for standalone restaurant installations.
- Use **Menuv8 POS (SaaS)** when your POS administrator supplies a Tenant ID.
- Linux packages are available only when they are included in the selected
  release.

Files ending in `.yml` or `.blockmap` are auto-update metadata used by installed
applications. They are not installers.

## Install on Windows

1. Open the [latest release](../../releases/latest).
2. Download the `.exe` for the required application.
3. Run the installer and complete setup.
4. Launch the application and open **Settings** if it is not shown
   automatically.
5. Select the receipt printer, enter its paper width, and save the settings.
6. For Menuv8 POS, also enter the required Tenant ID supplied by your POS
   administrator.

Windows installers are intentionally unsigned. Windows may display an
**Unknown publisher** or Microsoft Defender SmartScreen warning. Confirm that
the file was downloaded from this repository before continuing.

## Install on Linux

When an AppImage is included in the release, download it, make it executable,
and run it:

```bash
chmod +x *-linux-x64.AppImage
./Innov8-POS-production-*-linux-x64.AppImage
```

For Menuv8 POS, run the corresponding `Menuv8-POS` AppImage instead. A graphical
desktop session and an operating-system printer driver are required.

## Configure printing

Open **Settings** with `Ctrl+Shift+P` (`Cmd+Shift+P` on macOS) while the
application is focused.

From Settings you can:

- select the default receipt printer;
- configure the receipt paper width;
- send a test receipt;
- re-detect printers after operating-system changes; and
- clear POS cookies, local storage, cache, and service workers.

Install the printer manufacturer's normal graphical driver. Do not use a
**Generic / Text Only** driver, because it may print spool data as unreadable
characters.

Menuv8 POS additionally requires a Tenant ID. The application opens Settings at
startup when the Tenant ID is missing. Innov8 POS does not display or require
the Tenant ID field.

## Application updates

Installed production applications check this repository for newer versions.
When an update is available, the application provides controls to download it
and restart to install it.

The applications use independent update channels:

- Innov8 POS uses the `standalone` channel.
- Menuv8 POS uses the `saas` channel.

An installation downloads updates only from its own channel, so one application
variant will not replace the other. Finish the current sale before installing an
update.

## Important notes

- Install only the application assigned by your POS administrator.
- Installers are built for 64-bit Windows; optional AppImages are built for
  64-bit Linux.
- The workstation must be able to reach the configured POS service and its
  receipt printer.
- Published release assets and metadata belong together. Do not rename, edit,
  replace, or redistribute individual release files.
- Never post Tenant IDs, private POS URLs, customer data, or other credentials
  in public issues.

## Support

If installation, configuration, updating, or printing fails, contact your POS
administrator and provide the application name, version, operating system, and
error message. Do not include credentials or customer information.

## License

This software is proprietary and is distributed only for authorized Restaurant
POS deployments.
