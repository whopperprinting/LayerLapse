# DIY Build Guide (Not Complete)

This guide will help you build your own basic version of the LayerLapse timelapse trigger using off-the-shelf parts.

## 🔌 What You Need
- Microntroller (like an Arduino)
- Hall effect sensor (3-pin, e.g., A3144)
- 2.5mm camera shutter cable (compatible with your camera)
- 2.5mm female jack
- Transistor (e.g., PN2222)
- 1k Ohm resistor
- Jumper wires
- Breadboard (optional)

## 🧠 How It Works
- A magnet is affixed to the print head
- Printer's "layer change" gcode is modified to park the printer somewhere you specify, such as the back right corner of the printer
- When the printer parks in its designated location, the hall sensor detects the magnet on the parked printhead
- The Arduino waits for vibrations to settle (add a delay)
- Then it triggers the camera shutter using the transistor
- The printer then continues printing, repeating this process every layer

## 🖼️ Wiring Diagram
(Coming soon)

## 📂 Firmware
You can find the code to copy-paste here:  
[`firmware/LayerLapse_firmware.txt`](../firmware/LayerLapse_firmware.txt)

---

## 🤝 Support Me!
This DIY guide is offered freely to the maker community.  
If you'd like a compact, plug-and-play, pre-assembled version, check out the official [LayerLapse device](https://whopperprinting.com/)!
