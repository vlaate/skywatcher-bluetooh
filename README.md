# skywatcher-bluetooh

A few years ago, Skywatcher [open-sourced their API](https://github.com/skywatcher-pacific/skywatcher_open), which "provides a fundamental framework for user to control SkyWatcher mounts via PC, Mac, Linux or Smart Phone". 

Many have used this API to connect computers/tablets to their Skywatcher telescopes, and some android/iOS apps were built for this purpose.

In order to use the API or any of those apps, you need to actually connect the PC/tablet to your Skywatcher telescope, and that's where this little circuit comes in: it is a very simple connection for plugging a bluetooth serial adapter to the RX/TX pins of the Skywatcher Virtuoso mount (also known as Orion Starblast Autotracker).

This is my Orion Starblast Autotracker, a very fine mount (also sold as "Skywatcher Virtuoso"):
![alt text](https://raw.githubusercontent.com/vlaate/skywatcher-bluetooh/master/orion-autotracker.jpg "OrionStarblast Autotracker")

And this is the cuircuit assembled:
![alt text](https://raw.githubusercontent.com/vlaate/skywatcher-bluetooh/master/bluetooth-internals.jpg "Bluetooth adapter")

And the schematic for building it:
![alt text](https://raw.githubusercontent.com/vlaate/skywatcher-bluetooh/master/autotracker-virtuoso-Bluetooth.png "skywatcher bluetooth")

The HC-05 bluetooth adapter that I used is [this one](https://www.aliexpress.com/item/Bluetooth-Module-HC-05-with-cable-Host-and-Slave-3-6-6V-for-Arduino-uno-by/762120245.html)

Be careful with the resistors: they are only 100 ohms, so very small. The reason I recommend two in parallel for TX is to spread power dissipation, at 12V it's safer with two 100 ohm than with a single 50 ohm resistor. 

The order of the RJ-11 pins from top to bottom corresponds to linear order of the bare copper contacts in the actual connector (the ones that will touch the RJ11 cable), so make sure you get that order sorted out first (using a multimeter).

Before building anything, measure the voltage between the VCC and GND pins to make sure you get *positive* 12V, in order to be certain that you have the correct pins for VCC and GND, and that you got the pin order right. If you get negative 12V, you probably have it in reverse order.

This schematic is released under an MIT license. You *will* void your mount's warranty if you use this, so this circuit schematic is provided WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL I BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE CIRCUIT.
