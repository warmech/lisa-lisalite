# Lisa Lite

The Lisa Lite is an adapter card for the Lisa 2 and 2/5 that allows a Twiggy drive to be replaced by a 400K Sony 3.5" floppy drive. Most of the signals are passed directly from the Twiggy interface to the Sony interface, though the motor clock signal on the Twiggy side is used as the basis (along with a 5MHz oscillator) for generating the PWM signal used to drive the Sony drive.

![Lisa Lite Front](/images/pcb_front_render.png)

![Lisa Lite Rear](/images/pcb_rear_render.png)



## Assembly

There is little to explain in terms of assembly, as the card uses relative few components. It should be noted that it is recommended to use keyed connectors for the Twiggy and Sony ribbon cable connectors. Inserting the cables backwards will result in the +12V power rail being piped into the CA0, CA1, CA2, and LSTRB lines on the Sony drive and the READ and MTRCLK lines on the Twiggy interface; this will likely destroy any ICs on these lines and possibly other passive and/or electromechanical components.

## Use

There is also little to explain in terms of installation and use. The Lisa Lite fastens into two standoffs on the side of the internal drive cage closest to the monitor. The wide Twiggy ribbon cable connects to the interface at the rear of the card and the narrow ribbon cable to the interface in the card's middle. A socket may be used for the oscillator if desired, though it's not necessary by any means.

Once the card is installed and connected, no further action is required for use; the card is effectively a passive component itself and the Lisa ROM/IWM manages interfacing with the Sony drive.

## Miscellany

This card is unnecessary on a 2/10, which uses an IC on the I/O card to handle communications with a Sony drive. Additionally, an 800K drive may be used in conjunction with a Sun Remarketing ROM intended for use with the Macintosh XL.

This is a very simple design that I would like to eventually replace with a small CPLD for use in an ATX form-factor Lisa. As it's so tiny a curcuit, the Verilog required for this practically writes itself.
