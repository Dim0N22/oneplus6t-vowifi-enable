# oneplus6t-vowifi-enable
1. Install [Qualcomm USB Driver](https://github.com/Dim0N22/oneplus6t-vowifi-enable/blob/main/QUD.WIN.1.1%20Installer-10037.3%20Setup.exe?raw=true);
2. Enable usb debugging on the phone;
3. `adb reboot ftm`;
4. `adb shell`;
5. `setprop sys.usb.config diag,serial_cdev,rmnet,adb`;
6. Open `PDC` as Administrator;
7. Select `Qualcomm HS-USB WWAN Adapter 9091`;
8. 
