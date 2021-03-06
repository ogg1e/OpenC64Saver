## OpenC64Saver

OpenC64Saver is an Open Hardware implementation of the [Computer Saver device developed by Ray Carlsen](http://personalpages.tds.net/~rcarlsen/cbm/c64/SAVER/saver.txt), mainly targeted at Commodore 64 users.

![Board](https://raw.githubusercontent.com/SukkoPera/OpenC64Saver/master/doc/render-top.png)

### Summary
> This over-voltage protection unit is designed to prevent damage to
the Commodore 64 computer due to a failing power supply. One of the ways 
the Commodore "brick" power supply can fail is from a shorted internal 
5 volt regulator. That fault puts excessive voltage into the computer 
and damages chips such as RAM very quickly... and silently. The Saver 
protector is essentially a fast-acting electronic circuit breaker. It 
functions to quickly cut off the 5 volt supply line to the computer if 
the voltage exceeds about 5.4 volts. It is not a "crowbar" device but 
opens the line from the supply to the computer before the voltage gets
high enough to do damage. That's the safest way to do it. After-market 
power supplies, even switching types, can fail at any time. Switchers 
are more reliable and much less prone to catastrophic failures but can 
still cause damage to the computer if they fail. This Saver is designed 
to protect any computer that uses the standard Commodore "brick" power 
supply as well as any newer switch-mode PS. Computers include all 
versions of the C64, the later CR version of the VIC20, and the Plus/4. 
Because of its square power connector, an external Saver is possible 
for the Plus/4 but its power socket would have to be changed to the 
round C64 version because four pin square DIN connectors are not 
available. - Ray Carlsen

### Installation
> There are several ways to add this protection device to your system.
One way is to install the components or a completed module inside the 
computer. That way, it is protected from any supply plugged into it. If 
you have more than one computer, a protector can be installed in each 
one. To install the protector circuit inside a C64, it is necessary to
open the +5 volt line on the circuit board. Input and output lines of
the protector are wired to each end of the now-open circuit. If your
C64 board differs from the pictures on my site, you will have to locate
the correct area of your board to open the line and make the connections. 
In all internal versions, the correct point is electrically between the 
power connector and the power switch. There are at least five board 
versions of that computer, each with a different PC board layout, and 
the physical connections will be specific for each board.

Ray's motherboard pictures can be found at http://personalpages.tds.net/~rcarlsen/cbm/c64/SAVER/MOBOs/.

### Configuration
OpenC64Saver includes a trimmer to set the cut-off voltage:

> Because of fairly wide Saver component tolerances and to 
accommodate the normal voltage variations of even good power supplies, 
the basic Saver circuit must be "trimmed" so the voltage cuts off at 
about 5.4 volts DC. If set too high, it will not protect the computer; 
if too low it will trip prematurely even with a good PS. Feedback from 
a few users indicated the Saver would trip when they turned their 
computer off, and it remained in failsafe mode until unplugged from the 
PS. Apparently some power supplies output can jump up past the failsafe 
point when the load on them is suddenly removed (computer off). That's 
why the trip point is set as high as it is. 5.4 volts is still under 
the "absolute maximum rating" specification for the RAM chips.

To properly set the cut-out voltage you will need a variable DC supply and a voltmeter:
- Slowly increase the supply voltage until you hear the relay cut in (voltage appears on the relay output side)
- Continue advancing it until the relay cuts out again. The voltage at that instant is the trip point of the device.
- If it is too high, decrease the supply voltage until the relay cuts in again, rotate the trimmer screw, and repeat the above procedure.

> Note that the Zener diode is somewhat temperature sensitive. If very cold, the
trip point will read high, and if hot from soldering, the trip point will be low. Therefore, the mounting of the Saver components, if inside the computer, should be away from all heat producing components.

### License
OpenC64Saver is Open Hardware.
