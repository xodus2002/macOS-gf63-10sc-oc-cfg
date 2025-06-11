<p align="center" style="font-size:4vw; font-weight:bold">OpenCore config for MSI GF63 Thin 10SC</p>

![453975379-06511495-be5e-4c33-b4db-88ac5d29d0b6](https://github.com/user-attachments/assets/856de9a1-3c4c-40f6-8037-d95a292ea3fd)

## My specs
CPU: Intel Core i5-10300H @ 2.5GHz (turbo 4.50GHz) 4c/8t

RAM: 2x16 GB DDR4 3200MHz

dGPU: NVIDIA GTX 1650 Max-Q 4GB GDDR6 (obviously this won't be used)

iGPU: Intel UHD 630

# What works and doesn't work, and partially works
Works: WiFi, keyboard, touchpad, USB ports

Doesn't work: Bluetooth, dGPU (only up to High Sierra)

Partially works: Backlight (sometimes it does turn on, sometimes doesn't, only fix is to close the lid, then open it back up or wait till it refreshes the screen)

# Before doing the install, disable these options in the BIOS
![image](https://github.com/user-attachments/assets/74ee35b7-a238-45e1-b10c-fb40278eeb60)

# How to
### Requirements
* The UUID, SerialNumber, ROM and MLB from [this guide](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#platforminfo)
* A USB drive with atleast 2 GB of storage, formatted as FAT32
* Python 3
* A LOT of patience (atleast 1-2 hours, depending on your internet speed)
* The BaseSystem.dmg from [this guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html)
* A brain

1: Download my OpenCore config and copy the "EFI" folder to your USB drive. 

2: Download the BaseSystem.dmg and BaseSystem.chunklist from the 4th requirement guide.

3: Create the folder "com.apple.recovery.boot" in the root of your USB drive.

4: Copy the BaseSystem.dmg and BaseSystem.chunklist to "com.apple.recovery.boot"

5: Use the first requirement guide to generate your UUID, SerialNumber, ROM and MLB (use MacBookPro16,3 SMBIOS since processor has 4 cores)

### !! REQUIRED SINCE THIS IS AN ONLINE INSTALLER !!

6: Use ProperTree to edit "EFI\OC\Kexts\itlwm.kext\Contents\Info.plist",

6.1: Find the key "WiFiConfig"

6.2: Go to WiFi_1

6.3: Edit "ssid" with your SSID (name of your WiFi)

6.4: Edit "password" with your WiFi password

### !! REQUIRED SINCE THIS IS AN ONLINE INSTALLER !!

7: Reboot your machine and boot to the USB stick. Press SPACE then press ENTER to "NO NAME (dmg)", and let it boot.

### For dualbooting
8.1.1: Make sure that you have split your partition in Windows with minimal 30 GB of storage, recommended 50 GB or more

8.1.2: In Disk Utility, format the unused partition as APFS and name it (for example "Macintosh HD")

### For installing directly on a disk

8.2.1: Create 2 partitions, one with atleast 128 MB, and the rest of the disk.

8.2.2: Format the 128 MB disk as FAT32, and name it "EFI." This will be your EFI partition.

8.2.3: Format the rest of the disk as APFS and name it (for example "Macintosh HD")

9: Install Mac OS to the disk.

10: Still continue to boot to the USB since the EFI isn't configured yet.

11: Press SPACE then press ENTER on the MacOS partition (listed as "Macintosh HD", "MacOS Sequoia", ...)

12: Give it time to configure. Takes about 30 minutes.

12.1: Set the OS up.

13: After setting it up, copy the EFI folder to the EFI partition.

14: To manage your WiFi connections, install [HeliPort](https://github.com/OpenIntelWireless/HeliPort)

<p align="center" style="font-size:4vw; font-weight:bold">Congratulations, you have macOS on your MSI gaming laptop!</p>
