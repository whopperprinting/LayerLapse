# DIY Build Guide

**Disclosure:** Some links below are Amazon affiliate links. As an Amazon Associate, I earn from qualifying purchases. Using these links helps support the project at no extra cost to you.

This guide will help you build your own basic version of the LayerLapse timelapse trigger using off-the-shelf parts.

## 🔌 What You Need

| Item | Example/Link |
|------|----------------|
| Microntroller (like an Arduino or anything else that you have) | [What I used](https://amzn.to/4ibiYyZ) |
| Hall effect sensor (3-pin, e.g., A3144) | [What I used](https://amzn.to/4ja3YCi) |
| Camera trigger (compatible with your camera) | [What I used](https://amzn.to/4hSzcg3) |
| Transistor (e.g., PN2222) | [What I used](https://amzn.to/3Y7ognG) |
| 1k Ohm resistor | [What I used](https://amzn.to/4hTAXtA) |
| Breadboard jumper wires | [What I used](https://amzn.to/3RqsenG) |
| Magnets | [What I used](https://amzn.to/4j6uLz9) |
| Breadboard (optional) | [What I used](https://amzn.to/4292l0u) |

### Optional:
| Item | Example/Link |
|------|----------------|
| 10k Ohm Potentiometer | [What I would use](https://amzn.to/4j2ZoFK) |
| 3M Double Sided Tape | [What I would use](https://amzn.to/4iLMnk6) |

## 🧠 How It Works
- A magnet is affixed to the print head
- Printer's "layer change" gcode is modified to park the printer somewhere you specify, such as the back right corner of the printer
- When the printer parks in its designated location, the hall sensor detects the magnet on the parked printhead
- The Arduino waits for vibrations to settle (add a delay)
- The camera shutter is triggered using the transistor
- The printer then continues printing, repeating this process every layer

# Steps

### Initial Setup

1. Take apart the camera trigger using a small screwdriver. The goal is to get the circuit boards by themselves.

     <img src="https://github.com/user-attachments/assets/a660cdf3-21ae-4858-80f5-7f2e2914f32e" alt="Taking apart the camera trigger" width="250"/>

2. We can set aside the button circuit board. We will only be using the 2.5mm female jack for this project. You can cut the wires between them or unsolder the wires.
3. Now we have all the parts we need for this project.

### Wiring

***Note: All the pin numbers are arbitrary, but if you just want to copy and paste the code later, use the same pins.***

1. Connect the positive pin of the Hall sensor to the 5V pin on your Arduino
2. Connect the GND pin of the Hall sensor to the GND on the Arduino
3. Connect the OUT pin of the Hall sensor to pin 7
4. Connect the GND pin from the camera remote PCB and the AF pin to the ***emitter*** of the transistor
5. Connect a 1k Ohm resistor to the a jumper wire, and connect this to pin 5
6. Connect the RLS pin and the GND from the Arduino to the ***collector*** pin

Your device should look like the wiring below:

![IMG_6293](https://github.com/user-attachments/assets/2d1b112b-d509-4314-9b0c-4410fc75e854)

## 📂 Code

You are now ready to upload the code to your Arduino.
  
[You can find the code to copy-paste here.](/code/DIY_LayerLapse_firmware.txt)

---

## 🤝 Support Me!
This DIY guide is offered freely to the maker community.  
If you'd like a compact, plug-and-play, pre-assembled version, check out the official LayerLapse device!
