---
title: "TA Notes: Lab 5"
author: [Department of Physics | University of Colorado Boulder]
---

# Concepts

This lab has two main focuses:

1. Adjusting models to more accurately represent the physical system and adjusting physical systems to more accurately represent the model

    - This is mostly exemplified by the choice of resistors for the inverting amp. Lower resistances (R = 50 ohm) cause the output of the function generator to voltage divide over the 50 ohm output impedance, so the measured $V_\text{in}$ by the scope will be 2/3 of the desired input voltage. Therefore the output will be 2/3 of the prediction.
    
    - You can make a more sophisticated model to account for this (can also think about R=(50+100) ohm, so the gain is smaller)... but we want to encourage students to just design a better amplifier (use a higher value for R)

2. LOTS OF APPLICATIONS

    - emphasize how ***cool*** the circuits they're building are!
    
    - The DAC can be expanded with more inputs to get more precision. It's range can also be adjusted (i.e. it doesn't have to output integer values, it can output 7 voltages between 0 and 500 mV)

    - The integrator and the differentiator can be used for control loops (PID) and to solve differential equations.. solving differential equations means modeling physical systems. YOU CAN MODEL PHYSICS WITH CIRCUITS (analog computing)!

# DC Offset

There is a DC offset introduced that is inherent to the input bias current. I highly recommend NOT just encouraging them to use AC coupling to brush it under the rug. Let them see it and understand that it's real.

- It is not necessary to have them eliminate the DC offset, but it can be done by adding a compensation resistor $R_c$ between $V_+$ and ground with a resistance of

$$\frac{1}{R_c} = \frac{1}{R_F} + \frac{1}{R}$$

- You can read more about this in H&H 2nd ed p194-195.

- The DC offset is partially to blame for integrator drift. Integrating a constant offset results in a constant increase (or negative increase in this case) of $V_\text{out}$.

    - The voltage across the cap is $V_\text{out}$ (since the other end is virtual ground), so $V_\text{out}$ *represents* the charge accumulated on the cap. The drift in voltage is an accumulation of charge. To remove the DC offset, add a resistor in parallel with the capacitor to allow a path to discharge excess charge.

    - The value of the resistance should be large enough such that $Z_c(f) \ll R$ but small enough to allow discharge (1 Mohm is typically good, but sometimes you need a little smaller).

    - guide students through this thought process. Start with "what is integration?" They will likely say "area under the curve". This isn't wrong, but the answer you're looking for is "adding up little bits" (and in this case it's adding up bits of voltage over time).

    - A quick check while discussing these things with students is to short the cap with your finger. This should be close enough to the right impedance in parallel to mostly remove the offset.

# Precision

Students should be able to get within ~1 ohm of their predicted resistances for the DAC with 1-2 resistors from the bins. Students will likely ask how precise they need to be. There is no right answer here. Guide students through a thought process of designing something to a predefined tolerance. Most students will be happy to be sloppy with precision and will be happy to grab a few resistors close to the right value with a bit of error. For students who want to make a nice DAC, you can encourage them to use trim pots to tune the DAC.

# The Differentiator

This is a short section, but there's some cool stuff going on to have student's think about. Some of the input waves have discontinuous derivatives. How should that manifest itself in a physical system where infinities don't exist?
