* Setting up USB microphone in Raspberry PI is not that easy.
* The most common errors are these.
    * `Errr -9996`, means that you have not specified `input_device_index` in PyAudio stream.
    * `Segmentation fault`, means you wrongly put `input_device_index` or did not start the application with `sudo`.
    * No audio stream input because I was using 2 in 1 microphone and earphone that I usually use to listen to music and answering call. This will not work, use a dedicated microphone instead.
* Here are a lot of links about how I was able to solve a problem of getting audio input into PyAudio application.
    * [http://raspberrypi.stackexchange.com/questions/19705/usb-card-as-my-default-audio-device](http://raspberrypi.stackexchange.com/questions/19705/usb-card-as-my-default-audio-device)
    * [http://raspberrypi.stackexchange.com/questions/28158/audio-and-microphone-configuration-of-usb-sound-card-on-r-pi](http://raspberrypi.stackexchange.com/questions/28158/audio-and-microphone-configuration-of-usb-sound-card-on-r-pi)
    * [http://raspberrypi.stackexchange.com/questions/37177/best-way-to-setup-usb-mic-as-system-default-on-raspbian-jessie](http://raspberrypi.stackexchange.com/questions/37177/best-way-to-setup-usb-mic-as-system-default-on-raspbian-jessie)
    * [http://raspberrypi.stackexchange.com/questions/39187/alsa-base-conf-file-missing](http://raspberrypi.stackexchange.com/questions/39187/alsa-base-conf-file-missing)
    * [http://raspberrypi.stackexchange.com/questions/46799/usb-microphone-raspberry-pi](http://raspberrypi.stackexchange.com/questions/46799/usb-microphone-raspberry-pi)
    * [http://raspberrypi.stackexchange.com/questions/59852/pyaudio-does-not-detect-my-microphone-connected-via-usb-audio-adapter/](http://raspberrypi.stackexchange.com/questions/59852/pyaudio-does-not-detect-my-microphone-connected-via-usb-audio-adapter/)
    * [http://raspberrypi.stackexchange.com/questions/9951/pyaudio-recording-sound-on-pi-getting-errors](http://raspberrypi.stackexchange.com/questions/9951/pyaudio-recording-sound-on-pi-getting-errors)
    * [http://raspberrypirecipes.blogspot.nl/2014/02/raspberry-pi-using-pyaudio-external.html](http://raspberrypirecipes.blogspot.nl/2014/02/raspberry-pi-using-pyaudio-external.html)
    * [http://scruss.com/blog/2012/11/20/raspberry-pi-as-a-usb-audio-capture-device/](http://scruss.com/blog/2012/11/20/raspberry-pi-as-a-usb-audio-capture-device/)
    * [http://stackoverflow.com/questions/38470321/ioerror-errno-invalid-output-device-no-default-output-device-9996](http://stackoverflow.com/questions/38470321/ioerror-errno-invalid-output-device-no-default-output-device-9996)
    * [http://www.linuxcircle.com/2013/05/08/raspberry-pi-microphone-setup-with-usb-sound-card/](http://www.linuxcircle.com/2013/05/08/raspberry-pi-microphone-setup-with-usb-sound-card/)
    * [https://computers.tutsplus.com/articles/using-a-usb-audio-device-with-a-raspberry-pi--mac-55876](https://computers.tutsplus.com/articles/using-a-usb-audio-device-with-a-raspberry-pi--mac-55876)
    * [https://learn.adafruit.com/usb-audio-cards-with-a-raspberry-pi/instructions](https://learn.adafruit.com/usb-audio-cards-with-a-raspberry-pi/instructions)
    * [https://linuxconfig.org/how-to-test-microphone-with-audio-linux-sound-architecture-alsa](https://linuxconfig.org/how-to-test-microphone-with-audio-linux-sound-architecture-alsa)
* From those links the most useful tutorial is, [https://learn.adafruit.com/usb-audio-cards-with-a-raspberry-pi/instructions](https://learn.adafruit.com/usb-audio-cards-with-a-raspberry-pi/instructions).
* And then I had a good discussion in Raspberry PI StackExchange that led me to solve the problem, [http://raspberrypi.stackexchange.com/questions/59852/pyaudio-does-not-detect-my-microphone-connected-via-usb-audio-adapter/](http://raspberrypi.stackexchange.com/questions/59852/pyaudio-does-not-detect-my-microphone-connected-via-usb-audio-adapter/).
* Here is my compiled guide on how to get audio input from the USB audio adapter into PyAudio application.
* Use Raspbian Jessie, the latest version of Raspbian per January 2017.
* Do not use 2 in 1 microphone + earphone. This thing will not record anything into your Raspberry PI!
* Instead, use a dedicated microphone.
* `sudo nano /usr/share/alsa/alsa.conf` and then change these lines.

```markdown
defaults.ctl.card 1
defaults.pcm.card 1
```

* `~/.asoundrc` (without `sudo`) and `/etc/asound.conf` (with `sudo`) then change both into these (both will have same codes).

```markdown
pcm.!default {
    type hw card 1
}
ctl.!default {
    type hw card 1
}
```

* Make sure both microphone and speaker are working.
* To test microphone do this, `arecord --device=hw:1,0 --format S16_LE --rate 44100 -c1 test.wav`. Then press CTRL + C to stop recording.
* To test what you have captures in microphone use this, `aplay --device=plughw:1,0 test.wav`.
* To test speaker do this, `speaker-test -c2`. There will be some white noises.
* At this point everything should be set.
* Run this script to know the index of the USB audio driver that is detected in PyAudio.

```markdown
import pyaudio
p = pyaudio.PyAudio()
for i in range(p.get_device_count()):
    dev = p.get_device_info_by_index(i)
    print((i,dev['name'],dev['maxInputChannels']))
```

* Note the index on the of the USB audio driver you want to use.
* And then use in the arguments when you are initiating PyAudio object.
* Change the `input_device_index` into the index you found from the previous script.

```markdown
    format = self.FORMAT,
    channels = self.CHANNELS,
    rate = self.SAMPLE_RATE,
    frames_per_buffer = self.PERIOD_SIZE_IN_FRAME,
    input_device_index = self.INPUT_DEVICE_INDEX,
    input = True)
```

* Start the PyAudio application with `sudo`. For example, `sudo python -B my_pyaudio_application.py`.
* If there is an `Exception overflow` error, change the streaming method from the microphone by using this, `data = stream.read(chunk, exception_on_overflow = Fals`.
* At this point I have no problem anymore. I can easily capture and stream sound from USB microphone into my PyAudio application.