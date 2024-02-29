---
title: "TA Notes: Lab 2"
author: [Department of Physics | University of Colorado Boulder]
---

# Concepts
- Ground loops. This isn't important yet, but it's good to know now. Some circuits later on sometimes are sensitive to ground loops. Student's will likely create ground loops this lab which provides an opportunity to talk to them about it, but these ground loops likely won't impact their circuits this week.

    - Encourage students to think about the physical loop they created and think about what happens when there's a change in magnetic flux through the loop.

    - [Ground Loops: Avoid Them! (video)](https://youtu.be/gBCOeYfRL5g?si=iCscT0nlSTAaGR9U)

    - [Ground Loops: Grounding Series (video)](https://youtu.be/PACur_GcTJ0?si=LdmAqiBW-2nfuqxL)

    - The breadboard's header's coax inputs connect the outer-conductor to the black banana port (labeled with chassis ground), so when the function generator or scope is plugged in to a coax on the board, the power supply's ground doesn't need to be connected to the board. In fact, doing so creates a ground loop!

- The power rail columns on the breadboard don't run all the way down the board; for some reason there's a break halfway down.

- There are fuses to the wipers of the potentiometers on the header. These sometimes don't sit right in the fuse holder. Try reseating them before replacing. Have them measure the resistance to confirm if it's broken

- Voltage divider derivation from ohm's law.

- The effects of measurement impedance on the circuit. The DMM is 10 Mohm and the scope is 1 Mohm. The scope probe adds 9 Mohm.

    - resistors in parallel 1 order of magnitude apart equals the 90% smaller resistor

    - 2 orders of magnitude: 99%

    - 3 orders of magnitude: 99.9%, etc.

# Make sure students:

- Understand that if two or more elements have the same voltage drop across them, they are in parallel.

- Understand that if two or more elements of the same current going through them, they are in series.

- Understand voltages and current measurements:

    - Voltage measurement has high impedance and is in parallel

    - Current measurement has low impedance and is in series.

- Understand that a load on the voltage divider adds resistances in parallel, and changes the total current.

- Interface with their board through the header with the power supply, scope, and function generator. It's okay if they bypass it for the DMM, but sometimes it's good to show them how to use the DMM through the header.

- Use the coax connectors on the header!

- Make sure they aren't being "creative" with adapters. They will try!
    
- Label breadboards at bottom with label maker with their names.

- See the potentiometer tear down on page 30 of Open Circuits.
