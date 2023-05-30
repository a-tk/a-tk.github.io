---
layout: post
title:  "Diamond Section Saw"
date:   2023-05-15 20:13:02 -0700
categories: machine-shop
---


![section-saw](/assets/section-saw/section-saw-15.jpg)

## Section Saw? 

What is a section saw? A section saw is usually a small saw that utilized diamond blades to cut
all kinds of material. Materials could be rocks, fossils, epoxy filled electronics and many more.
A typical saw will utilize flood coolant. 

I am not interested in using a section saw for any of those though, my use case will be
to cut HSS tool blanks and tungsten carbide blanks to make scraper blades, boring tools
and other things that would be useful in a machine shop. 

While the variety of material that can be cut is an advantage, one disadvantage is
that cutting speed is relatively low. 

## Design

I used to own an industrial section saw, but at 2'x3', it was just too big to keep
around my shop. When I disassembled it, I was happy to learn it was very simple inside. 
A small DC motor to power the blade, a simple gear train (actually belts), and 
basic DC speed controller was essentially all that was there. 

Taking notes from this, I designed a much smaller mechanism using scrap parts that I
have had lying around for some time. Two 15mm aluminum plates, bearings, and a 
small but powerful DC motor, but with a twist: I'd use diamond wire to build a
bandsaw blade. 

## Build

Building was pretty straightforward, mostly standard techniques for everything. 

Of note was (because it's new to me) was using a boring head in the horizontal
spindle to machine bearing seats.

![section-saw](/assets/section-saw/section-saw-1.jpg)

![section-saw](/assets/section-saw/section-saw-2.jpg)

The frame was separated by simple and cheap aluminum standoffs. Spring washers
used to preload the bearings.

### Build Pictures

![section-saw](/assets/section-saw/section-saw-3.jpg)

![section-saw](/assets/section-saw/section-saw-4.jpg)

![section-saw](/assets/section-saw/section-saw-5.jpg)

![section-saw](/assets/section-saw/section-saw-6.jpg)

![section-saw](/assets/section-saw/section-saw-7.jpg)

![section-saw](/assets/section-saw/section-saw-8.jpg)

![section-saw](/assets/section-saw/section-saw-9.jpg)

![section-saw](/assets/section-saw/section-saw-10.jpg)

![section-saw](/assets/section-saw/section-saw-11.jpg)

## Diamond Bandsaw

The most notable part of this project is the diamond bandsaw blade.

I had the idea after building my spot welder, and finally ordered some 
0.011" diameter diamond wire to test it out. I needed a blade with a
circumference of about 20," and the stock comes in 5 meter lengths
for an inexpensive price. 

I first tried to weld using the spot welder itself, but such thin wire was 
obliterated by even the lowest voltage settings. 

I quickly realized I needed a new solution. 

## Blade Welder

I build a simple version of the blade welder shown in [this paper](https://www.researchgate.net/publication/323925136_Test_rig_for_welding_diamond_wires_into_a_loop).

![section-saw](/assets/section-saw/section-saw-13.jpg)

They basically found that using small welding currents (20A) would properly fuse the wire. 

My welding system used a small and very low friction linear slide to hold two copper
electrodes. The electrodes also double as clamping surfaces for the wire. 

An electrical contactor was used to route the ~20A to the welder itself. This
particular model was from my engineer's stash, and uses a 24VDC coil. 

Now, I simply needed some control circuitry. 

### Circuit Design

As a welding process, time during welding is very important. A simple 555 
timing circuit was utilized for this purpose.

![section-saw](/assets/section-saw/section-saw-12.jpg)

![section-saw](/assets/section-saw/section-saw-14.jpg)

This is a monostable multivibrator put together with components I had lying around. 

Since the 555 cannot produce the currents needed to saturate the contactor coil,
a transistor on the output is used (with diode flyback protection).

Other design notes

- LM7805 used to step the voltage down for the NE555.
- 'Annealing' mode (basically just a bypass to hold the transistor 'on') provided by a small switch

### Success?

While I could now produce welding diamond saw blades, I found limited success in
their use. Welding the blades will almost always create a weld bead that exceeds the 
current diameter of the wire, and this would need to pass through a cut many hundreds
of times before a cut is complete. Extensive testing revealed that the blade
weld sites would also fail from fatigue before the completion of a weld. 

Testing parameters:
- Wire diameter
- welding current
- welding voltage
- welding pressure
- welding time
- annealing temperature
- annealing time

Next steps for the wire welder would be to test with larger diameter drive wheels.
The current wheels may be too small and also fatiguing the weld site. 

## Lapidary Saw Blades

Instead of being stuck with a not-working solution and no ability to cut 
carbide, an adapter was built that would allow the saw to use 4" lapidary saw blades. 

![section-saw](/assets/section-saw/section-saw-15.jpg)

These blades are also cheaply purchased and do a fine job. 

Fortunately, the saw could easily be converted to hold the workpieces in
a simple cutting sled. 

![section-saw](/assets/section-saw/section-saw-16.jpg)

And the test pieces (1/8" HSS drill blank and 1/16" x 1/2" carbide blank)
were cut!


![section-saw](/assets/section-saw/section-saw-17.jpg)
