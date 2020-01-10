## Overview
Via this tutorial, we shall be going over the entire process of installation and use of the Julia Programming language on a Raspberry Pi. We will be using the [PiGPIO.jl](https://github.com/JuliaBerry/PiGPIO.jl) library for controlling GPIO elements (namely LEDs). 

## What you'll need
You will require a Raspberry Pi (I am using a Raspberry Pi 3 model B+), along with the standard peripherals(keyboard, mouse, display, power supply), 1 breadboard, 2 resistors, 2 LEDs and jumper wires. I am assuming that you have the Raspbian OS set up and running on the Raspberry Pi. If not, take a look at [this tutorial.](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up)

## Setting up Julia

In your __Raspbian commmand line__, simply run:

```
sudo apt install julia
```
Next, we need to launch a __pigpio daemon__, which PiGPIO.jl can connect to and control the GPIO pins. To do this, run the following command.
```
sudo pigpiod
```
Then, run this to enter the __Julia REPL__
```
julia
```
now run the following commands to install the __PiGPIO__ library:

```
using Pkg
Pkg.add("PiGPIO")
```
You should now be ready to start with the circuit

## Building the Circuit

connect the __cathode__ of both the LEDs to the __ground rail__ of the breadboard. Connect the __anode__, via an appropriate resistor (I used 82 ohm) to __GPIO pins 2 and 3__ of the Raspberry Pi.

#### circuit diagram for reference: 
<circuit diagram>

<circuit pic>
 
You are now ready to launch Julia and start coding. PiGPIO.jl should be installed by now.

## The Code
First we need to import the package with the __using__ keyword. Next, we need to initialize the Raspberry Pi by creating an object variable and initialising it to __Pi()__
```Julia
using PiGPIO
pi = Pi()
```

