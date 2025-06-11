# OpenCore config for MSI GF63 Thin 10SC

# Some snags that you need to know (IMPORTANT)
Backlight sometimes is iffy on macOS install, the only "fix" is to close the lid and open it back or wait till it refreshes the screen. Bluetooth is a bit buggy so it's not added on this config.

# How to
Before doing anything, replace UUID, SerialNumber, ROM, MLB with Propertree and make sure you have a higher capacity, FAT32 formatted USB drive and download my OpenCore config and copy the "EFI" folder to your USB drive. Download the macOS recovery (10.15.4 and higher, Tahoe works as well) and put the "com.apple.recovery.boot" folder to the root of your USB drive. Before making the switch to the macOS installer, you need to edit config.plist and edit line 1399 and add your MLB, line 1405 with your ROM, line 1413 with your SerialNumber and line 1415 with your UUID with ones from your own. Then go to "EFI\OC\Kexts\itlwm.kext\Contents\info.plist" and edit line 64 with your WiFi password and line 66 with your SSID, this will make sure you can connect to the internet on the macOS recovery install. After this reboot your machine and boot to your USB, press SPACE and then press enter to "NO NAME (dmg)" and let it boot. Partition your disks using Disk Utility and then install macOS normally. Note that you need to use the USB drive as your bootloader, it should work as a partition on your SSD as well (not tested that). Set up macOS and everything and then after this you will need to install https://github.com/OpenIntelWireless/HeliPort so you can manage your WiFi connections.


Congratulations, you have macOS on your MSI gaming laptop!
