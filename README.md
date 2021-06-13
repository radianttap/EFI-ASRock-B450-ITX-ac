OpenCore ver 0.7.0 · Bug Sur 11.4

# ASRock B450 ITX/ac + Ryzen 5 3600 + RX 570 XT → iMacPro1,1

Current hardware:

- [ASRock Fatal1ty B450 Gaming-ITX/ac](https://www.asrock.com/mb/AMD/Fatal1ty%20B450%20Gaming-ITXac/) motherboard
- AMD [Ryzen 5 3600](https://www.amd.com/en/products/cpu/amd-ryzen-5-3600) CPU
- Acetek 645LT AIO
- Noctua [NF-A9x14](https://noctua.at/en/products/fan/nf-a9x14-pwm) fan, placed on top the AIO
- Sapphire [Nitro+ RX 570 XT 8GB](https://www.sapphiretech.com/en/consumer/nitro-rx-570-8g-g5-oc) graphics card
- Corsair [Vengeance LPX](https://www.corsair.com/ww/en/Categories/Products/Memory/VENGEANCE-LPX/p/CMK16GX4M2B3200C16) 16 GB (2 x 8 GB) DDR4 3200MHz CL16
- Corsair [SF600 Platinum](https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020182-NA) SFX PSU
- ADATA [XPG 8200 Pro](https://www.xpg.com/us/feature/583/) 1TB NVMe SSD
- Samsung [860 EVO](https://www.samsung.com/us/computing/memory-storage/solid-state-drives/ssd-860-evo-2-5--sata-iii-500gb-mz-76e500b-am/) 500 GB 2.5in SSD
- Dan [A4 SFX](https://dan-cases.com/dana4.php) v4.1 SFF case
- [Fenvi WiFi/Bt card](https://www.aliexpress.com/item/Dual-band-Wireless-Hackintosh-BCM94352Z-WIFI-Card-Broadcom-bcm94352-M-2-Bluetooth-4-0-Network-NGFF/32464748097.html) with BCM94352Z chip

### BIOS

Version 4.10

- Fast Boot: `Disabled`
- CSM: `Disabled`
- Above 4G Decoding: `Enabled`
- XMP Profile activated.
- FCLK set to 1600MHz, to be equal to MCLK.

## Usage

1. [Update `PlatformInfo/Generic` stuff](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial) with your own, inside `config.plist`
2. Use your Ethernet’s MAC address for `ROM` value, as explained in the Dortania guide. Don’t leave it as all 0s.
3. Update value of `brcmfx-country` argument in `NVRAM/7C436110-AB2A-4BBB-A880-FE41995C9F82/boot-args` with your country code. Should be identical or compatible with what your WiFi router is broadcasting. (Remove the parameter if you don’t know what I’m talking about here.)
4. Turn off Power Nap in Energy Saver.

Important: Add `-v` boot-args parameter to get verbose boot process, it greatly simplifies troubleshooting.

### What’s working

Pretty much everything.

- NVMe SSD recognised properly.
- WiFi, Bluetooth, Ethernet
- All USB ports properly mapped. I disconnected front USB-C as I did not need it.
- Radeon GPU, natively supported.
- All media services (Plex, Netflix in Safari, iTunes, Apple TV+ etc). All are fully hardware-accelerated.
- 4K HDMI with HDR, Dolby.
- Handoff, iMessage, iCloud, Keychain, Xcode etc.
- System Integrity Protection (SIP) fully enabled.

### What’s not working

- Sidecar
- Sleep, Wake
- Watch unlock

## Notes

Use at your own risk. 

- All `.efi` drivers and `.kext` are `-DEBUG` builds from the respective packages. 
- OpenCanopy (GUI boot menu) is up and running.
- I don’t boot Windows 10 using OC, thus I can’t guarantee it will work. I have Win 10 installed on separate SSD and switch using Boot Menu.

**Don’t ask me for help.** Sorry but this stuff is finicky and infuriatingly detailed that every little mis-step can be a proper headache. This is why [Dortania](https://dortania.github.io) advises to not reuse anyone’s EFI.  

Ask [on reddit](https://www.reddit.com/r/hackintosh/) and the [discord server](https://discord.gg/Wxam8aH).

Good luck.


## Give back

If you found this code useful, please consider [buying me a coffee](https://www.buymeacoffee.com/radianttap) or two. ☕️😋
