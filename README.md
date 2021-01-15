How to install Xposed on Memu 7.1.1
=========

### Requirements

- Enable Root
- Enable «Memu Downloads» in shared folders settings
- Xposed APK — forum.xda-developers.com/showthread.php?t=3034811
- SuperSU 2.79 APK (Don't use SuperSU 2.82!) — mediafire.com/file/93061a18cw0280a/SuperSU_v2.79.apk/file

### Installation

1. Install both SuperSU and Xposed - just drag & drop apks to the Memu window.

2. Install SU Binaries (click «Normal» button) and reboot in order for the Xposed installer to work.

*Allow superuser permission when asked*

3. Unzip already patched xposed zip to «Downloads/Memu Download» folder, then run INSTALL XPOSED.bat

Thats all. Now reboot.

#### If you want to do patch process manually, then follow another instructions instead of 3rd step:

3. Download xposed at dl-xda.xposed.info/framework. Then select correct sdk version for your Android version, select x86 and grab latest xposed version. For Memu 7.1.1, choose xposed-v89-sdk25-x86.zip.

List of SDK versions

- Android11 — SDK 30
- Android10 — SDK 29
- Pie 9.0 — SDK 28
- Oreo 8.1 — SDK 27
- Oreo 8.0 — SDK 26
- Nougat 7.1 — SDK 25
- Nougat 7.0 — SDK 24
- Marshmallow 6.0 — SDK 23
- Lollipop 5.1 — SDK 22
- Lollipop 5.0 — SDK 21




4. Save the downloaded file in your shared folder «Downloads/Memu Download» and unzip the xposed

5. Goto the directory where you unzipped the xposed and open «/META-INF/com/google/android» and in there is 4 files select all those files and copy them back to the top «Memu Download/xposed» folder

6. Edit the Flash-Script.sh file and on line 166 (or the last exit 1 command in the file) add # before it so it reads like that:

```
163. if [ -z $XVALID ]; then
164.   echo "! Please download the correct package"
165.   echo "! for your platform/ROM!"
166.   # exit 1 <-- «#» here
167. fi
```

7. Open Command Prompt (Win+R, «cmd», Enter) and type the following:

```
adb connect localhost:21503
adb shell
cd sdcard/Download/xposed
sh flash-script.sh
```

8. Reboot Emulator

If your emulator gets stuck, you would have to reinstall emulator using installer and start over again. You do NOT need to uninstall to wipe your data.

9. Now run Xposed app. If it says that Xposed is not active reboot emulator again, and it should say xposed is active!
