# PC Migration Tool --- By NORTH

**PC Migration Tool --- By NORTH** is a Windows migration utility
designed to make reinstalling Windows or moving to a new PC easier.

It uses two applications:

``` text
PC Migration Tool - Backup - By NORTH.exe
PC Migration Tool - Restore - By NORTH.exe
```

Run **Backup** before reinstalling or replacing Windows, then run
**Restore** after the new Windows installation is ready.

## Features

### Personal Files Backup

The Backup tool preserves common Windows user folders:

-   Desktop
-   Documents
-   Downloads
-   Pictures
-   Videos
-   Music
-   Saved Games

### Browser Data

Supported browser data includes:

-   Google Chrome bookmarks
-   Microsoft Edge bookmarks
-   Brave bookmarks
-   Mozilla Firefox profile data

### Wi-Fi Profiles

Windows Wi-Fi profiles are exported so supported profiles can be
imported again after Windows is reinstalled.

The tool does **not** request plaintext Wi-Fi passwords.

### Installed Programs Inventory

The tool creates an inventory of installed applications containing
information such as:

-   Program name
-   Version
-   Publisher
-   Installation location when available

The inventory is saved in both CSV and readable text formats.

> \[!NOTE\] Installed programs are inventoried, not copied. Applications
> normally need to be reinstalled after Windows is installed again.

### System Information

The backup also records useful information about the original Windows
installation:

-   Computer manufacturer and model
-   Installed RAM
-   GPU and driver version
-   Installed driver inventory
-   Printers
-   Windows culture information
-   Time-zone information

### Migration Manifest

Every backup contains migration metadata including the original computer
name, Windows user, Windows version, and backup creation date.

## How to Use

### Before Reinstalling Windows

1.  Connect a USB flash drive, external SSD, or external HDD.
2.  Launch:

``` text
PC Migration Tool - Backup - By NORTH.exe
```

3.  Select the external drive.
4.  Wait for the migration backup to complete.
5.  Verify that the `PC Migration` folder exists on the external drive
    before reinstalling Windows.

### After Reinstalling Windows

1.  Complete the new Windows installation.
2.  Connect the external drive containing the migration backup.
3.  Launch:

``` text
PC Migration Tool - Restore - By NORTH.exe
```

4.  Select the external drive and the migration backup.
5.  Confirm the restoration.
6.  Reinstall programs and drivers as needed using the generated
    inventories as references.

## Backup Structure

Migration backups are stored inside:

``` text
PC Migration\
```

Example:

``` text
PC Migration/
└── COMPUTER_USER_2026-09-30_18-30-00/
    ├── Personal Files/
    │   ├── Desktop/
    │   ├── Documents/
    │   ├── Downloads/
    │   ├── Pictures/
    │   ├── Videos/
    │   ├── Music/
    │   └── Saved Games/
    │
    ├── Browser Data/
    │   ├── Chrome/
    │   ├── Edge/
    │   ├── Brave/
    │   └── Firefox/
    │
    ├── System/
    │   ├── Installed_Programs.csv
    │   ├── Installed_Programs.txt
    │   ├── Drivers.csv
    │   ├── Printers.csv
    │   ├── GPU.csv
    │   ├── Computer.json
    │   └── Wi-Fi profiles
    │
    ├── Logs/
    │   └── migration_backup.log
    │
    └── Migration_Info.json
```

## External Drive Detection

PC Migration Tool scans Windows storage devices for removable drives and
storage connected through USB.

When multiple compatible drives are connected, the program lets you
select the correct device.

Displayed information can include:

-   Drive letter
-   Volume label
-   Available space
-   Total capacity
-   Device model

## Backup Engine

Personal files are copied using Windows **Robocopy**.

The migration process copies the selected data to external storage
without intentionally deleting the original files from the PC.

Logs are generated to help identify copy errors or skipped files.

## Restore Behavior

The Restore application searches the selected external drive for
migration sets stored under:

``` text
PC Migration\
```

Supported personal folders are copied back to the current Windows user's
folders.

Chrome, Edge, and Brave bookmarks can be restored to their supported
profile locations.

Firefox profile data is preserved in the backup, but the tool does not
force-overwrite an active Firefox profile.

Installed-program and driver inventories remain available as references
when rebuilding the Windows installation.

## Requirements

-   Windows 10 or Windows 11
-   USB flash drive, external SSD, or external HDD
-   Enough free external storage for the data being backed up

## Important Information

PC Migration Tool is designed to assist with migration. It is **not a
complete disk-image or cloning solution**.

Installed applications themselves are not migrated, and some
application-specific or machine-specific settings may need to be
configured again after Windows is reinstalled.

Before formatting or replacing a PC:

-   Verify that the migration backup completed successfully.
-   Check that important files exist on the external drive.
-   Keep another independent copy of irreplaceable data whenever
    possible.
-   Do not disconnect the external drive during backup or restoration.

## Author

Developed by **NORTH**.

## Disclaimer

This software is provided as a migration and backup utility.

Test backup and restore operations with non-critical data before relying
on the application for important files.

The author is not responsible for data loss, incomplete migrations,
hardware failure, interrupted transfers, accidental drive selection, or
misuse of the software.
