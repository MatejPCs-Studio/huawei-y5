# How to install DotOS
(Wifi + BL working, sim probably too (not tested))


## Step 1:
Boot to fastboot by doing Vol Up + PWR and select Fastboot Mode.
Flash vendor, boot and cust from the images directory by using:
```
fastboot flash <partission name> <image>
```

Then flash twrp from the image directory: 
```
fastboot flash erecovery twrp.img
```
Delete userdata so you dont get stuck on the TWRP load screen:
```
fastboot erase userdata
```

## Step 2:
Now, hold PWR until the screen goes black and IMMIDIETLY press PWR + Vol Up again.
Then select Erecovery Mode and boot.
Your device will now boot to "erecovery" which we replaced with TWRP.
We need to repack the kernel and flash DM-Verity patch.
```
adb push repack_twrp_in_erecovery.zip Disable_Dm-Verity_ForceEncrypt_11.02.2020.zip /sdcard
```
Go into install and install repack zip then DM-Verity zip.
Disconnect the usb cable, go back, Reboot and Power Off.

## Step 3:
Now press PWR + Vol Up and select Erecovery Mode again.
When TWRP loads, go to settings and select "use rm -rf instead of formatting" and then format all partisions except the SD Card and Vendor.
Now we have the hardest part done but do not reboot.

Go to Advanced and ADB Sideload then slide to the right.
Run this command and that will install the DotOS rom with all patches!
```
adb sideload dotOS-flash.zip
```

And we are done! After that flashes, click Reboot System or go to the main menu and click Reboot -> System!

## Bugs
You tell me!

