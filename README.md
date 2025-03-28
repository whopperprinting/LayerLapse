# LayerLapse – 3D Printing Timelapse Trigger Device

**LayerLapse** is a camera trigger designed for 3D printers that triggers an external camera on each new layer using a hall effect sensor and a magnet affixed to the print head. This creates buttery smooth layer-by-layer timelapse footage — perfect for makers, designers, and content creators. It's really awesome to see your prints/designs from a different perspective!

The official LayerLapse device is a plug-and-play solution using a compact custom PCB powered by an ATtiny1604 microcontroller, built and sold by **Whopper Printing**. You can get the completed, plug-and-play [LayerLapse here.](https://whopperprinting.com/)

---

## 🎯 Features

- Triggers after each layer via a hall effect sensor + magnet
- Optional camera delay to reduce vibration blur from printer movements
- Compatible with DSLR/mirrorless cameras (2.5mm shutter trigger jack)
- Plug-and-play simplicity — just power it, mount the sensor and magnet, and go
- Open-source firmware (hardware is proprietary)
- DIY-friendly guide for makers

---

## 🔧 Uploading Firmware

Steps:
1. Copy the code from `firmware/LayerLapse_firmware.txt`
2. Paste it into the Arduino IDE
3. Select the correct board/port and upload

---

## 🧠 Want to Build Your Own?

Check out the DIY guide:  
👉 [`docs/diy-build-guide.md`](docs/diy-build-guide.md)

You’ll need:
- Microntroller (like an Arduino)
- Hall effect sensor (3-pin, e.g., A3144)
- 2.5mm camera shutter cable (compatible with your camera)
- 2.5mm female jack
- Transistor (e.g., PN2222)
- 1k Ohm resistor
- Jumper wires
- Breadboard (optional, but convenient)

Optional:
- A potentiometer for adjustable delay

---

## 📸 Camera Compatibility

Right now, only **Nikon cameras** are confirmed to work.  
I'm gathering data for Sony, Canon, Fuji, etc.

Want to help? Submit a PR or open an issue:  
📂 [`docs/camera_compatibility.md`](docs/camera_compatibility.md)

---

## 🛡️ License

The code in this repo is licensed under the **MIT License** — for firmware only.  
You are free to build your own DIY version using Arduino components and this code.

> 🚫 The **hardware design** (custom PCB, layout, enclosure, and branding) is **proprietary** and not licensed for reproduction or resale.

See the full license here: [`LICENSE`](LICENSE)

---

## 💬 Support & Contact

Created by **Whopper Printing**  
Questions or inquiries?  
📩 Email: whopperprinting@gmail.com  
🔗 Website: [whopperprinting.com](https://whopperprinting.com/) <- Purchase LayerLapse here!  
📷 Instagram: [@whopperprinting](https://instagram.com/whopperprinting)  
🕒 TikTok: [@whopperprinting](https://www.tiktok.com/@whopperprinting?is_from_webapp=1&sender_device=pc)
