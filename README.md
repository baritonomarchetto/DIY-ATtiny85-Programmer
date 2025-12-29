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

