---
title: "Lab Skill Activity - Simulating Electronic Circuits"
author: [Department of Physics | University of Colorado Boulder]
---

# Goals

You will install and learn the basics of using LTspice (a particular SPICE program) and simulate a voltage
divider.

Proficiency with:

- LTspice:
  - Install program
  - Learn how to configure and simulate a voltage divider circuit

# Definitions {#sec:def}

**SPICE:** A general purpose open source Simulation Program with Integrated Circuits Emphasis

**LTspice:** A SPICE program developed by Linear Technology (now owned and maintained by Analog Devices)

# Preparation {#sec:prep}

**Installing LTspice:** [Download](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) and install the LTspice simulation software.

**How to use LTspice:** [This](https://www.youtube.com/watch?v=JRcyHuyb1V0) tutorial video demonstrates basic functions of the program by simulating a voltage divider. It lasts about 12 minutes. If you have installed the program already, you can skip the installation part and watch starting from 2:30.

This tutorial (and the following instructions) are based on the Windows version. For help with the Mac version, you should also review these two files:

- [Tips for LTspice on a Mac](../resources/ltspice-resources/TipsForLTspiceOnMac.pdf)
- [Mac keyboard shortcuts for LTspice](../resources/ltspice-resources/LTspiceShortcutsForMacOSX.pdf)

# Simulating a Voltage Divider

Something here

## Making the circuit

1. Insert each electronic component (a power supply and two resistors in this case) by selecting the appropriate toolbar icon and then clicking to place in the model window.
2. Wire them together using the ‘pen’ tool on the tool bar.
3. Add a ground that corresponds to the negative side of the power supply.
4. Include a $V_{out}$ label in between the two resistors.
5. Set parameters of the components by right-clicking on each component (use the values for Case 1 in the table below).

<center>

| Parameters            | Case 1   | Case 2  | Case 3                                               |
| --------------------- | ------- | ------ | --------------------------------------------------- |
| Power Supply          | 10V, DC | 10V    | 10V peak-to-peak with 0V DC offset, 1kHz, sine wave |
| Resistor 1 ($\Omega$) | 1k      | 10k    | 10k                                                 |
| Resistor 2 ($\Omega$) | 1k      | 90k    | 90k                                                 |

</center>

## Running a simulation of the circuit

1. Set simulation parameters using ‘Edit Simulation Cmd’ from the ‘Simulate’ menu.
2. Choose Transient and set the "Stop time" to 1s.
3. Run the simulation by clicking the ‘running man’ icon in the toolbar. Then you will see a graph window.
4. You can select a value of your interest in the circuit my using your cursor to click on:
   - a point of a wire for a voltage
   - a component for the current
   - a component with the alt key for the power

## Displaying the simulation graph

1. Adjust the scale of y-axes of the graph and select which data to present as shown in the video for a good presentation of the simulation. 
1. Choose power dissipated in R1. Notice that the graph shows two values using the vertical axes on the left for one value and the vertical axes on the right for the other value.

3. You can zoom in the graph by selecting an area with the mouse.
4. You can select or deselect graphs using ‘Pick Visible Traces’ icon on the tool bar.

## Copying the graph or circuit on the screen

1. Copy the image of the graph or circuit to clipboard using the option in the ‘Tools’ menu. This will copy an image of the active window within LTspice. Copy the result of the simulation showing the $V_{out}$ and power at R1 and paste it into your lab notebook. On Mac, you can either do a screenshot or print to a PDF file.

2. Verify that these results match what you find from calculations using Ohm’s Law ($V = IR$) and the power equation ($P = IV = I^2 R = V^2 /R$). Include your calculations in your lab notebook.

## Variation of the Simulation

Repeat the steps above for Case 2 an Case 3. You don’t need to do the calculations for Case 3.

## Save your simulation

Save the circuit file with an appropriate descriptive filename. The default extension of the saved file is .asc when the circuit window is selected. Upload the .asc file to Canvas.

## Summary
Write a short conclusion paragraph about this activity. Combine this conclusion with your log of the
steps above (a scan of your lab notebook), including snapshot circuits and result plots from LTspice, and save as a PDF and submit to Canvas.
