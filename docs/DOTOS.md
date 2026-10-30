# How to install DotOS
(Wifi + BL working, SIM and DATA work. In Czechia only EDGE connection)

## IMPORTANT
```
Your warranty is now void. I am not responsible for bricked devices, dead SD cards,
thermonuclear war, or you getting fired because the alarm app failed.
YOU are choosing to make thesemodifications,and if you point the
finger at me for messing up your device, I will laugh at you. 
Take a full backup of the device before doing any modifications!
```

## Step 1:
If your device is bricked, flash the backup and reboot to system.
Then go back to BROM and flash [rgpt.bin](https://github.com/MatejPCs-Studio/huawei-y5/releases/download/guide-v1/rgpt.bin) to gpt by using ```mtk w gpt rgpt.bin```
If you skip this step you wont be able to flash system and vendor.

## Step 2:
This step is VERY important.
Stay in BROM Mode and open mtkgui, **erase userdata** and flash the full stock backup **WITHOUT userdata**. If you flash the userdata image the emmc wont enough space on it as we 
took 150MB from it and gave it to the vendor partission.
If you would boot without erasing userdata in this step it will fall into erecovery and it wont even be able to do a data format.
Now after you write the full backup **erase** userdata again for good messure.

_you can boot to system, it will take around 8 minutes_

## Step 3:
Boot to fastboot by doing Vol Up + PWR and select Fastboot Mode.
Flash vendor, boot and cust from the images directory by using:
```
fastboot flash <partission name> <image>
```

Then flash twrp from the image directory: 
```
fastboot flash erecovery twrp.img
```
Erase userdata so you dont get stuck on the TWRP load screen: 
```
fastboot erase userdata
```

## Step 4:
Now, hold PWR until the screen goes black and IMMEDIATELY press PWR + Vol Up again.
Then select Erecovery Mode and boot.
Your device will now boot to "erecovery" which we replaced with TWRP.
We need to repack the kernel and flash DM-Verity patch.
```
adb push repack_twrp_in_erecovery.zip Disable_Dm-Verity_ForceEncrypt_11.02.2020.zip /sdcard
```
Go into install and install repack zip then DM-Verity zip.
Disconnect the usb cable, go back, Reboot and Power Off.

## Step 5:
Now press PWR + Vol Up and select Erecovery Mode again.
When TWRP loads, go to settings and select "use rm -rf instead of formatting" and then format all partisions except the SD Card and Vendor.
Now we have the hardest part done but do not reboot.

Go to Advanced and ADB Sideload then slide to the right.
Run this command and that will install the [DotOS rom](https://github.com/MatejPCs-Studio/huawei-y5/releases/download/roms/dotos-3.zip) with all patches!
```
adb sideload dotos-3.zip
```

And we are done! After that flashes, click Reboot System or go to the main menu and click Reboot -> System!

## Credits
Lots and lots of people on the [4PDA forum](https://4pda.to/forum/index.php?showtopic=982322) for this device!
## Bug
You tell me!

