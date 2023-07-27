# FlashForge Timelapse
I want to create a timelapse recording of my 3D prints, but the camera on my FlashForge Adventurer 3 Pro is only accessible through the local cloud connection. I plan on using openCV to capture a frame every so often and compile them into a timelapse-video.

My original solution was to use OBS to record a cropped video at a low framerate, then speeding it up to make a shorter, 60 fps video. A similar thing can be done by taking a normal video and compressing/sampling frames from it; however the both of these solutions present the issue of a large amount of storage being taken up by the raw footage. In addition, because the camera is mounted on the side of the case - not on the print bed - a timelapse video would be very jittery as the print bed moves along the Z-axis.

The solution contained in this program will be to use opencv to detect whenever the printer crosses a certain axis and snap a picture, this will remove the jitter/wobble from the print by making sure that the bed is in the same position every time a picture is taken.

- Maybe there can be some gcode parsing/analysis for better timing
- Place a colored sticker on the plate to indicate the position of the print in openCV
- This will likely have time stretching, where there will be varying time-gaps in the video 