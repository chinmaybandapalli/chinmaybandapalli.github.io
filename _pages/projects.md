---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
redirect_from:
  - /projects
---
Discovery Project 
====
WIP

LED Peripheral for DE-10 Standard | Spring 2025
====

Problem
----

The DE-10 Standard Board layout labeled. Credit: [RocketBoards Documentation](https://www.rocketboards.org/foswiki/Documentation/DE10Standard)

In teams of 5, we had to make sure the peripheral was easy to use, had a simple API, and was compatible with a simple computer's ISA (made by the professors). We were encouraged to either create the peripheral with block diagrams or through VHDL, a hardware description language, using Intel's Quartus Prime to organize the design hierarchy. The professor gave us the barebone simple computer files (SCOMP), and we were supposed to integrate the peripheral within the existing system. Along with designing the actual peripheral, we had to create a solution proposal, log our progress through logbooks, and give a final demonstration with a custom made assembly program (following a given ISA). We had approximately 4-5 weeks to complete the peripheral, demonstration, and the other proposal assignments. While it is impossible to explain every detail of how SCOMP works in a concise matter, here is the general architecture of SCOMP (16-bit, 4 registers with RAM): 

![SCOMP](/images/SCOMP.png)

The general architectural overview of the SCOMP processor along with its interface with memory. Credit: **ECE 2031 Lab Manual**

Solution
----

We immediately started brainstorming ideas. At first, we wanted to use the LEDs to have brightness control (through PWM generation), checkpoint tracker (a specific function that allows the user to track checkpoints in their assembly code), and a loop counter, but we realized that implementing all those functionalities would be impossible to do in a month. At the end of the brainstorming process, we decided to prioritize brightness control. To summarize our API, based on the address number the programmer uses, they can control the brightness of individual or every LED on the DE-10 by inputting a standard 0-255 value to the peripheral address(es). Along with that, using a 10-bit bit mask, the programmer could toggle each LED on or off. As a last minute functionality, we also had a read function where the programmer could store a value into the LEDs and read from them whenever they choose. We felt that these four functionalities fulfilled the design challenge and was relatively easy/useful for a SCOMP programmer. I worked on coding the PWM generator (to produce the proper signal for corresponding brightness based on input value) and a gamma correction function to adjust incoming brightness value to human perception of brightness in VHDL, both of which worked properly with slight tweaks to the input clock signal. 

Below is a rough diagram of our LED Peripheral architecture:

![LED Peripheral](/images/LEDPeripheral.png)

Along with the diagram, here is a register map that explains the function of each register and address:

![Register Map](/images/RegisterMap.png)

Results
----
In the end, we managed to achieve everything we had decided upon during brainstorming. We could control each LED brightness with around 95% accuracy on the 0-255 scale, as well as a working bit-mask and read functionality to complete our API. The PWM generation worked as expected, as brightness with LEDs is dictated by the high-low cycle of the input signal, and we were able to set the brightness to any value between 0 and 255. To demonstrate all of these functionalities, we made a loading bar animation where each LED slowly increased to max brightness one by one in order. We also did a read functionality at the end of the animation to display the value held in the LEDs on the DE-10's HEX displays. Unfortunately, I lost the live demo video, but I have attached our supplementary demo presentation along with our original design proposal presentation.

<a href="/files/Presentation.pdf" download="Design_Proposal.pdf">Download Design Proposal</a>

<a href="/files/Demo.pdf" download="Demo.pdf">Download Demo</a>

