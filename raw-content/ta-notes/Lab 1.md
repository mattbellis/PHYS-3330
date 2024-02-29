---
title: "TA Notes: Lab 1"
author: [Department of Physics | University of Colorado Boulder]
---

# Establish office hours 
- Each TA should hold 1 hour per lab section

- Go to https://classes.colorado.edu and find all upper division physics class times (EM, QM, Thermo, etc.)

    - Find times that best avoid conflicts with them

    - Stagger times if that's not possible (i.e. not the same time on MWF)

- DON'T OVERLAP WITH JLAB LECTURES!

# Important Concepts
- The DMM, function generator, power supply, and oscilloscope.

    - Read through lab guide and play with equipment

- Four terminal resistance measurement
    - Apply fixed current through two wires

    - Measure voltage across resistor with other two wires
    
    - This not only bypasses lead resistance, but contact resistance too!

- Grounding: "ground" is an often ambiguous term and as the TA it's important to understand grounding in detail.
    
    - Ground often is used to mean a part of the circuit to reference all voltages from (common ground: triangle symbol). People often use earth ground symbols (shrinking parallel lines) when they really mean common ground.
    
    - Know the difference between common ground, chassis ground, and earth ground!
    
        - [Types of Ground (article)](https://www.thegeekpub.com/274501/types-of-grounds-earth-ground-chassis-ground-signal-ground/)

        - [Effective Chassis Grounding Techniques (article)](https://resources.pcb.cadence.com/blog/2021-effective-chassis-grounding-techniques)
    
        - [Ground Wire Explained (video)](https://youtu.be/JBpQ9Fodz_Q?si=t7gFk7pHy3_0dCOT)
    
        - [Electrical Grounding Explained (video)](https://youtu.be/YO-Dnk6ZKrI?si=3q3_XweCBmKLbvTN)
    
    - The power supply has the ground terminal labeled **chassis ground**, but if plugged into a wall socket properly, this connects to Earth ground as well (so it's both). The function generator's coax outputs are also Earth AND chassis grounded.
        -  Therefore, all circuits that are using the function generator or power supply have a connection to Earth ground, and the Earth ground symbol should be used!

- Constant voltage vs constant current

    - [Understanding Constant Voltage & Constant Current (article)](https://www.rohde-schwarz.com/us/products/test-and-measurement/essentials-test-equipment/dc-power-supplies/understanding-constant-voltage-current-_256008.html)

- 10x probe: why and what?

    - Student's won't use them the first week, but as the TA, understanding the 10x probe's nature is important with regards to why the oscilloscope defaults to 10x mode.

    - [Understanding passive probes](https://youtu.be/fj1o2CQEVwU?si=ND-0b23QeolG_EU8)

    - Scope's default is 10x mode which compensates for the 10x attenuation from the 10x probe

    - The probe is 9 M and the measurement impedance is 1 M, so the transfer function is 1/10th.

    - Pressing "Default Setup" is a great way to reset the scope's memory and can solve a lot of problems. This however will set all 4 settings to 10x mode.

    - Encourage students to look out for factor of 10 errors!


- Impedance matching isn't exactly relevant to the course, and students don't need to come out understanding it, but as the TA, it is important to understand it to rationalize the design of the function generator at the very least (and to be able to answer questions students may have about impedance matching)

    - The short of it is: mismatched impedances reflect waves because of the "step function" in the potential. This is not a concern in this class because of the low-ish frequencies and compact signal lines.

    - [Impedance Matching (article)](https://www.electronicdesign.com/technologies/communications/article/21796367/back-to-basics-impedance-matching-part-1)

- Function generator ALWAYS has a 50 ohm output impedance.
    
    - By default (every time you turn it on), it assumes you are impedance matching with a 50 ohm load. The display will report the assumed voltage across the 50 ohm load (half of what is actually being applied).

    - Student's will ALWAYS have to set the output mode to High Z (assumes a load much larger than 50 ohm), which will report the full voltage being applied.

    - For smaller loads, the voltage at the output won't match the applied voltage due to the voltage divider between the load and the output impedance. It is important for students to be able to predict the voltage measured at the output based on this voltage divider (but not the first week)

- Ohms law and Kircchoff's laws

    - Voltage drops across resistors if trace direction matches current direction choice. Voltage rises across resistors if trace path opposes current direction choice.

    - Conservation of current at junctions

    - Circuit diagrams that don't complete the loop..

        - If the trace doesn't return to the voltage source (full loop), then the equation equals the voltage at the node you stopped at    (instead of zero)

- How energy in circuits actually works (it's not current and voltage). Sometimes it will be helpful to make students think about the fact that circuits are "boundary conditions" for Maxwell's equations, and that the "physics" is really happening in the air/free-space around the metal of the circuit.
    - [The Big Misconception About Electricity (video)](https://youtu.be/bHIhgxav9LY?si=PAYfhB5u1yIarm39)
    - [How Electricity Actually Works (video follow-up)](https://youtu.be/oI_X2cMHNe0?si=j53cqsiBzfbFlzlv)
    - [How Right IS Veritasium?! Don't Electrons Push Each Other?? (video response)](https://www.youtube.com/watch?v=O-WCZ8PkrK0)

# Preteach

- **Make sure students *unofficially* become aware that Horowitz and Hill 2nd and 3rd Ed PDFs are available online**
    
    - Google: "Art of Electronics PDF"

- Ohms law V=IR (write it on the board)

# Things to look out for

- Make sure students are using the banana to BNC adapter with the right orientation.

    - There's a tab labeled "GND" which routes to the outer conductor of the coax.

    - Incorrect orientation will lead to minus sign errors.

- Make sure they use wire from the spools to ground the terminals of the power supply, and not banana cables. This will ensure a tidier work space later on.

- Make sure they are using a short coax instead of a coupler between DMM and the mini-grabbers, this makes it easier on them...

- Look out for students "jerry-rigging" connections in strange ways (like using minigrabbers to grab onto banana plugs) and encourage them to make more appropriate connections.

## At the end of lab

- Except for last section of the week, remove the grounding wires from the power supplies so that the next lab has the chance to do it themselves!

