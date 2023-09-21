---
title: "Lab 4 - Operational Amplifiers (OP-Amps) I"
author: [Department of Physics | University of Colorado Boulder]
---

# Goals

In this lab, you will characterize the gain and frequency dependence of op-amp circuits, one of the most useful components in electronics. You will also measure input and output impedances of these circuits. The op-amp is the most important building block of analog electronics. As op-amps are made out of transistors, most textbooks discuss transistors first, followed by op-amps. We choose the opposite order as we are not particularly interested in how op-amps are constructed but rather how to use them in circuits and the principles of op-amps operation are actually simpler than for transistors.

Proficiency with new equipment:

-   Op-amps: Non-inverting amplifier with unity gain (voltage follower) and finite gain

Proficiency with new analysis and plotting techniques:

-   Bode plots

Modeling the physical system:

-   Frequency dependence of op-amp circuits

-   Input and output impedances of op-amp circuits

# Definitions

**Closed-loop gain, $G$** - gain of the *op-amp circuit* at all frequencies with feedback applied

**Low frequency gain, $G_{0}$** - gain of the *op-amp circuit* at DC (f = 0 Hz)

**Open-loop gain, $A$** - gain of the *op-amp itself* at all frequencies with no feedback applied

**DC gain, $A_{0}$** - gain of the *op-amp itself* at DC (f = 0 Hz) with no feedback applied

$\mathbf{f_0}$ - 3 dB frequency for an *op-amp itself* with no feedback

$\mathbf{f_B}$ - 3 dB frequency for an *op-amp circuit* with feedback applied

$\mathbf{f_T}$- unity gain frequency, frequency where the open loop gain $A$ is equal to one

# General Purpose of OP-Amps

One of the main purposes of an amplifier is to increase the voltage level of a signal while preserving as accurately as possible the original waveform. In the physical sciences, transducers are used to convert basic physical quantities into electric signals, as shown in Figure @fig:lab-measurement. An amplifier is usually needed to raise the small transducer voltage ($\mu V$ to $mV$) to a useful level ($mV$ to $V$).

