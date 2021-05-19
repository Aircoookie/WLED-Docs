WLED can sync to your Philips hue lights.

To activate it, please go to Sync settings, fill in the IP of your hue bridge. Also you need to fill in the numeric ID of the hue light you want to sync to, which you can find in the "About" section of the hue app.

The poll interval specifies how often WLED asks the hue bridge for a light change. Lower values will mean a quicker response of WLED to hue light changes, but also decrease responsiveness and stability of WLED and potentially the hue bridge.
It is recommended to set it to 1000-2000ms.

Due to the nature of the hue protocol, WLED can only sync itself to a native hue bulb. At this time, there is no way to add WLED to the hue bridge and control it individually as if it was a native light. 

Please don't expect the same level of stability with this feature active, the ESP may reset itself because of the increased traffic it needs to handle.