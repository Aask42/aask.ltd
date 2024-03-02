---
title: 'Ftc_fancy_lights'
date: 2024-03-01T20:49:17-06:00
draft: false
github_link: "https://github.com/aask42/ftc_fancy_lights"
image: /images/money_shot.png
---

# Illuminating Productivity: My Journey with FTC Fancy Lights

Hey there [First Tech Challenge](https://firstinspires.org) enthusiasts! For the past month I've been hyperfocusing on building this special project for FTC Iowa/Nebraska's Championship at the XTreme Arena in Coralville Iowa. Presenting: The "FTC Fancy Lights"! These aren't just any ordinary lights; they're a blend of art, technology, and a bit of magic. Let me take you through the captivating world of my 8-sided infinity mirror creation, where every reflection tells a story of innovation and creativity.   

### Inspiration

I made these lights to give to the 9 Jackson Pollock League finalist for the 2024 FTC CENTERSTAGE season State Championship in Iowa City, Iowa. There are 10 in the set of nine infinity mirrors, and there are going be detailed build instructions and a build video posted at a later date I'm not committed to yet. 

There are also FOUR custom "Pixel" shaped TOKENS that are being given to the 4 teams who advance to the next stage of the competition in Texas. These were given out to the winning teams at the same event mentioned above. If you received one of these tokens, make sure to check out the code on board as there is a special message to you from me!

### Heads up

FYI: Approx 50% of this article was written by GPT 4.0 from OpenAI because I didn't have time to do it before the event with all you lovely INSPIRING students. I used the linked repository along with a prompt engineered with the source code for the mirrors in order to pull this off.

## WHAT DO THE COLORS MEAN!!!

| Indicator                | Description                                  |
|--------------------------|----------------------------------------------|
| Red Honk x3              | Issues connecting to wifi                    |
| Green Honk x3            | Wifi connected                               |
| Purple Honk x1           | MQTT connecting                              |
| Second Green Honk x3     | MQTT Connected                               |
| Red Honk x3 after first Green Honk | Wifi connected, MQTT failed        |
| Spinning chase animation | Idle, no internet connection                 |
| Bouncing chase animation | Connected to MQTT server and receiving clock pulse |

## SKIP TO THE GOOD PART, I WANT TO BUILD MY OWN

Hold on there partner, this is a 5/10 difficulty task, with some aspects being a 6/10 difficulty (mainly the soldering to split the LED strip) and some that require a laser cutter to fully realize the precision of OpenSCAD. If you are so inclined and don't want to wait for the full writeup, you can find the files you need in [our repository](https://github.com/Aask42/ftc_fancy_lights/blob/main/ftc_fancy_lights). 

## Where do I get the code IE Important Files?

What do you need to get going if you want to build your own?

- The housing files are here, but it's missing some stuff right now so you will have to know a little scad to add your own flare
  - https://github.com/Aask42/ftc_fancy_lights/blob/main/renderings/box_for_mirror.152.5.scad
- The files you need for your MicroPython instance
  - NOTE: [YOU MUST USE THE PIMORINI FLAVOR OF MICROPYTHON FOR THIS ALL TO WORK](https://github.com/pimoroni/pimoroni-pico/releases)
  - NOTE: You MUST add the umqtt library to your pico, you can add this using Thonny's library manager
  - https://github.com/Aask42/ftc_fancy_lights/blob/main/ftc_fancy_lights
  - You MUST have the CONFIG folder set up with MQTT_CONFIG.py and WIFI_CONFIG.py. 
    - MAKE SURE TO RENAME YOUR TEMPLATES
  - You MUST have the following files: 
    - main.py
    - updates.py
    - helper.py
    - umqtt/*
      - Install using the thonny library manager and pull it out of the lib folder
    - CONFIG/*_CONFIG.py
      - There are 6 files in here you need

## Project Overview

### **Design and Structure**: 

At the heart of this project is an 8-sided infinity mirror, meticulously crafted using PLA and designed with OpenSCAD. The geometric symmetry and precision reflect my commitment to both aesthetics and functionality.
- The structure combines artistic design with precision engineering, achieved through the versatility of OpenSCAD

### **Lighting Up the Scene**: 

What makes FTC Fancy Lights truly shine are the 144 WS2812 LEDs. Arranged over two 0.5-meter loops, these LEDs are more than just sources of light; they're the canvas where I paint my tech-inspired dreams.
- Each LED loop is carefully programmed to create mesmerizing lighting effects, providing a dynamic visual experience

### **The Brain Behind the Beauty**: 

Powering this intricate setup is the RP2040 Pico W. I chose this for its reliability and versatility, especially when working with MicroPython – a language that's close to my coder's heart.
- The RP2040 Pico W, running MicroPython, provides a stable and flexible platform for controlling the LEDs and managing the device's functionality

### **Connectivity and Control**: 

This project isn't just about static beauty. It's interactive, thanks to its connection to a pair of webservers. These servers enable MQTT subscription triggers, allowing the mirror to respond to various inputs and events in real-time.
- The device connects to MQTT servers for real-time interaction and control. It can respond to different triggers and display various animations based on the received MQTT messages
- THIS MEANS WE HAVE A FULL SYNCED NETWORK OF LIGHTS!

### **Seamless Updates and Integration**: 

The integration with an OTA (Over-The-Air) server ensures that FTC Fancy Lights is always up-to-date with the latest features and fixes, all running on the same architectural Docker host.

- OTA updates are implemented for easy maintenance and feature upgrades, ensuring that the device remains current and versatile

## Technical Highlights

### **OpenSCAD Design**: 

The freedom and precision of OpenSCAD played a crucial role in the design process, allowing for customization down to the smallest detail.
- The design process involved detailed customization and precision modeling to create the unique 8-sided structure
![Picture of OpenSCAD interface](/images/image_97.png)

### **MicroPython Magic**: 

Utilizing MicroPython on the RP2040 Pico W not only provided a stable platform but also allowed for easy coding and quick iterations.
- The use of MicroPython facilitated efficient coding and rapid development, making it easier to implement and test various features
![alt text](/images/image_98.png)

### **Webserver Interactivity**: 

The dual webserver setup for MQTT and OTA updates exemplifies the project's focus on interactivity and seamless user experience.
- The MQTT server allows for real-time interaction, while the OTA server provides a mechanism for seamless updates, enhancing the overall user experience
- This is currently configured to go to my MQTT broker at aask.services and enables us to trigger interruptable light shows using other triggers!
- We also can trigger the devices to pull updates over the network! (UNDER CONSTRUCTION, NOT FULLY FUNCTIONAL YET)

## Conclusion (for now?)

Stay tuned for a detailed walkthrough of the FTC Fancy Lights, where technology meets creativity!  

THANK YOU FOR STOPPING BY  

AND ESPECIALLY THANK YOU FOR THE INSPIRATION  

AND YOUR GRACIOUS PROFESSIONALISM!  

YOU ARE TRULY MY MUSE!   

AND...  
AND...  
AND...  

<3

-Amelia-
