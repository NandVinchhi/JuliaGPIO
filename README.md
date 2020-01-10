## Overview
Via this tutorial, we shall be going over the entire process of installation and use of the Julia Programming language on a Raspberry Pi. We will be using the [PiGPIO.jl](https://github.com/JuliaBerry/PiGPIO.jl) library for controlling GPIO elements (namely LEDs). 

## What you'll need
You will require a Raspberry Pi (I am using a Raspberry Pi 3 model B+), along with the standard peripherals(keyboard, mouse, display, power supply), 1 breadboard, 2 resistors, 2 LEDs and jumper wires. I am assuming that you have the Raspbian OS set up and running on the Raspberry Pi. If not, take a look at [this tutorial.](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up)

## Setting up Julia

In your Raspbian commmand line, simply run:

```
sudo apt install julia
```

Then, run this to enter the Julia REPL
```
julia
```
now run the following commands to install the PiGPIO library:

```
using Pkg
Pkg.add("PiGPIO")
```
You should now be ready to start with the circuit

## Building the Circuit

connect the cathode of both the LEDs to the ground rail of the breadboard. Connect the anode, via an appropriate resistor (I used 82 ohm) to GPIO pins 2 and 3 of the Raspberry Pi.

#### circuit diagram for reference: 
