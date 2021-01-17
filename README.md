How to install Xposed on Memu 7.3.2
=========

For MEmu 7.3.2 by default it comes with x86 Android 7.1.2 which is SDK 25.

### Requirements

- Enable Root
- Enable **Memu Downloads** in shared folders settings
- Xposed zip - https://dl-xda.xposed.info/framework/sdk25/x86/xposed-v89-sdk25-x86.zip
  - **Note:-** if you want to install Xposed in older or newer Android versions other than 7.1.2, then download Xposed zip from https://dl-xda.xposed.info/framework according to SDK version of Android running in MEmu.
- Xposed APK — https://forum.xda-developers.com/attachments/xposedinstaller_3-1-5-apk.4393082

### Installation

- Install Xposed app - just drag & drop apk to the MEmu window.
- Place downloaded xposed-v89-sdk25-x86.zip in `/data/local/tmp` folder. Extract only `META-INF/com/google/android/update-binary` to `/data/local/tmp`.
- Run below commands either in `adb shell` or in Terminal Emulator app with root option enabled in MEmu.
  ```
  su
  cd /data/local/tmp
  chmod 777 update-binary
  NO_UIPRINT=1 ./update-binary 2 1 xposed-v89-sdk25-x86.zip
  rm update-binary xposed-v89-sdk25-x86.zip
  ```
- Restart MEmu

Enjoy!
