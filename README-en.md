# Hasee God-of-War Z7(m)-KP7(5)GZ macOS

[简体中文](README.md)

Clover configuration EFI folder for installing latest macOS Mojave (Hackintosh) on Hasee Z7-KP7GZ.

Note that this EFI should be theoretically work well on Z7m-KP7GZ or Z7m-KP5GZ, but it was only tested on Z7-KP7GZ. The macOS version I'm installing is 10.14.2/10.14.3. Approximately 98% of completion.

# Tutorial

If you don't now how to install macOS Mojave on a new Windows computer, there are many posts and videos that guide you through installing it, and you can find them on Tonymacx86/InsanelyMac/Youtube/Reddit, etc. Or, if you can read Chinese, you may refer to [this post](http://blog.daliansky.net/Lenovo-Xiaoxin-Air-13-macOS-Mojave-installation-tutorial.html).

If you have already installed macOS Mojave on your Z7(m)-KP7(5)GZ, but you have failed to make some devices work, please refer to my post [Installing macOS Mojave on Hasee God-of-War KP7GZ](https://kirainmoe.com/blog/post/guide-on-hasee-z7-kp7gz-hackintosh-macos-mojave/). (But it is in Chinese :D), or you may use my whole EFI folder directly.

# Screenshot

![screenshot](https://wx1.sinaimg.cn/large/9f1137b1gy1g0fim4a7ezj21770oan6a.jpg)

S/N is hidden.

# Info

| Component | Model |
|--|--|
| CPU | Intel Core(TM) i7-8750H | 
| GPU | Intel UHD630 / Nvidia GTX1060
| RAM | 8GB |
| Wireless | Intel AC9462 |
| Ethernet | Realtek RTL8168H |
| Audio | Realtek ALC269vc |

# What's working

- Turbo boost and CPU frequency stage
- Intel UHD630 Graphics
- Brightness control and Brightness key (You may plug in a USB keyboard to configurate it)
- I2C HID touchpad (Battery must work normally before you set gestures)
- Ethernet
- Sound (ALC269vc, using AppleALC, injecting layout-id 88. Speakers, Headphone Jack and Microphone all work)
- Battery status (Not a Clover Hotpatch, please apply the dsdt patch in this repository using MaciASL by yourself)
- USB (no port count limit)
- Sleep (USB _PRW patch is required)
- etc.

# What's partial working

- Bluetooth (It is available by random)

# What's not working

- DGPU (GTX1060 is not available)
- WLAN (Intel Wireless AC9462 is not available)

# Tips

Q: How to patch battery and USB _PRW?

After you install the system, press F4 to extract DSDT from your BIOS when you are in Clover Bootloader. Boot into the macOS and open MaciASL, find the DSDT you extract in /EFI/CLOVER/ACPI/origin, click 'Patch', copy the content of [dsdt-patch.txt](dsdt-patch.txt) and paste it into 'Patch' window, then click 'Apply'. You should see 'XX Patches, XX Applied, 0 Rejected' while patching. Compile and save your patched DSDT to /EFI/CLOVER/ACPI/patched. Then check if you have ACPIBatteryManager.kext installed, reboot your system and you should see your battery status and sleep works.

Warning: Do NOT change SMBIOS model randomly, or USB may not working anymore. If you do have the requirement of modifying SMBIOS model, you should use Hackinool to make a custom USBPorts.kext driver.

# Detail screenshot

USB  
![usb](https://ws2.sinaimg.cn/large/9f1137b1gy1g0fimkywrfj20gv0bp3zn.jpg)

Ethernet  
![network](https://wx3.sinaimg.cn/large/9f1137b1gy1g0finlomxaj20gv0bpaap.jpg)

IGPU  
![uhd630](https://ws1.sinaimg.cn/large/9f1137b1gy1g0fipr3magj20gv0bpjs9.jpg)

Battery(S/N is hidden)  
![battery](https://wx3.sinaimg.cn/large/9f1137b1gy1g0fiq7gu9ej20gv0bpwfl.jpg)

Bluetooth(MAC address is hidden)  
![bluetooth](https://ws4.sinaimg.cn/large/9f1137b1gy1g0fiqm7c70j20gv0bpdh4.jpg)

Audio  
![sound](https://wx2.sinaimg.cn/large/9f1137b1gy1g0fir5cqzmj20gv0bp751.jpg)  
![sound-2](https://ws3.sinaimg.cn/large/9f1137b1gy1g0firigeyhj20f00b7t95.jpg)  

Brightness, HiDPI  
![hidpi](https://wx3.sinaimg.cn/large/9f1137b1gy1g0firynbysj21770oa477.jpg)  
![brightness-key](https://ws2.sinaimg.cn/large/9f1137b1gy1g0fisj7r1kj206j0660sx.jpg)  

Turbo boost, LPC  
![hwmonitor](https://wx3.sinaimg.cn/large/9f1137b1gy1g0fisxsg8jj206m0c3wf8.jpg)  
![lpc](https://wx2.sinaimg.cn/large/9f1137b1gy1g0fitafzljj20f00a1gm4.jpg)  

Touchpad gesture  
![gesture](https://wx4.sinaimg.cn/large/9f1137b1gy1g0fitjrcoqj20f00bk75e.jpg)  

Screenfetch  
![screenfetch](https://wx1.sinaimg.cn/large/9f1137b1gy1g0fitwobg3j20d5087my0.jpg)

# Contribute

Feel free to contribute.