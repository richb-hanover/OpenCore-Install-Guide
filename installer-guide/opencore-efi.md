# Adding The Base OpenCore Files

* Supported version: 0.6.0

To setup OpenCore’s folder structure, grab the EFI folder from [OpenCorePkg's releases](https://github.com/acidanthera/OpenCorePkg/releases/). Regarding DEBUG versus RELEASE version:

* **DEBUG**: Can greatly help with debugging boot issues, however can add some noticeable delay to boot times. Once installed you can easily transition to RELEASE
* **RELEASE**: Much snappier boot times, however virtually no useful DEBUG info is provided in OpenCore making troubleshooting much more difficult.

Place the downloaded EFI folder (from OpenCorePkg) at the root of your EFI partition. Check the following to be sure the spelling and capitalization are correct:

* The EFI partition must have a top-level folder named **EFI** (you may need to change the name of the downloaded folder.)
* That top-level folder must contain folders named **BOOT** and **OC**
* Those folders should substantially match the image below

**Note**:

* Windows users: MakeInstall will already have done this on the `BOOT` USB drive
* Linux users: This is the `OPENCORE` partition we created earlier
  * Note that Method 1 only creates 1 partition, while Method 2 creates 2 partitions

![base EFI folder](../images/installer-guide/opencore-efi-md/base-efi.png)

The OpenCorePkg comes with a bunch of files in `Drivers` and `Tools` folder. You don't need most of these:

* **Remove from Drivers:**
  * AudioDxe.efi
    * Unrelated to Audio support in macOS
  * CrScreenshotDxe.efi
    * Used for taking screenshots in UEFI, not needed by us
  * OpenUsbKbDxe.efi
    * Used for OpenCore picker on **legacy systems running DuetPkg**, [not recommended and even harmful on Ivy Bridge and newer](https://applelife.ru/threads/opencore-obsuzhdenie-i-ustanovka.2944066/page-176#post-856653)
  * UsbMouseDxe.efi
    * similar idea to OpenUsbKbDxe, should only be needed on legacy systems using DuetPkg
  * NvmExpressDxe.efi
    * Used for Haswell and older when no NVMe driver is built into the firmware
  * XhciDxe.efi
    * Used for Sandy Bridge and older when no XHCI driver is built into the firmware
  * HiiDatabase.efi
    * Used for fixing GUI support like OpenShell.efi on Sandy Bridge and older
  * OpenCanopy.efi
    * This is OpenCore's optional GUI, we'll be going over how to set this up in [Post Install](https://dortania.github.io/OpenCore-Post-Install/cosmetic/gui.html) so remove this for now
  * Ps2KeyboardDxe.efi + Ps2MouseDxe.efi
    * Pretty obvious when you need this, USB keyboard and mouse users don't need it
    * Reminder: PS2 ≠ USB

* **Remove (almost) everything from Tools:** There are way to many to list. I recommend keeping OpenShell.efi for troubleshooting purposes

A cleaned up EFI:

![Clean EFI](../images/installer-guide/opencore-efi-md/clean-efi.png)

The next step is to gather files and place the necessary drivers and kexts for **your** hardware into their respective folders. 

> Clover users: UEFI drivers from Clover are not supported with OpenCore!(EmuVariableUEFI, AptioMemoryFix, OsxAptioFixDrv, etc). Please see the [Clover firmware driver conversion](https://github.com/dortania/OpenCore-Install-Guide/blob/master/clover-conversion/clover-efi.md) for more info on supported drivers and those merged into OpenCore.

Here's what a populated EFI ***can*** look like (yours will be different):

![Populated EFI folder](../images/installer-guide/opencore-efi-md/populated-efi.png)

**Reminder**:

* SSDTs and custom DSDTs(`.aml`) go in ACPI folder
* Kexts(`.kext`) go in Kexts folder
* Firmware drivers(`.efi`) go in the Drivers folder

# Now with all this done, head to [Gathering Files](../ktext.md) to get the needed kexts and firmware drivers
