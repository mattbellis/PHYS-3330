---
title: "Lab 8"
subtitle: "Field-Effect Transistors: MOSFETS"
author: [Department of Physics | University of Colorado Boulder]
date: '2022-12-07'
caption-justification: centering
toc: true
toc-own-page: true
titlepage: true
header-left: "\\thetitle"
header-center: "Bipolar Junction Transistors"
header-right: "PHYS 3330"
footer-left: "\\thedate"
footer-center: "\\copyright \\theauthor"
footer-right: "Page \\thepage"
listings-no-page-break: true
code-block-font-size: \scriptsize
---

As discussed in the last lab, transistors are the basic devices providing control of large currents with small signals. There are two general types of transistors, bipolar and field-effect. The difference between these two types is that for bipolar devices an *input current* controls the large current flow through the device, while for field-effect transistors an *input voltage* provides the current control. In the last experiment, you used the transistor as a voltage amplifier. In the present experiment, you explore using the FET type transistors as a current controller to create an electromagnet.

# Goals

Proficiency with new equipment: MOSFETS and magnetic coils

Applications: Build a voltage-controlled electromagnet

# Definitions

**Threshold voltage, V~th~** -- minimum gate-to-source voltage to allow current to flow.

**V~GS~** -- Gate to Source voltage difference

**V~DS~** -- Drain to Source voltage difference

# FET Basics

The input to a FET is called the gate (see Figure @fig:mosfetpo), analogous to the base of a bipolar transistor. But unlike the situation with bipolar transistors, almost no current flows into the gate, and FETs are nearly ideal voltage amplifiers with very high input impedance. In junction FETs (JFETs) the gate is connected to the rest of the device through a reverse-biased pn junction, while in metal-oxide-semiconductor FETs (MOSFETs) the gate is connected via a thin insulating oxide layer. Bipolar transistors come in two polarities called npn and pnp, and similarly FETs come in two polarities called n-channel and p-channel.

In integrated circuit form, small MOSFETs are ubiquitous in digital electronics, used in everything from simple logic circuits to the 2.5-billion transistor Intel 10-core Xeon processor chip. Small MOSFETs are also used in some op-amps, particularly when very low supply current is needed, as in portable battery-powered circuits. Small discrete (single) MOSFETs are not normally used because they are extremely fragile. Large discrete MOSFETs are used in all sorts of high power applications, including commercial radio transmitters.

JFETs add very little intrinsic noise to a circuit, and a JFET input op-amp is often the first choice for low-noise amplification. Discrete JFETs are commonly seen in scientific instruments. Consider using a JFET when low-noise is critical. While we will not be exploring this feature in the current lab, you might consider this for a future project.

# MOSFET Current-Voltage Relations

MOSFETs can operate in three distinct regions. The first region is where the gate-to-source voltage, $V_{GS}$, is less than the threshold voltage, $V_{th}$. In this region, the MOSFET is turned off and no current can flow. The second region is when $V_{GS} > V_{th}$ and $V_{DS} < (V_{GS} ~–~ V_{th})$. In this linear region, the transistor is turned on, and a channel has been created that allows current to flow between the drain and the source. In this region, the MOSFET operates like a resistor, controlled by the gate voltage relative to both the source and drain voltages. In the third region, $V_{GS} > V_{th}$ and $V_{DS} \ge (V_{GS} - V_{th})$. This is called the saturation region. Here the current is controlled by the gate voltage and is nearly independent of $V_{DS}$. We will work in the saturation region for this lab. The linear and saturation regions are separated by the dotted line in Figure @figmosfetchar. In the saturation region, the dependence of current on $V_{GS}$ is modeled by $I_D = k(V_{GS} ~–~V_{th})^2$, where $k$ is a constant that depends on the device.

