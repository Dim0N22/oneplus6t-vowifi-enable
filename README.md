# oneplus6t-vowifi-enable
Enabling VoLTE + VoWiFi on OnePlus 6T for Freedom Mobile:

1. Install [Qualcomm USB Driver](https://github.com/Dim0N22/oneplus6t-vowifi-enable/blob/main/QUD.WIN.1.1%20Installer-10037.3%20Setup.exe?raw=true)
2. Install [QPST](https://github.com/Dim0N22/oneplus6t-vowifi-enable/blob/main/QPST_2.7.474.7z?raw=true)
5. Enable usb debugging on the phone
6. `adb reboot ftm`
7. `adb shell`
8. `setprop sys.usb.config diag,serial_cdev,rmnet,adb`
9. Open `PDC` as Administrator
10. Select `Qualcomm HS-USB WWAN Adapter 9091`
11. Find `Oversea-Commercial_DS`, right click and deactivate for `Sub0`
12. Find `Commercial-TMO`, right click on it, `SetSelectedConfig` for `Sub0`
13. Select `Commercial-TMO` again and press `Activate`
14. Download and unpack [EfsTools](https://github.com/Dim0N22/oneplus6t-vowifi-enable/blob/main/EfsTools-0.10-modded-1.2-win32.zip?raw=true)
15. `cd E:\EfsTools-0.10-modded-1.2-win32\` (change to the actual directory)
16. `.\EfsTools.exe efsInfo`. It should not fail
17. `.\EfsTools.exe writeFile -i mcfg_autoselect_by_uim -o /nv/item_files/mcfg/mcfg_autoselect_by_uim`
18. `.\EfsTools.exe uploadDirectory -i mcfg_sw.mbn -o / -v`
19. `adb reboot`

Congratulations!
VoLTE and VoWiFi should be working.
