# DIY-ATtiny85-Programmer
These microcontrollers comes handy when space is limited, isn't that? But how annoying is to wire the UNO-ISP every time we want to upload a sketch? We need a simple-but-effective tool in our box to speed up the process and give the fun a fast kick!

# Intro
ATtiny85 is a small but powerful microcontroller from Microchip Technology. Six pins, built-in 10-bit ADC, SPI or I2C communication ready, 5V logic, and dimensioned like a dual op-amp, this chip is an ideal choice when "MCU magik" has to be performed, but limited space is available.

Being a barebone microcontroller, not the usual full Arduino board we’re familiar with, we cannot connect it directly to a PC to upload a sketch. We are instead in the need for a dedicated programming environment.

Luckily for us Arduino community comes to the rescue, and a simple-but-effective way to program ATtinys has been available for a long time now.

This calls for a UNO microcontroller board running as ISP (In-circuit Serial Programmer).

Wiring the "master" UNO to the ATtiny85 for programming is a very instructive (thus recommended) experience, but doing it from scratch any time one needs to test a sketch becomes annoying after a while.

I had realized a perfboard shield for my personal use some time ago, the only issue with that being the need to disconnect the UNO's USB power cable every time I had to remove the microcontroller to avoid the risk of shorting something. Not good for the hardware, especially when continuous insert-remove actions have to be made to test minimal code changes.

Being that I make use of ATtiny85 in my projects (audio mixer module and a forthcoming arpeggiator module, just to cite a few) the time had come to roll something more clean and share it so that anybody interested could assemble a copy and have it ready in its toolbox.

PS: yes, I know: there are various UNO shields for ATtiny85 programming, but this-is-mine ;)

# Supplies
1x "Another ATtiny85 Programmer Shield" PCB

1x Arduino UNO

2X 10uF capacitor (electrolitic)

1x 100nF capacitor ( non polarized, 104)

1x LED, 3mm

1x 2K ohm resistor

1x ON/ON switch (single pole, double throw SPDT)

1x ZIF socket (16 pins)

# Hardware
To turn a UNO into an ATtiny programmer only few boundary elements are in the need. A barebone programming environment is made by the UNO itself, a DIP-8 socket and 6 wires in total.

This shield follows the common, default wiring, here reported for completeness:

(please notice that UNO pinout refers to silk screened pin numbers, while ATtiny pinout refers to package pin numbers)

Arduino UNO → ATtiny85

5V → Pin 8 (Vcc)

GND → Pin 4 (Gnd)

D13 → Pin 7 (SCK)

D12 → Pin 6 (MISO)

D11 → Pin 5 (MOSI)

D10 → Pin 1 (Reset)

The choice for ZIF socket comes from the possibility to remove the ATtiny85 without the need to unplug the power every time you want to test the micro with it's fresh sketch uploaded. This is instead necessary to avoid the risk of shorts when a DIP-8 socket is adopted (most of the time the IC removing tool of choice is a small screw driver).

ZIF-4 are not commercialized, so I had to use a bigger ZIF (16 pin ZIF), shorting the unused pins to ground.

The PCB is compatible with DIP-8 socket, if you only have those around. User can disable power to the chip through the on-board ON/OFF switch. Switching the power off before removing the chip is not entirely necessary with a ZIF socket.

The on-board LED gives visual feedback about the presence of 5V at ATtiny85 Vcc input.

There are two capacitors on board. The ceramic is used to stabilize the 5V line; the electrolitic is used to prevent the UNO from resetting while programming the tiny.

# How to Program
## 1: Turn Your Arduino UNO into a Programmer
The first step is to configure your Arduino UNO to work as an ISP:

Open the Arduino IDE.
Connect your Arduino UNO to your PC.
Go to File -> Examples -> ArduinoISP and open the ArduinoISP.ino example.
Upload the ArduinoISP sketch to your Arduino UNO.

## 2: Upload the Sketch
Select the appropriate microcontroller and clock source:

Go to Tools -> Board and select "AttinyCore -> ATtiny45/85 Optiboot".
Under Tools -> Clock Source, select "8MHz Internal" (this should already be set by default, but double-check).
Open the sketch you want to upload.

Now, go to Tools -> Programmer and select "Arduino as ISP".

Burn the bootloader:

Go to Tools -> Burn Bootloader.
Upload the sketch:

Select Sketch -> Upload Using Programmer
Don't use the arrow on the upper left or you wil reprogram your UNO instead of you ATtiny!

Note: Burn the bootloader each time you upload a new sketch.

# Acknowledgments
Many thanks to the nice girls and guys at [JLCPCB](https://jlcpcb.com/?from=IAT) for sponsoring PCBs manufacturing for this project.

In this run of PCB's they also manufactured some preliminary board for the very next project: a multi FX guitar pedal (stay tuned ;))

JLCPCB is a high-tech manufacturer specialized in the production of high-reliable and cost-effective PCBs. They offer a flexible PCB assembly service with a huge library of more than 600.000 components in stock at today.

3D printing is part of their portfolio of services so one could create a full finished product, all in one place!

What about nano-coated stencils for your SMD projects? You can take advantage of a coupon and test it for free in these days.

By registering at JLCPCB site via [THIS LINK](https://jlcpcb.com/?from=IAT) (affiliated link) you will receive a series of coupons for your orders. Registering costs nothing, so it could be the right opportunity to give their service a due try ;)