![Typical output characteristics of a MOSFET. These vary greatly between different types of MOSFETs. Always check the data sheet for your exact part. This is not the diagram for the MOSFET you will be using!](https://raw.githubusercontent.com/UCBoulder/PHYS-3330/main/lab8fig/mosfetchar.png){#fig:mosfetchar}

# Useful Readings

1.  [Steck](https://atomoptics-nas.uoregon.edu/~dsteck/teaching/electronics/electronics-notes.pdf) Sections 5.2, 5.3, and 5.4.1

2.  Horowitz and Hill 2^nd^ Ed. Sections 3.01-3.10

3.  The data sheet for the IRF710PBF, the n-channel MOSFET we will be using (on Canvas).

# Prelab

Answer the following questions using Mathematica for the plots. You can use either Mathematica for the rest of the questions as well or do them by hand. **Make sure to have the Mathematica notebook for your lab section as well. You will use it to plot and fit your data during the lab session.**

## Characterizing the MOSFET {#sec:fetcharpre}

1. What is the range of the Gate-Source threshold voltage for the IRF710PBF transistor? The data sheet is on the Canvas.
2. Plot $I_D$ vs. $V_{DS}$ for a value of $V_{GS}$ that will give you about 0.5 A in the saturation regime. You can do this by plotting a bunch of points obtained from Figure 1 of the data sheet. This can give you an idea about where in the saturation region we can operate.
3.  Plot $I_D$ vs. $V_{GS}$ for $V_{DS} = 10 ~V$ using the data available in Figure 1 of the data sheet. Just plot the points in the saturation region. In this region, the drain current dependence on $V_{GS}$ can be modeled as $I_D = k(V_{GS} ~–~ V_{th})^2$. Fit your data points using this model to obtain values for the constant, $k$, and the threshold voltage, $V_{th}$, along with their associated uncertainties. You can refer to your work in Lab Skills Activity 2 for an example of fitting data to a function. Be sure to enter your best estimate of the uncertainties on the input data points. Also, be sure to include the resulting uncertainties when reporting the fitted values of $k$ and $V_{th}$.

## MOSFET controlled electromagnet {#sec:fetmagpre}

1. What is an equation for the magnetic field on axis from a loop of current carrying wire in terms of the radius of the loop, current through the loop, number of turns, and distance from the plane of the loop?
2. Come up with a way of qualitatively measuring the strength of the electromagnet you are going to create and ways of testing at least two of the parameters of the model that determine magnetic field strength.

## Lab activities

1. Read through all of the lab steps and identify the step (or sub-step) that you think will be the most challenging.
2.  List at least one question you have about the lab activity.

# IRF710PBF Pin-Out and Schematic

![MOSFET schematic symbol and pin out configuration.](https://raw.githubusercontent.com/UCBoulder/PHYS-3330/main/lab8fig/mosfetpo.png){#fig:mosfetpo}

**CAUTION!**

1. These transistors are vulnerable to static discharges. Discharge yourself before handling the device. Also, never apply power to a MOSFET before the gate is properly terminated. If the gate is left open, it will turn on when the power supply is connected to the circuit.
2. As you may dissipate lots of power in your transistor, make sure you have a heat-sink attached to your MOSFET. Also, do not touch the FET until you are sure it has cooled off after use.
3. Note that the drain is connected to the back flange of the transistors as well as the center pin.

# Device Characterization

![Test circuit to determine the MOSFET I-V curves.](https://raw.githubusercontent.com/UCBoulder/PHYS-3330/main/lab8fig/testcir.png){#fig:testcir}

## Characterizing the MOSFET {#sec:fetchar}

1. Build the test circuit for the MOSFET shown in Figure @fig:testcir. Make sure to attach a heat sink fin to the FET. (See notes of caution above.) You can use the 10-turn pot on the front panel of your board. The 10-turn pot allows finer control of the $V_{GS}$ than the knobs on the DC power supply. You can measure the resistance between pairs of the three leads to make sure you have it wired correctly. 
2. Devise a quick way to determine the approximate threshold voltage for your device and write down your method. Proceed with finding the approximate threshold voltage. Is this value within the specified range for the IRF710PBF? 
3. Measure the characteristic $I_D$ vs. $V_{DS}$ curve for a value of $V_{GS}$ that will give you about 0.5 A in the saturation regime (see @sec:fetcharpre\.2). Plot the measurements on the same graph as your prelab predictions. Do your measurements agree qualitatively with the predictions from the data sheet?
4. Measure the relationship between $I_D$ and $V_{GS}$ for one value of $V_{DS}$. Use your measurements from @sec:fetchar\.3 and the data sheet to determine the $V_{DS}$ value so as to operate in the saturated regime. Describe how you determined the value of $V_{DS}$ to use. Plot $I_D$ vs. $V_{GS}$ on the same graph as your lab prep predictions. Do your measurements agree qualitatively with the predictions from the data sheet? If there is a difference, what could account for the discrepancy? Fit your data to obtain values for $k$ and $V_{th}$, including uncertainties. Do these match your predictions from @sec:fetcharpre\.3? Does the value for $V_{th}$ agree with your result from @sec:fetchar\.2?  

# Voltage Controlled Electromagnet

![Circuit diagram for a voltage-controlled electromagnet.](https://raw.githubusercontent.com/UCBoulder/PHYS-3330/main/lab8fig/magcircuit.png){#fig:magcircuit}

## Electromagnetic coil

1. Build, or find in the lab, a 25-turn coil (about 1 inch in diameter) made from magnet wire. Note that you will need to strip insulating varnish off the ends of the wire. You can do this with a lighter and/or sandpaper.
2. Measure the resistance of the coil using the 4-terminal measurement as you did in Lab 1 (run a large current through the wire and measure the voltage across it). Describe your procedure and measurements. HINT: The banana to alligator clips make easy connections to the coil.
3. Modify your model of the magnetic field you developed in the lab prep to include the actual number of turns and diameter of your coil.

## Electromagnet 

1. Build the circuit shown in Figure @fig:magcircuit using your coil.
2. Using the data you acquired in section @sec:fetchar, determine $V_{supply}$ and $V_{GS}$ to operate your electromagnet with 1 A of current in the saturation region. Remember to include the voltage drop across your coil in your calculations (HINT: $V_{DS} = V_{supply} ~–~ I_DR_{coil}$). To reduce the heat load on the FET, you should use the minimum $V_{supply}$ that fulfills the requirements.
3. Test out your electromagnet. Choose a way to test your model of the magnetic field produced. Explain the model you are testing and what your predictions are (even qualitative, such as how things scale).
4. Describe your procedures, results/measurements, and refinements to your model. Some starter suggestions are listed below. Be creative! You should try a few different things:
   - Measure the magnetic field as a function of distance from the plane of the loop using the Gaussmeter in lab (or a magnetometer app on your phone). You can also slide the wire loops off-center and see the dependence. 
   - Look at the force applied by a permanent magnet on the coil and see how that scales with current or number of turns.
   - By changing $V_{GS}$, you can vary the current through the coil. Measure the field strength as a function of the current. 
   - Vary the number of turns on your loop of wire and verify the dependence.
   - Slide a screwdriver (steel) or another steel rod into the coil and report what happens.
   - Check the effect of your coil on a compass and compare to the known magnetic field of the Earth. 
   - Get a power supply that can supply more current and pick up objects, test how the number or weight of objects you can pick up depends on the current. 
   - Wrap your coil around an iron core and test how the magnetic field changes, refine your model to include the iron
