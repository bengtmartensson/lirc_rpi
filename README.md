# lirc_rpi: GPIO-based Lirc driver for Raspberry Pi

This code is a further development of the [Lirc driver for the
Raspberry Pi by Aron Szabo](http://aron.ws/projects/lirc_rpi/), which
was derived from the Lirc serial driver.

The added features are: Multiple transmitter support, support for
"modulation frequency 0", and the programmable inversion of outputs.

It is described in greater detail in
[this article](http://harctoolbox.org/lirc_rpi.html) (not quite up-to-data). Please also see
[this article](http://harctoolbox.org/rpi_daughterboard.html) for possible hardware.

The original work is copyrighted under the GNU General Public License,
version 2 "or later". Being a derived work, this goes for my version
too.

## Update 2016-12-06
Updated for current Raspberry Pi OS, including device tree (the file lirc-rpi-overlay.dts).
Tested with Raspian May 2016 kernel 4.4.11-v7+. Changes:

* The option `gpio_out_pins` has been renamed to `gpio_out_pin` (singular), to be compatible by the original `lirc_rpi`.
  Suggested by Aron.
* New option `gpio_in_pull` (from the Raspian `lirc_rpi`).
* The option `tx_mask` has been removed (not really a module parameter, but a user parameter).
* Support for devicetree; the new file `lirc-rpi-overlay.dts`. (Note the hyphens; there is an
  underscore in `lirc_rpi`.) Note that the actually used pins (or a superset thereof)
  have to be defined in this file, which is subsequently compiled,
  for example when building the kernel. 

