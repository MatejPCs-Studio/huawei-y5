# How to unlock the Huawei Y5 (DRA-L21)

## IMPORTANT
Your warranty is now void. I am not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed.
Take a full backup of the device before doing any modifications!

## Unlocking
First start ```mtk da seccfg unlock``` on your computer then get your device to brom mode:
Hold Vol Up + Vol Down and plug in the usb cable.

Your device will be partially unlocked now you need to run ```mtk da vbmeta 3```.
And flash kaeru by doing ```mtk w lk dura-kaeru.bin```.

Your device is now unlocked!

## Testing
To see if you succeeded in unlocking run ```fastboot oem kaeru-version``` while your phone is in fastboot.
It should display a big "kaeru" logo.
To get to fastboot use PWR + Vol Up and select Fastboot Mode.

## Custom Rom
[click here after unlocking!](https://github.com/MatejPCs-Studio/huawei-y5/blob/main/docs/DOTOS.md)

## Credits
[@r0rt1z2](https://github.com/R0rt1z2) - for kaeru and mtkclient fork

[@bkerler](https://github.com/bkerler) - for original mtkclient




