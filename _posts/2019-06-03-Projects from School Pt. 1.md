---
layout: post
title:  "Projects from School Part 1"
date:   2019-06-03 18:37:00 -0500
categories: projects
---

### CMPS 375 - Jazzberry Pi

When forming our group for our CMPS 375 class, the three of us all had a shared interest of music and we wanted to bring that unique aspect into our project. Since this project had to be hardware based, we came up with the idea of creating a drum machine, where the machine would literally play the drum itself.

Now there is a Raspberry Pi, hence the Jazzberry Pi name, but ultimately we went with a combination of an Arduino to control the hardware elements of our project, and Raspberry Pi to handle software elements.

![Image of materials](https://undeadzant.github.io/img/materials.png)

For the DrumBot Project, we started the design phase by planning out how to implement the Arduino board with an electronic circuit board. Initially we wanted two drumsticks to move up and down to strike a drum placed directly in front of the DrumBot. The Arduino board was hooked up to a breadboard that was originally hooked up to two 6 volt batteries. The batteries also powered the solenoids for controlling the drumsticks. In the initial build, we added two buttons to the Arduino board that controlled each individual drumstick (left and right).

![Image of proto](https://undeadzant.github.io/img/earlyproto.png)

During the second phase  the power source was changed to have a better current and to ensure enough power was going to each individual component. We replaced the 6 volt batteries with Alternating Current (AC) power. In addition to the power switch, an additional component, a cymbal, was implemented to add a more dynamic sound to our DrumBot. The DrumBot was also mounted to what used to be a lamp post. The hollow inside of the lamp post allowed for the running of cables throughout the DrumBot, and was sturdy enough to mount the drumsticks, the cymbal, the Arduino and accompanying electronics.

With the hardware of the arduino and the raspberry pi, we were able to create a system that responds to user input through a web-based interface. This interface was built with Python 3.4, the Flask web framework, Nanpy firmware and the Nanpy Python library, as well as Jquery and Ajax for client/server communication. All this combines to make a project with workable functionality, allowing users to easily create the beats that they wish to.

[Video of project](https://www.youtube.com/watch?v=fc5ypkFRA6A "Check the demo here!")