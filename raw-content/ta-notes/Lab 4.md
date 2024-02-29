---
title: "TA Notes: Lab 4"
author: [Department of Physics | University of Colorado Boulder]
---

# Things about the LF356

- The op-amps use JFETs for the input stage so they have very high input impedance, so the current golden rule is a great approximation.

- The op-amps have an open loop gain of A=2e5, so for a closed-loop gain of 101, A is sufficiently infinite.

- The unity-gain-frequency/gain-bandwidth-product is AT LEAST 5 MHz, many op-amps will have a GBW of 6-7 MHz (and sometimes even higher). Student's really don't seem to like that it works this way. Ease their spirits by saying this is a good thing.

    - I sometimes talk about photolithography fab processes and how this isn't a perfect process. the 5 MHz quote is essentially a lower-bound on the tolerances they have for their fab process.

- The bare op-amp output impedance is about 40 ohm.

# Powering the op-amp

All powered ICs draw current through the power inputs. As the power demands change over time (i.e. the current changes), there will be a back EMF due to the inductance of the power supply! This ruins the performance of ANY powered IC. For op-amps, this will cause high frequency oscillations to occur on top of the output signal. These often are not uniform (sometimes the oscillations are larger when the voltage is more positive *or* more negative). **Look out for these high frequency oscillations** and make sure students are using decoupling capacitors correctly

- Decoupling means coupling to ground

- One way to think about it is that it's *like a low pass filter* and cuts the high frequency oscillations.

- Another way to look at it is that it provides a low impedance path to ground for anything other than DC.

- Physically, what is happening, is that the capacitor is acting as a power reservoir. Due to the power supply's inductance, it is unable to instantaneously change its power output, so the capacitor supplies extra power when the power supply dips and recharges when the power supply surges.

- 1 uF should be enough. 4.7 uF is definitely enough capacitance

- The reason the capacitor should be plugged in as close to the power pin as possible is because all lines/wires have inductance per unit length. minimizing the distance of the capacitor to the pin minimizes the inductance between the capacitor and the op-amp.

    - It is unlikely the line inductance will play a large roll in any of the circuits built in this class, so putting the capacitor anywhere *should* work just fine, but it's good to encourage this as it's a good habit in general

    - Also in general, people use both electrolytic and ceramic or mica capacitors in parallel for decoupling because aluminum capacitors have a significant ESL and the second, smaller capacitor is able to compensate for the aluminum capacitors series inductance. This won't significantly impact any of the circuits in this class, but sometimes it's worth talking about.

# Input and Output impedance

Other than familiarizing themselves with op-amps and basic operation, a main point of this lab is considering the effects of output impedance on circuits.

- The buffer, having a closed-loop gain of 1, has the smallest possible output impedance: so small that it should basically be negligible.

- The non-inverting amp with a gain of 101 has a very small output impedance, but it is large enough to see the effects of it when the load is 8 ohm (the speaker). The point of last-ish part of the lab is to use measurements of $V_\text{out}$ without a load and $V_\text{out}$ with a load to determine the output impedance. When no load is applied the current is essentially 0, so no voltage drops across the output impedance and therefore, this measure of the output is a measure of the internal $V_\text{out}$ (i.e. $V_\text{out}^\text{(internal)})$

$$\frac{V_\text{out}^\text{(external)}}{V_\text{out}^\text{(internal)}} = \frac{R_L}{R_o'+R_L}$$

- Students may struggle with this idea, remind them about the 50 ohm output impedance of the function generator and how that affects its ability to drive loads.

# Scope probes

At this point, students should be encouraged to always use the scope probe for their measurements.

- The inductance of speaker seems to cause oscillations on the low swing of the signal if you are not using the scope probe.