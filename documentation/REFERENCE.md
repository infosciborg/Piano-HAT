#Piano HAT Function Reference

This library lets you use Piano HAT in Python to control whatever project you might assemble.

See `buttons.py` for an example of how to handle buttons. The library has 4 different events you can bind to:

* `on_note` - triggers when a piano key is touched
* `on_octave_up` - triggers when the Octave Up key is touched
* `on_octave_down` - triggers when the Octave Down key is touched
* `on_instrument` - triggeres when the Instrument key is touched

See `leds.py` for an example of how to take command of the Piano HAT LEDs. You can turn all of the LEDs on and off at will, useful for creating a visual metronome, prompting a user which key to press and more.

* `set_led(x, True/False)` - lets you set a particular LED to on ( True ) or off ( False ).
* `auto_leds(False)` - stops Piano HAT from automatically lighting the LEDs when a key is touched

Piano HAT will also work with anything that supports MIDI input, thanks to Python MIDI and the `midi-piano.py` example.

##Installing Python MIDI

This is a little tricky, but if you follow these steps you should get it installed in no time:

First you'll need some dependencies, install them with: `sudo apt-get install python-dev libasound2-dev swig`

Next, you need to clone the GitHub repo: `git clone https://github.com/vishnubob/python-midi`

And install it: `cd python-midi && sudo ./setup.py install`

If it installs properly, you should get a handy new tool `mididumphw.py` which will tell you what MIDI-compatible synths you've got running and what Client/Port IDs you'll need to connect to to use them.

##Using `midi-piano.py`

You'll find the MIDI Piano example in the examples folder of this repository, or in `~/Pimoroni/piano-hat` if you used our installer script. By default it supports SunVox and yoshimi:

* Sunvox ( Get it from http://www.warmplace.ru/soft/sunvox/ )
* Yoshimi ( `sudo apt-get install yoshimi` )

Run either of these synths first, and then run `sudo ./midi-piano.py` and start playing. For best results, you should use a Pi 2- especially with Yoshimi which can be a bit taxing on the older models.
