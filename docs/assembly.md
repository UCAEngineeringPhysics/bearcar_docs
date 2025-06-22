# Hardware Assembly Guide

We recommend you to follow the order to assemble your BearCar

## 1 ESC Upgrade

1. Remove Body Cover and Battery
2. Remove Stock ESC
3. Install Quicrun ESC

![esc_install](images/assembly/esc_install.jpg)

## 2 Wire Splitter

The wire splitter splits the 2 input channel into 4 output channels.
The channels in same color are connected together.
We recommend you to plug positive wires to the orange channels, and negative wires to the blue channels.

1. Plug in wires with **male** T-plug connector to the **input** end.
2. Plug in wires with **female** T-plug connector to the **output** end.
3. Plug in wires with JST-XH connector to the **output** end.

> _You may need to peel extra skin off these wires.
Or the levers may bite the skins not the wires that leads to a broken circuit._

### Pre-Assembled

![splitter pre-assemble](images/assembly/pre_splitter.jpg)

### Post_Assembled

![splitter post-assemble](images/assembly/post_splitter.jpg)

## 3 Frame Bed

1. Wire Splitter Assembly Installation (2xM2.5-12 screws and 2xM2.5 nuts)
2. Attach RPi power expansion board (4xM2.5-15 standoffs, 4xM2.5 nuts)
3. Stack Raspberry Pi 5 (4xM2.5-15 standoffs)
4. Stack Pico carrier board (4xM2.5-6 screws)
5. Insert Raspberry Pi Pico.

### Splitter Assembly Installation

![splitter install](images/assembly/splitter_install.jpg)

### RPi Power Expansion Board Installation

![peb_install](images/assembly/peb_install.jpg)

### Raspberry Pi 5 Installation

![pi5_install](images/assembly/pi5_install.jpg)

### Pico Carrier Installation

![carrier_install](images/assembly/carrier_install.jpg)

## 4 Frame Handle

1. Assemble camera module.
2. Mount camera to the case.
3. Attach camera case assembly to handle.
4. Assemble the handle and the bed.

## 5 Car Frame Integration

1. Attach ESC switch.
2. Fasten frame to car body.
3. Connect ESC and servo signal wires to Pico carrier board.
4. Connect Pico to Pi 5 with Micro-USB cable
5. Connect ESC power wires.
6. Connect RPi power expansion board power input wires.
7. Connect battery.
