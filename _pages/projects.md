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

LED Peripheral for DE-10
====

For our final project in [Digital Design Laboratory](https://ece.gatech.edu/courses/ece2031), we had to create a peripheral to control the included LEDs on the DE-10 Standard (attached below).

![DE-10 Standard](/images/Layouttop.jpg) 

The DE-10 Standard Board layout labeled. Credit: [RocketBoards Documentation](https://www.rocketboards.org/foswiki/Documentation/DE10Standard)

In teams of 5, we had to make sure the peripheral was easy to use, had a simple API, and was compatible with a simple computer's ISA (made by the professors). We were encouraged to either create the peripheral with block diagrams or through VHDL, a hardware description language. The professor gave us the barebones simple computer files (SCOMP), and we were supposed to integrate the peripheral within the exisiting system. Along with desiging the actual peripheral, we had to create a solution proposal, log our progress through logbooks, and give a final demonstration with a custom made assembly program (following a given ISA). We had approximately 4-5 weeks to complete the peripheral, demonstration, and the other proposal assignments. While it is impossible to explain every detail of how SCOMP works in a concise matter, here is the general architecture of SCOMP (16-bit, 4 registers with RAM): 

![SCOMP

![SCOMP](

We immediately started brainstorming ideas. At first, we wanted to use the LEDs to have brightness control (through PWM generation), checkpoint tracker (a specific function that allows the user to track checkpoints in their assembly code), and a loop counter, but we realized that implementing all those functionalities would be impossible to do in a month. At the end of the brainstorming process, we decided to prioritize brightness control (individual and all together). 
