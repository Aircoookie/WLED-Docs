---
title: Philips Hue
hide:
  # - navigation
  # - toc
---

WLED can sync to your Philips hue lights.

!!! info
    This feature allows your WLED light to set it color to that of one of your Hue lights. It does NOT enable individual control of your WLED light from the hue app.

To activate it, please go to Sync settings, fill in the IP of your hue bridge. Also you need to fill in the numeric ID of the hue light you want to sync to.  
Newer versions of the Hue app do not display light IDs in the "About" section of the app anymore, to find it, the app `Hue Config Viewer` is highly recommended.  
It is available on the [Play Store](https://play.google.com/store/apps/details?id=com.life4hue.hueconfigviewer) as well as the [App Store](https://apps.apple.com/app/id1145977453).  
After pairing the app to your Hue bridge, you can see the numeric IDs of all your Hue lights in the `Lights` menu.  

The poll interval specifies how often WLED asks the hue bridge for a light change. Lower values will mean a quicker response of WLED to hue light changes, but also decrease responsiveness and stability of WLED and potentially the hue bridge. It is recommended to set it to 1000-2000ms.

Due to the nature of the hue protocol, WLED can only sync itself to a native hue bulb. At this time, there is no way to add WLED to the hue bridge and control it individually as if it was a native light.

Please don't expect the same level of stability with this feature active, the ESP may reset itself because of the increased traffic it needs to handle.

With DiyHue you can emulate a hue bridge that will show all WLED strips as Hue Strip Plus which will work with Hue Sync in realtime.
