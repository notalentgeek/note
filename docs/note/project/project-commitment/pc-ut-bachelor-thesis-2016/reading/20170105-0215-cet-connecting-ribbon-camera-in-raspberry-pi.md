* These are some tutorial that I use to connect PiCam into my Raspberry PI.
    * [http://www.pyimagesearch.com/2015/03/30/accessing-the-raspberry-pi-camera-with-opencv-and-python/](http://www.pyimagesearch.com/2015/03/30/accessing-the-raspberry-pi-camera-with-opencv-and-python/)
    * [http://www.pyimagesearch.com/2016/08/29/common-errors-using-the-raspberry-pi-camera-module/](http://www.pyimagesearch.com/2016/08/29/common-errors-using-the-raspberry-pi-camera-module/)
    * [http://www.techradar.com/news/computing-components/peripherals/how-to-install-the-raspberry-pi-camera-module-1172034](http://www.techradar.com/news/computing-components/peripherals/how-to-install-the-raspberry-pi-camera-module-1172034)
    * [https://thepihut.com/blogs/raspberry-pi-tutorials/16021420-how-to-install-use-the-raspberry-pi-camera](https://thepihut.com/blogs/raspberry-pi-tutorials/16021420-how-to-install-use-the-raspberry-pi-camera)
    * [https://www.raspberrypi.org/documentation/configuration/camera.md](https://www.raspberrypi.org/documentation/configuration/camera.md)
    * [https://www.raspberrypi.org/learning/getting-started-with-picamera/worksheet/](https://www.raspberrypi.org/learning/getting-started-with-picamera/worksheet/)
    * [https://www.reddit.com/r/raspberry_pi/comments/5lylr9/how_can_i_make_usb_audio_adapter_work_with/](https://www.reddit.com/r/raspberry_pi/comments/5lylr9/how_can_i_make_usb_audio_adapter_work_with/)
* The best tutorial is this one, [http://www.pyimagesearch.com/2015/03/30/accessing-the-raspberry-pi-camera-with-opencv-and-python/](http://www.pyimagesearch.com/2015/03/30/accessing-the-raspberry-pi-camera-with-opencv-and-python/).
* To sum up!
* Attach the ribbon camera into Raspberry PI.
* Do these.

```markdown
sudo raspi-config
```

* There you need to choose to "Expand Root" or "Expand Size" (I forget the name of the entry menu, but it is around those words).
* Also enable camera. This can be also done with "Start Menu", then go to "Preferences".
* After this accessing the camera is different with using USB camera there is a specific library to accessing camera (refer to the best tutorial several points above).