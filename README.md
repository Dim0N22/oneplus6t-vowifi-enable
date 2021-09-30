# oneplus6t-vowifi-enable
Enabling VoLTE + VoWiFi on OnePlus 6T for Freedom Mobile:

1. Install [Qualcomm USB Driver](https://github.com/Dim0N22/oneplus6t-vowifi-enable/blob/main/QUD.WIN.1.1%20Installer-10037.3%20Setup.exe?raw=true)
2. Enable usb debugging on the phone
3. `adb reboot ftm`
4. `adb shell`
5. `setprop sys.usb.config diag,serial_cdev,rmnet,adb`
6. Open `PDC` as Administrator
7. Select `Qualcomm HS-USB WWAN Adapter 9091`
8. Find `Oversea-Commercial_DS`, right click and deactivate for `Sub0`
9. Find `Commercial-TMO`, right click on it, `SetSelectedConfig` for `Sub0`
10. Select `Commercial-TMO` again and press `Activate`
11. Download and unpack [EfsTools](https://github.com/Dim0N22/oneplus6t-vowifi-enable/blob/main/EfsTools-0.10-modded-1.2-win32.zip?raw=true)
12. `cd E:\EfsTools-0.10-modded-1.2-win32\` (change to the actual directory)
13. `.\EfsTools.exe efsInfo`. It should not fail
14. `.\EfsTools.exe writeFile -i mcfg_autoselect_by_uim -o /nv/item_files/mcfg/mcfg_autoselect_by_uim`
15. `.\EfsTools.exe uploadDirectory -i mcfg_sw.mbn -o / -v`
16. `adb reboot`

Congratulations!
VoLTE and VoWiFi should be working.
