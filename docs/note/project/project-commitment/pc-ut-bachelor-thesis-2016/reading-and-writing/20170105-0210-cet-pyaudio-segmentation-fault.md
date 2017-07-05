* PyAudio usually have `Segmentation fault` in Raspberry PI in case you wrongly put the `input_device_index` and if you start the PyAudio application without `sudo`.
* So run this scripts.

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

* After this run the Python script with `sudo`.
* There should be no more error.