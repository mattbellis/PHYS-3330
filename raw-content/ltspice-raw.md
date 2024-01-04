---
title: "Lab Skill Activity - Simulating Electronic Circuits"
author: [Department of Physics | University of Colorado Boulder]
---

# Goals

You will install and learn the basics of using LTspice (a particular SPICE program) and simulate a voltage
divider.

Proficiency with new equipment

- LTspice:
  - Install program
  - Learn how to configure and simulate a voltage divider circuit

# Definitions {#sec:def}

**SPICE:** A general purpose open source Simulation Program with Integrated Circuits Emphasis
**LTspice:** A SPICE program developed by Linear Technology (now owned and maintained by Analog Devices)

# Preparation {#sec:prep}

**Installing LTspice:** [Download](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) and install the LTspice simulation software.

**How to use LTspice:** [This](https://www.youtube.com/watch?v=JRcyHuyb1V0) tutorial video demonstrates basic functions of the program by simulating a voltage divider. It lasts about 12 minutes. If you have installed the program already, you can skip the installation part and watch starting from 2:30.

This tutorial (and the following instructions) are based on the Windows version. For help with the Mac version, you should also review the two files on Canvas under Modules -> LTSpice: “Tips for LTspice_on_Mac” and “LTspiceShortcutsForMacOSX”.

# Simulating a Voltage Divider

Something here

## Making a circuit

1. Bring each electronic component, a power supply and two resistors from the tool bar.
2. Wire them using the ‘pen’ tool on the tool bar.
3. Add a ground that corresponds to the negative side of the power supply.
4. Set parameters of the components by right-clicking on each component as shown below and

include a Vout label in between the two resistors.

2
Case 1 Power Supply Resistor 1 (Ω) Resistor 2 (Ω)
10 V, DC 1k 1k

## Running a simulation of the circuit

1. Set simulation parameters using ‘Edit Simulation Command’ from the ‘Simulate’ menu.
2. Choose Transient and set the Stop Time to 1s, see the tutorial video.
3. Run the simulation by clicking the ‘running man’. Then you will see a graph window.
4. You can select a value of your interest in the circuit with the mouse. Choose the voltage.
5. On a point of a wire for voltage
6. On a component for current
7. On a component with the alt key for power

## Displaying the Simulation Graph

1. Adjust the scale of y-axes of the graph and select which data to present as shown in the video

for a good presentation of the simulation. (Optional)

2. Choose power dissipated in R1. Notice that the graph shows two values using the vertical axes

on the left for one value and the vertical axes on the right for the other value.

3. You can zoom in the graph by selecting an area with the mouse (Optional)
4. You can select or deselect graphs using ‘Pick Visible Traces’ tool on the tool bar (Optional)

## Copying the Graph or Circuit on the Screen

1. Copy the image of the graph or circuit to clipboard using the menu in the ‘Tools’. Copy the result

of the simulation showing the Vout and power at R1 and paste it into your electronic lab
notebook. On Mac, you can either do a screenshot or print to a PDF file.

2. Verify that these results match what you find from calculations using Ohm’s Law (V = IR) and the

power equation (P = IV = I2 R = V2 /R). Include your calculations in your notebook.
## Variation of the Simulation

3
Repeat Steps 1-4 for the two following cases. You don’t need to do the calculations (Step 4.2) for Case
3.
Case 2 Case 3
Power Supply 10 V 10 V peak-to-peak with 0 DC offset, 1 kHz, sine wave
Resistor 1 (Ω) 10 k 10 k
Resistor 2 (Ω) 90 k 90 k

## Step 6

Save the circuit file with a good name to save. The default extension of the saved file is “asc” when the
circuit area is selected. Upload the asc file to Canvas (in addition to the pdf in step 7).
## Step 7
Write a short conclusion paragraph about this activity. Combine this conclusion with your log of the
steps above, including snapshot circuits and result plots from LTspice, and save as a PDF and submit to
Canvas (in addition to the asc file in step 6).
