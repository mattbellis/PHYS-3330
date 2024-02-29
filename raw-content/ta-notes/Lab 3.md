---
title: "TA Notes: Lab 3"
author: [Department of Physics | University of Colorado Boulder]
---

# Concepts

- This lab is pretty straight forward. Most of the struggle will be in the prelab making Bode plots

    - Encourage students to solve for the magnitude of the complex function by hand

    - For Mathematica, use `LogLogPlot[]` and not `BodePlot[]` and make sure the x-axis bounds start at 1 and not 0, i.e. {f, 1, 10000000}.

    - For Python, use `np.logspace()` instead of `np.linspace` to generate the frequency array so that the points on the graph are spaced even in log-space.

- Capacitor uses:

    - Filtering / signal processing (this lab)

    - Coupling / decoupling (We will start decoupling next week with op-amps, and coupling will come up in the first BJT lab)

    - Timing / oscillators (this will come up in the digital circuits lab, and is common to incorporate in final projects)

**Different kinds of capacitors are DIFFERENT!**

- Non-polar capacitors are named after the dielectric used:

    - Ceramic
      
        - good temperature stability

        - good at high frequency

        - low series inductance

        - great for filtering and as a second capacitor for decoupling.

        - cheap

    - Mica (natural material with large dielectric constant):

        - high voltage and high frequency applications

        - very fine tolerances and high stability

        - more expensive

    - Polyester film (Pretty sure the MMR capacitors are polyester films):

        - high stability, low cost

        - low leakage

        - large (low capacitance per volume)

        - These are supposed to be good for signal processing applications, but they seem to have issues in active filter, differentiator, and integrating circuits. This won't come up until final projects.

- Polarized capacitors are named after the metal used (the dielectric is an oxide layer of that metal) [Electrolytic Capacitors: Comprehensive Overview, Teardown, and Experiments (video)](https://youtu.be/MAP-VA1m-A4?si=TeV3Tp21oF-0MMnS)

    - They should NOT be used for this lab!

    - Electrolytic (aluminum): one of the aluminum plates is coated with an oxide layer (the dielectric) that is etched to give roughness and filled with a liquid/gel (electrolyte) and rolled into a can-like shape

        - huge capacitance per size

        - used in power circuits to decouple power

        - have significant series inductance

        - explode when they are poled wrong

        - limited lifetime

        - significant leakage current

    - Tantalum: another type of electrolytic cap that uses a tantalum bead as the anode and a tantalum oxide as the insulator.

        - very high capacitance per volume

        - conflict mineral (expensive)

        - ignite as failure mode

        - sensitive to overvoltage

- Aliasing on the scope is a common problem. 

    - If the time scale on the scope is long relative to the period of the wave (i.e. the wave is ~>1 MHz and the time scale is ~>1 ms), it will sample slow and display an aliased version of the wave. It will appear to be orders of magnitude slower than reality.
    
    - A "tell" is seeing the wave "crawl" across the screen. If the scope's trigger mode is "Auto (untriggered roll)" the display will roll the wave across the screen even if triggered for very slow waves. If you see this, make sure they know what they're looking at.

    - A great analogy is that of filming a helicopter blade or the wheels of a car and seeing, in the video, the rotor spinning slow or backward or standing still. The sample rate is too slow to capture the full wave, but it still captures SOMETHING.
      
        
      
        
