---
title: Developing for Oculus Quest in Unity v2019.1
author: Luis Quintero
date: 2020-07-20 15:00:00 +0100
categories: [Blogging, XR]
tags: [writing]
---

# ADB Connection with Oculus Quest

Location of ADB installed with Unity: 

`C:\Program Files\Unity\Hub\Editor\2019.2.12f1\Editor\Data\PlaybackEngines\AndroidPlayer\SDK\platform-tools`

Manuals for ADB Debugging:
- [ADB manual for sending commands Wirelessly](https://developer.android.com/studio/command-line/adb#wireless)
- [Connect Android to Unity Debugger](https://docs.unity3d.com/560/Documentation/Manual/AttachingMonoDevelopDebuggerToAnAndroidDevice.html)

## Screen casting

[Cast to PC through Android SDK Platform-Tools](https://developer.android.com/studio/releases/platform-tools)

```
LAST DATE 
Device id: 		1PASH9B9949386
Device last IP:	10.200.26.92
```

To get the IP address of the Android phone/Quest

```
>> .\adb.exe shell ip addr show wlan0`
OR
>> adb shell
Monterey:/$ ip -f inet addr show wlan0
7: wlan0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 3000
    inet 10.200.26.92/18 brd 10.200.63.255 scope global wlan0
       valid_lft forever preferred_lft forever
```

To connect via WiFi
```
>> .\adb.exe devices
>> .\adb.exe tcpip 5555
[disconnect the device from the USB port]
>> .\adb.exe connect 10.200.26.92:5555
```

The following file can be downloaded from https://github.com/Genymobile/scrcpy

`>> .\scrcpy.exe -c 1440:1600:0:0 -m 1600 -b 8M`


## Install/Uninstall APK

`adb install -r <app name.apk>`: The -r option allows you to re-install or update an existing app on your device

`adb install -s <app name.apk>`: The -s option lets you install app to SD card if the app supports move to SD card feature

`adb uninstall <app name.apk>`


# Setup in Unity 2019


