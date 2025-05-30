# DIY Build Guide

**Disclosure:** Some links below are Amazon affiliate links. As an Amazon Associate, I earn from qualifying purchases. Using these links helps support the project at no extra cost to you.

This guide will help you build your own basic version of the LayerLapse timelapse trigger using off-the-shelf parts. To get the plug & play LayerLapse, [visit my website!](https://whopperprinting.com/products/layerlapse)

## 🔌 What You Need

***Right click the links and click "open in new tab" to keep the instructions open.***

| Item | Example/Link |
|------|----------------|
| Microntroller (like an Arduino or anything else that you have) | [What I used](https://amzn.to/4ibiYyZ) |
| Hall effect sensor (3-pin, e.g., A3144) | [What I used](https://amzn.to/4ja3YCi) |
| Camera trigger (compatible with your camera) | [What I used](https://amzn.to/4hSzcg3) |
| Transistor (e.g., PN2222) | [What I used](https://amzn.to/3Y7ognG) |
| 1k Ohm resistor | [What I used](https://amzn.to/4hTAXtA) |
| Breadboard jumper wires | [What I used](https://amzn.to/3RqsenG) |
| Magnets | [What I used](https://amzn.to/4j6uLz9) |

You'll also need an AC power dummy battery (get one compatible with your camera). You'll need this for long printing sessions, so your camera doesn't die mid print.
This is [what I used](https://amzn.to/3XERjiq) for my Nikon camera.

### Optional:
| Item | Example/Link |
|------|----------------|
| Breadboard (optional) | [What I used](https://amzn.to/4292l0u) |
| 10k Ohm Potentiometer | [What I would use](https://amzn.to/4j2ZoFK) |
| 3M Double Sided Tape | [What I would use](https://amzn.to/4iLMnk6) |

# Steps

### Initial Setup
  
1. Take apart the camera trigger using a small screwdriver. The goal is to get the circuit boards by themselves. We just want the 2.5mm jack PCB from this trigger.

     <img src="https://github.com/user-attachments/assets/a660cdf3-21ae-4858-80f5-7f2e2914f32e" alt="Taking apart the camera trigger" width="250"/>

2. We can set aside the button circuit board. We will only be using the 2.5mm female jack for this project. You can cut the wires between them or unsolder them.
3. Now we have all the parts we need for this project. Onto the wiring.

### Wiring
  
  
***Note: All the pin numbers are arbitrary, but if you just want to copy and paste the code later, use the same pins.***
  
1. Connect the positive pin of the Hall sensor to the 5V pin on your Arduino
2. Connect the GND pin of the Hall sensor to the GND on the Arduino
3. Connect the OUT pin of the Hall sensor to pin 7 of the Arduino
4. Connect the GND pin from the 2.5mm female jack PCB that we just isolated  **and** the AF pin to the ***emitter*** of the transistor
5. Connect a 1k Ohm resistor to a jumper wire, and connect this to pin 5 of the Arduino
6. Connect the RLS pin from the 2.5mm jack PCB **and** the GND from the Arduino to the ***collector*** pin

Your device should look like the wiring below:

![IMG_6293](https://github.com/user-attachments/assets/2d1b112b-d509-4314-9b0c-4410fc75e854)

### 📂 Code

You are now ready to upload the code to your Arduino.
  
[You can find the code to copy-paste here.](/code/DIY_LayerLapse_firmware.txt)

## Mounting Sensor & Magnet

Everyone has different printers so this step will look different for everyone, but the main idea is the same.

### Steps

1. Affix a magnet to your print head; somewhere the sensor will be able to get close to it. ***On my Bambu Lab P1P, I placed the magnet on the bottom of the print head near the back right corner and taped it.***
2. Attach the sensor to the printer, somewhere it will be safe during printing. It needs to be right next to the magnet at its parked location. ***On my P1P, I taped the sensor to the frame on the right side near the back***

  <img src="https://github.com/user-attachments/assets/38141a6e-3dc4-42a5-a9af-9e5bb8034e29" alt="Sensor location" width="500"/>

## Custom gcode

This is the very last step of the whole build. You'll need to figure out a location to park your printhead during the timelapse. For example, I parked my P1P in the back right corner, then I taped the hall sensor to the frame right under where the magnet will be parked during the photo capture. Save this location and add this to the layer change gcode in your slicer. This is the final puzzle piece to the whole system.

### Tip: Make sure that you duplicate your existing printer profile before making modifications. This will allow you to easily switch between regular printing mode and timelapse mode with the click of a button.

[See gcode examples here.](/code/custom-gcode)

## Final Remarks

Now all thats left is to plug in your Arduino, plug in your camera to the 2.5mm jack, and get to printing!

### Tips:

- Add a new printer profile in your slicer and name this "Timelapse" or something to that effect. That way you can still print normally, but when you want a timelapse, you can just switch printer profiles.
- Set a delay in your code that is reasonable. If you take a photo right after triggering, you'll get vibrations in your timelapse.
- Make sure to set your focus wisely before starting. I reccomend placing an object where you're going to print and focus on that. You don't want to look at your timelapse in the end and see it's out of focus.
- Make sure your camera's standby time is high enough to not cause lag during the printing. I had mine set to go into standby mode after a few seconds. This caused lag between the trigger and the camera actually taking the photo, ruining timelapses until I figured out the issue. But again, every camera is different, so test out your own settings before committing to a print.
- Use an AC dummy battery for your camera. You wouldn't want your camera dying halfway through a print.

---

## 🤝 Support Me!
This DIY guide is offered freely to everyone!

Consider supporting me [on Patreon!](https://www.patreon.com/whopperprinting)

If you'd like a compact, plug-and-play, pre-assembled version, [check out the official LayerLapse device](https://whopperprinting.com/products/layerlapse)! (Releasing April 2025)
