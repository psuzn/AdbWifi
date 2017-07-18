# AdbWifi
 Unless you are using CM or lineage based rom with support for adb over wifi, you have to 
connect  your device via bluethooth and run following command to  enable adb over WiFi.I have written a small bash script for Android to enable adb (android debugging bridge) over your local network like WiFi.

```
adb tcpip [PORT]
```
eg.
```
adb tcpip 5555.
```
This script can save your some time and give freedom of wireless.


> **Note:**
> **To use this script you need**
>- Your device must be rooted with busybox installed.
>- adb via use for once.
>Or,
>- Pre-installed terminal emulator or any root explorer app to write in /system/xbin directory
>- Your both device must be in same network

**Process to install:**

The overall process is to place AdbWifi file in /system/xbin folder and make it executable.You can do it via any way you like.


I assume you have downloaded the file in your pc (Windows|OSX|Linux any) and have adb installed. Then,
- Open terminal in linux or mac or if you are in windows open CMD.
- Navigate to directory containing AdbWifi file (script not the folder).
- Connect your android device via usb and enable usb debugging.
- Type following command in terminal or cmd (in windows)
```
adb push AdbWifi /sdcard/AdbWifi
adb shell
su 
mv /sdcard/AdbWifi /system/xbin/AdbWifi
chmod +x /system/xbin/AdbWifi
exit
exit
```
Now disconnect your device and open terminal emulator in it and type:
```
$ su
```
Then give the superuser permission for terminal,then you'll see $ changes to #
```
$ su
#
```
after that
```
AdbWifi
```
then you'll see menu like 
```
GT-I9100:/ # AdbWifi                                                          
1) Start adb over wifi on default port 5555
2) provide the port
3) Stop adb over wifi
4) Do nothing
#? 
```
type 1 and you'll see something like:
```
GT-I9100:/ # AdbWifi                                                              
1) Start adb over wifi on default port 5555
2) provide the port
3) Stop adb over wifi
4) Do nothing
#? 1
adb over WiFi has been started
run 'adb connect 192.168.1.5 ' to connect adb via WiFi
and run 'adb devices' to check your device
```
In your terminal or CMD type following:
```
$ adb connect 192.168.1.5
connected to 192.168.1.59:5555
$ adb devices
List of devices attached
192.168.1.59:5555	device
```
Yepee,Now your device is connected via Wifi,next time open terminal emulator in your android and run AdbWifi command and do as above. If something went wrong just change the port.