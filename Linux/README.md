There are a few ways to remap keys in Linux. Here's a description of the method I went with.

Every input device sends a *scancode* when a key is depressed. The kernel then
maps this to a *keycode*. The idea is to let `udev` intercept the scancode and
remap it to whatever we want the new keycode to be.

### Get the device identifier
First, before actually doing the remapping, we need to let `udev` know what
device it's looking for. Use the command `evemu-describe`, provided by the
[`evemu`](https://www.freedesktop.org/wiki/Evemu/) package. In a terminal, enter
```bash
$ sudo evemu-describe > description.txt
```
You'll be asked to choose a device from a list of input devices, after which
the utility writes out the device's info to `description.txt`.
Open up `description.txt`. For example, for a Logitech USB keyboard, at line 5,
you'll see something like
```bash
# Input device ID: bus 0x03 vendor 0xc45 product 0x7403 version 0x110
```
These are the numbers we'll use to tell `udev` which device to look for.

### Determine the scancode
Now we'll find the scancode of the key we want to remap. For this we'll use the
utility `evtest`.
```bash
$ sudo evtest
```
As before, you'll be asked to choose your device. Next you'll be put into an
interactive mode, where each key press outputs a bunch of information. For
example, pressing `F5` on an unmodified keyboard yields
```
Event: time 1529858847.324741, -------------- SYN_REPORT ------------
Event: time 1529858849.476742, type 4 (EV_MSC), code 4 (MSC_SCAN), value 7003e
Event: time 1529858849.476742, type 1 (EV_KEY), code 15 (KEY_F5), value 1
```
The scancode is the value number after `MSC_SCAN`, so for example the scancode of `F5` is 7003e.

I've found that for most external Logitech keyboards, `F5` has scancode 7003e; `F6` has 7003f;
`F7` has 70040; and `F8` has 70041.

### Write a configuration file for `udev`
We put the above ingredients into a configuration file, which is saved
in the folder `/etc/udev/hwdb.d/`. Each scancode is remapped to the new
keycode, which is represented as a lowercase string. A sorted list of possible
keycodes is available
[here](https://hal.freedesktop.org/quirk/quirk-keymap-list.txt).

Here's an example configuration file for all Logitech USB keyboards. Notice the
bus identifier in the second line is set to 0003, for USB keyboards; and the
vendor id is set to 064d, which is the id for Logitech.
```bash
evdev:input:b0003v046d*       # All USB Logitech keyboards
 KEYBOARD_KEY_7003e=tab       # bind F5 to tab
 KEYBOARD_KEY_7003f=esc       # bind F6 to esc
 KEYBOARD_KEY_70040=backspace # bind F7 to backspace
 KEYBOARD_KEY_70041=enter     # bind F8 to enter
```
Let's save the file as `91-logitech.hwdb`, and move it to `/etc/udev/hwdb.d/`:
```bash
$ sudo mv 91-logitech.hwdb /etc/udev/hwdb.d/
```
### Rebuild the hardware database
Finally, we rebuild the database of input hardware, via
```bash
$ sudo systemd-hwdb update
```
On reboot, the four function keys `F5`-`F8` will be remapped as desired.

## Rinse, repeat for all input devices
The procedure is basically the same for a USB foot switch. Determine the device
identifier, the scancodes, the name of the remapping, and save to a `udev` config file.

For internal laptop keyboards, it's a bit different. I've included an example
config file, which should match all internal laptop keyboards. All you need to
do is check that the scancodes are correct for your laptop. Modify as you see
fit, then place in `/etc/udev/hwdb.d/` as usual.