![Typical laboratory measurement system](../resources/lab4fig/lab-measurement.png){#fig:lab-measurement}

Measuring and recording equipment typically requires input signals of $10~
mV$ to $10~ V$. To meet such needs, a typical laboratory amplifier might have the following characteristics:

1.  Predictable and stable gain. The magnitude of the gain is equal to the ratio of the output signal amplitude to the input signal amplitude.

2.  Linear amplitude response, so that the output signal is directly proportional to the input signal.

3.  According to the application, the frequency dependence of the gain might be a constant independent of frequency up to the highest frequency component in the input signal (wideband amplifier), or a sharply tuned resonance response if a particular frequency must be picked out.

4.  High input impedance and low output impedance are usually desirable. These characteristics minimize changes of gain when the amplifier is connected to the input transducer and to other instruments at the output.

5.  Low noise is usually important. Every amplifier adds some random noise to the signals it processes, and this noise often limits the sensitivity of an experiment.

Commercial laboratory amplifiers are readily available, but a general-purpose amplifier is expensive (\>\$1000), and most of its features might be unneeded in a given application. Often, it is preferable to design your own circuit using a cheap (\<\$1) op-amp chip. Op-amps have many other circuit applications. They can be used to make comparators, filters, limiters, rectifiers, oscillators, integrators, and other devices. We will build some of these circuits in later labs.

# OP-Amp Basics

Two basic op-amp circuit configurations, the non-inverting amplifier and the inverting amplifier, are shown in Figures @fig:non-invert and @fig:invert, respectively. Both circuits use ***negative feedback***, which means that a portion of the output signal is sent back to the negative input of the op-amp through the feedback resistor $R_F$. The op-amp itself has very high gain, but relatively poor gain stability and linearity. When negative feedback is used, the circuit gain is greatly reduced, but it becomes very stable. Also, linearity is improved, and the output impedance decreases.

![Non-inverting amplifier](../resources/lab4fig/non-invert.png){#fig:non-invert width="10cm"}

![Inverting amplifier](../resources/lab4fig/invert.png){#fig:invert width="10cm"}

Both configurations are widely used because they have different advantages. Besides the fact that the second circuit inverts the signal, the main differences are that the first circuit has much higher input impedance, while the second has lower distortion because both inputs remain very close to ground. In this lab, we will be focusing on the first-type, non-inverting.

The gain or transfer function, $A$, of the **op-amp alone** is given by

$$A\equiv\frac{V_{out}}{V_{in}^+-V_{in}^-}$$

where the denominator is the difference between the voltages applied to the + and - inputs. We use the symbol $G$ for the gain of the complete amplifier with feedback: $G = V_{out}/V_{in}$. This gain depends on the resistor divider ratio

$$B = \frac{R}{R + R_{F}}$$

If we assume an ideal situation where $A = \infty$, that the op-amp input impedance is infinite, and that the output impedance is zero, then the behavior of these circuits can be understood using the simple \"Golden Rules\":

1.  **The voltage difference between the inputs is zero. (\"voltage rule\")**

2.  **No current flows into (or out of) each input. (\"current rule\")**

The "Golden Rule" analysis is very important and is always the first step is designing op-amp circuits, so be sure you understand it before you read the material below, where we consider the effect of finite values of $A$.

## Non-inverting amplifier

The basic formula for the low frequency gain of non-inverting amplifiers is derived in Steck Section 7.3.3. Using just the Golden rules, which assumes $A\gg 1$, the gain is given by

$$G_{0} = \frac{V_{out}}{V_{in}} =\frac{R+R_F}{R} = 1 + \frac{R_{F}}{R}$$

Equations for the input and output impedance of the entire circuit are derived in H&H Section 4.26. The results are

$$R_{i}^{'} = R_{i}(1 + AB)$$ $$R_{o}^{'} = R_{o}/(1 + AB)$$

where $R_i$ and $R_o$ are the input and output impedances of the *op-amp alone*, while the primed symbols refer to the whole amplifier with feedback. These impedances will be improved from the values for the bare op-amp if $A\cdot B$ is large.

The above formulas are still correct when $A$ and/or $B$ depend on frequency. $B$ will be frequency independent if we have a resistive feedback network (in other cases that use complex impedance it may not be), but $A$ always varies with frequency. For most op-amps, including the LF356, the open loop gain varies with frequency like an RC low-pass filter:

$$A(f)=\frac{A_0}{1+j\frac{f}{f_0}}$$

The 3dB frequency, $f_0$, is usually very low, around 10 Hz. Data sheets do not usually give $f_0$ directly; instead they give the DC gain, $A_0$, and the unity gain frequency $f_T$, which is the frequency where the magnitude of the open loop gain A is equal to one. The relation between $A_0$, $f_0$, and $f_T$ is

$$f_{T} = A_{0}f_{0}$$

The frequency dependence of the closed loop gain $G$ is then given by:

$$G(f)=\frac{G_0}{1+j\frac{f}{f_B}}$$

The frequency response of the amplifier with feedback is therefore also the same as for an RC low-pass filter.

We can now derive an example of a very important general rule connecting the gain and bandwidth of feedback amplifiers. Multiplying the low frequency gain $G_0$ by the 3 dB bandwidth $f_B$ gives

$$A_0 f_0=G_0 f_B = f_T$$

In words, this very important formula says that the gain-bandwidth product, $G_0f_B$, equals the unity gain frequency, $f_T$. Thus if an op-amp has a unity gain frequency, $f_T$, of 1 MHz, it can be used to make a non-inverting amplifier with a gain of one and a bandwidth of 1 MHz, or with a gain of 10 and a bandwidth of 100 kHz, *etc.* We will consider what this means for the transfer function as a function of frequency on a Bode plot.

# Useful Readings

1.  [Steck](https://atomoptics-nas.uoregon.edu/~dsteck/teaching/electronics/electronics-notes.pdf) Sections 7.1, 7.2, 7.3.1, 7.3.3

2.  Fischer-Cripps Sections 12.2 -- 12.15

3.  Horowitz and Hill 2^nd^ Ed., Chapter 4

# Prelab

Answer the following questions using Mathematica (or similar math software) for the plots. You can use either Mathematica for the rest of the questions as well or do them by hand. **Make sure to have the Mathematica notebook for your lab section as well.**

## Properties of an op-amp

The first step in using a new component is to look up its basic characteristics. Find the following specs using the data sheet for the op-amp you will use in the lab for the rest of the semester and record in your lab notebook. Data sheets for the LF356 op-amp (same as LF156) can be found on the [Data Sheets and Instrument Manuals page](/PHYS-3330/manuals-data-sheets).

1.  Unity gain frequency, $f_T$ (same as GBW in tables)

2.  DC voltage gain, $A_0$ (same as $A_{VOL}$ in tables) **(convert to a unitless quantity)**

3.  Maximum output voltage (same as $V_O$ in tables)

4.  Maximum output positive current at 0 V for a supply voltage of ±15 V (look for a graph)

5.  Input resistance, $R_i$

## Non-inverting amplifier

1.  Calculate the values of the low frequency gain $G_0$ and bandwidth $f_B$ for the non-inverting amplifier in Figure @fig:non-invert for the following two circuits you will build in lab.

    1.  $R_F = 10 ~k\Omega$ and $R = 100 ~\Omega$

    2.  $R_F = 0$ and $R = \infty$ (this is a voltage follower)

2.  Predict the output voltage, $V_{out}$, for the non-inverting amp with $R_F = 10 ~k\Omega$ and $R = 100 ~\Omega$ with ±15 V power supply rails when

    1.  $V_{in} = 1~ mVDC$

    2.  $V_{in} = 1 ~V$ (you may find your answer to 6.1.3 useful)

3.  Create Bode plots for the open loop gain and the two closed loop gains from 6.2.1 on the same graph using Mathematica (label each curve and cover at least 1--10^8^ Hz).

4.  Estimate the input impedance of the complete amplifier circuit ($R_i^{'}$) with $R_F = 10 ~k\Omega$ and $R = 100 ~\Omega$ for 1 kHz sine waves.

5.  Estimate the output impedance of the complete amplifier circuit ($R_o^{'}$) with $R_F = 10 ~k\Omega$ and $R = 100 ~\Omega$ for 1 kHz sine waves. The nominal output impedance of the LF356 alone is $40~\Omega$. To obtain the circuit output impedance at 1 kHz, one can use this value and determine $R_o^{'}$ using the formula given above. Alternatively, one can read off the value from the top left plot on page 7 of the datasheet. This shows the output impedance for an inverting amplifier (which has the same output impedance as a non-inverting amplifier) as a function of frequency for gains of $A_v=~1,~10,~100$.

## Lab activities

1.  Read through all of the lab steps and identify the step that you think will be the most challenging.

2.  List at least one question you have about the lab activity.

# Setting Up a Basic OP-Amp Circuit

All op-amp circuits start out by making the basic power connections. Op-amps are active components, which means they need external power to function, unlike passive components such as resistors and capacitors.

![LF356 schematic and pin-out.](../resources/lab4fig/lf356.png){#fig:lf356 width="10cm"}

## General Op-amp Tips

Here are some basic steps you should always follow when working with op-amps. Read through them all (likely more than once) before you begin to build your circuit (which is covered in the next section). You can then refer back to this section at any point to remind yourself of these tips.

1.  This experiment will use both +15 V and -15 V to power the LF356 op-amp. <span style="color: red;">Make sure you **unplug** the DC supplies while wiring your op-amp (you may find it useful to plug them into their own power strip). Everyone makes mistakes in wiring-up circuits. You should always check your circuit over before applying power.</span> Figure @fig:lf356 shows a pin-out for the LF356 chip. Familiarize yourself with the layout. The following procedure will help you wire up a circuit accurately:

    1.  Draw a complete schematic in your lab notebook, including all ground and power connections, and all IC pin numbers. Try to layout your prototype so the parts are arranged in the same way as on the schematic, as far as possible.

    2.  Measure all resistor values before putting them in the circuit. Make sure you are using the correct capacitors. Some capacitors indicate the capacitance directly, but small capacitors usually just have a number where 10 = 10 pF, 102 = 10x10^2^ pF = 1 nF, 103 = 10x10^3^ = 10 nF, 104 = 10x10^4^ pF = 100 nF. Also, see the important note below about polarized capacitors.

    3.  Adhere to a color code for wires. For example:

        -    <span style="color: black;">0V (ground) Black</span>

        -    <span style="color: red;">+15V Red</span>

        -    <span style="color: blue;">-15V Blue</span>
        

2.  The op-amp chip sits across a groove in the prototyping board (see Figure @fig:pb). Before inserting a chip, ensure the pins are straight (using a needle-nose pliers or something similar). After insertion, check visually that no pin is broken or bent under the chip. To remove the chip, use a small screwdriver in the groove to pry it out or use IC pliers (which can be found on the long workbench next to the LCR meter and digital microscope).

3.  You will have less trouble with spontaneous oscillations if the circuit layout is neat and compact, in particular the feedback path should be as short as possible to reduce unwanted capacitive coupling (see Figure @fig:pb). Also, wire around the chip rather than over it.

4.  To help prevent spontaneous oscillations due to unintended coupling via the power supplies, use bypass capacitors to filter the power supply lines. A bypass capacitor between each power supply lead and ground will provide a miniature current "reservoir" that can quickly supply current when needed. This capacitor is normally in the range 1-10 µF. <span style="color: red;">Compact capacitors in this range are usually ***polarized***, meaning that one terminal must always be positive relative to the other. If you put a polarized capacitor in backwards, it will burn out.</span> You will probably hear a pop and smell something foul. Please don't do this. The negative side should have an arrow on the capacitor. Also, the positive side should have a longer lead but this is not a good identification method as the leads can (and should) be cut. Bypass capacitors should be placed close to the op-amp pins. If you are connecting the +15 V supply to ground, the negative capacitor lead is connected to ground and the positive lead is connected to +15 V. If you are connecting the -15 V supply to ground, the negative capacitor lead is connected to -15 V and the positive lead is connected to ground.

![An example circuit (not the one you will build in this lab) showing good placement of the op-amp and bypass capacitors on a protoboard. Note that short wires are used for all connections.](../resources/lab4fig/pb-example.png){#fig:pb width="10cm"}

## Building an op-amp test circuit

1.  You can save yourself some frustration by testing your op-amp chips to make sure they are not burned out. You will now build a test circuit on your protoboard to quickly check that your op-amp is functioning as expected. It will be helpful to leave this test circuit built on your protoboard to quickly check an op-amp in future weeks so keep this in mind when building it (that is, keep it compact and leave plenty of space on your protoboard for future work). Connect the op-amp as a grounded-input ***voltage follower*** with the (positive) input grounded (see Figure @fig:voltage-follower-gnd). What is the predicted voltage on pins 2, 3, 4, 6 and 7 using the Golden Rule model? Measure and record the measured voltages on these pins. If your predictions do not match your measurements check your connections to the chip to find the problem. Make sure your predictions match your measurements before going on. Once you've confirmed you have a good op-amp, you can then move the chip out of the test circuit and build the upcoming circuits elsewhere on your protoboard.

2.  If you find you have a bad chip, throw it in the trash and grab another. (In case you are wondering, the LF356 costs less than $1.)

![Schematic of a voltage follower with the input grounded](../resources/lab4fig/voltage-follower-gnd.png){#fig:voltage-follower-gnd width="10cm"}

# Voltage Follower

A voltage follower is the simplest version of a non-inverting amplifier. The voltage follower has no voltage gain ($G_0=1$), but it lets you convert a signal with high impedance (i.e. very little current) to a much lower impedance output for driving loads. The voltage follower is also often called a unity gain buffer.

![Voltage follower](../resources/lab4fig/voltage-follower.png){#fig:voltage-follower width="10cm"}

## Low frequency gain and frequency dependence of the gain

1.  The voltage follower circuit is nearly the same as the test circuit, except that now a signal enters the positive input (Figure @fig:voltage-follower). Build this now. The basic test and measurement setup is shown in Figure @fig:op-amp-test.

2.  Use the function generator to measure the low frequency gain. What frequency should you use to test the low frequency gain (i.e., what frequency should the signal be below)? Consider the gain-bandwidth product for a unity gain amplifier. What is the gain-bandwidth product for this circuit? How did you find the value? What is the predicted gain for the frequency you chose? Measure the low frequency gain $G_0$ by measuring $V_{in}$ and $V_{out}$ using the scope. Do your measurements agree with your predictions?

3.  Now vary the frequency and look for deviation from the performance of an ideal follower model. The measurement at high frequency will depend on many details of your setup and you are unlikely to find a simple RC filter type falloff. Using the 10X scope-probe, measure the gain at every decade in frequency from 10 MHz down to 10 Hz, with (as usual) a few extra points anywhere things are starting to change. Do you find any deviation from unity gain? HINT: Be sure that the output amplitude is below the level affected by the slew rate. For help, see H&H p. 192. Plot the low and high frequency data and predicted behavior on your Bode plot from your prelab. Do you find a simple fall-off as suggested by the theory for the ideal follower ($f_T=f_B$)? If so, find the 3 dB frequency. How does your measured 3 dB frequency compare to what is expected from the op-amp datasheet?

4.  If you observed ideal behavior, you're lucky! At frequencies above a few MHz, the simple model of the frequency response of the op-amp is not accurate. Once you are in this frequency range, many physical details of your circuit and breadboard can have large effects in the circuit (see notes in 7.1.4 above). You could model these effects, but a better procedure to follow is to modify the physical setup. Building reliable circuits at these frequencies typically requires careful attention to grounding and minimization of capacitive and inductive coupling between circuit elements and to ground. Printed circuit boards are much better for high-frequency applications. At lower frequencies, our model of the circuit will work much better.

![Test and measurement setup for op-amp circuits](../resources/lab4fig/op-amp-test.png){#fig:op-amp-test width="15cm"}

# Non-Inverting Amplifier

![Non-inverting amplifier](../resources/lab4fig/non-inv-amp.png){#fig:non-inv-amp width="15cm"}

## Frequency dependent gain

1.  Change the negative feedback loop in your circuit to the one shown in Figure @fig:non-inv-amp, with $R_F = 10 ~k\Omega$ and $R = 100 ~\Omega$ (or build new one elsewhere on your protoboard). Measure $R$ and $R_F$ with the DMM before inserting them into the circuit board. Predict $G_0$ and $f_B$ from these measured values and the op-amps value of $f_T$ from the data sheet. (You should be able to review your prelab work here too!)

2.  Use the function generator to measure the low frequency gain. What frequency should you use to test the low frequency gain (i.e., what frequency should the signal be below)? What is the gain-bandwidth product for this circuit? How did you find the value? What is the predicted gain for the frequency you chose? Measure the low frequency gain $G_0$ by measuring $V_{in}$ and $V_{out}$ using the scope. Do your measurements agree with your predictions?

3.  Measure the voltage saturation values for your circuit. Vary the input amplitude until you observe saturation in the output. What are the output saturation levels, $+V_{sat}$ and $–V_{sat}$? Record how you determined $V_{sat}$. Can the op-amp produce voltages that span the voltages applied (-15V to +15V) to the op-amp? The model of the op-amp you have been working with does not include saturation effects. To make sure you are working within the range where your model is valid, make sure the output amplitude is below half the saturated value.

4.  Predict the 3 dB frequency for your circuit. Include your calculations in your lab notebook. Now, determine the 3 dB frequency experimentally. Describe the procedure you followed to determine the $f_B$. Does your measurement agree with your prediction? Explicitly record what criteria you used to determine whether or not the model and measurements agree.

5.  Using the gain-bandwidth relation $G_0f_B = f_T$ and your measurements of $G_0$ and $f_B$, determine the $f_T$ for your op-amp. Does your measured value of $f_T$ agree with the one from the datasheet?

6.  Measure the frequency dependence of your circuit. Measure the gain at every decade in frequency from 1 MHz down to 10 Hz. You should record $V_{out}$ and $V_{in}$ as well as the calculated gain. Plot your gain measurements and predicted gain curve on the same plot. Where, if at all, is the simple model of the op-amp circuit not valid? Suggest possible model refinements and/or physical system refinements to get better agreement between the model predictions and measurements.

## Input/output impedances and current limit of the circuit

1.  Predict the input impedance of your non-inverting amplifier circuit, $R_i^{’}$. (Hint: You found the input impedance of the op-amp alone in your prelab.) Explain how you determined this number. If you were to increase the input impedance by placing a 1 M$\Omega$ resistor in series with the input, predict how much the output voltage will change. Hint: consider the voltage drop across the 1 M$\Omega$ resistor to get the voltage at Pin 3. Measure $V_{out}$ with and without the 1 M$\Omega$ resistor in place. It is better not to measure $V_{in}$ at the same time. Do your measurements agree with your model predictions?

2.  Predict the output impedance of your circuit, $R_o{’}$, at a frequency of 1 kHz. (HINT: See 6.2.5) Predict the output voltage based on your input voltage when your circuit is used to drive a load of 200 $\Omega$ and 8 $\Omega$. (Model as a voltage divider with the op-amp output impedance as one resistor and your load resistor as the other resistor.) Measure the output voltage $V_{out}$ for all three configurations (no load, 200 $\Omega$ load, 8 $\Omega$ load). Do the measured values agree with your model prediction? If not, can you make modifications to your model to understand the discrepancy? Hint: Consider the maximum output current of the op-amp.

