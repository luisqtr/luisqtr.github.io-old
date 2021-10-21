---
title: Developing for Oculus Quest
author: Luis Quintero
date: 2020-07-20 15:00:00 +0100
categories: [Blogging, VR]
# image: /assets/img/portfolio/PortalSense.jpg
tags: [VR]
---

There are many differences in rendering for desktop VR and mobile standalone VR. As shown in the comparison video of a video game ([source](https://www.youtube.com/watch?v=-DLSqfftsnE)):

![VRComparison]({{site.baseurl}}/assets/posts/vr/Onward_Quest_vs_PC_VR_Graphics_Comparison.gif)


# ADB Connection with Oculus Quest

Location of ADB installed with Unity: 

`C:\Program Files\Unity\Hub\Editor\2019.X.Xf1\Editor\Data\PlaybackEngines\AndroidPlayer\SDK\platform-tools`

Manuals for ADB Debugging:
- [ADB manual for sending commands Wirelessly](https://developer.android.com/studio/command-line/adb#wireless)
- [Connect Android to Unity Debugger](https://docs.unity3d.com/560/Documentation/Manual/AttachingMonoDevelopDebuggerToAnAndroidDevice.html)
- [Download Android SDK Platform-Tools](https://developer.android.com/studio/releases/platform-tools)

## Screen casting

Requires [scrcpy] to cast from device to PC, it can be downloaded from <https://github.com/Genymobile/scrcpy>. **It includes ADB**.

**Screen casting connected to PC**

```
>> adb devices
>> scrcpy --crop 1200:800:180:320 -m 1600 -b 25M
```

**Screen casting via WiFi**

`>> .\scrcpy.exe -c 1440:1600:0:0 -m 1600 -b 8M`

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


## Install/Uninstall APK

`adb install -r <app name.apk>`: The -r option allows you to re-install or update an existing app on your device

`adb install -s <app name.apk>`: The -s option lets you install app to SD card if the app supports move to SD card feature

`adb uninstall <app name.apk>`


# Setup in Unity 2019.4.1

Install the *XR Management* from the *Package Manager*

Documentation for XR Interaction Toolkit [here](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@0.9/manual/index.html)

# Performance Considerations for Oculus Quest

## Rendering

(*Source: [OC6](https://youtu.be/PUK2-GzXuso?t=2130)*)

Regarding the use of Universal Rendering Pipeline for Oculus Quest:
- Bake shadows in the lightmap, it is extremely costly for the tiled renderer of mobile platforms to render and resolve shadows per frame
- Final Blit Pass. Avoid it.

Oculus Standalone Optimal Usage of the URP:
- Limit the number of resolves to one per tile.
- Keep in mind that intermediate render textures in standalone devices is that it breaks Fixed Foveated Rendering, which saves about 20% GPU performance per frame. Any rendering to intermediate texture will not have the FFR savings that we are looking for. E.g. Blit uses intermediate texture, that is why it is not useful.



