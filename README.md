# LayerLapse – 3D Printing Timelapse Trigger Device

**LayerLapse** is a camera trigger designed for 3D printers that captures a photo on every new layer using a hall effect sensor and a magnet mounted to your print head. This creates buttery smooth, layer-by-layer timelapse footage — perfect for makers, designers, and content creators. It's an awesome way to view your prints from a whole new perspective.

The official LayerLapse device is a plug-and-play solution using a compact custom PCB, built and sold by **Whopper Printing**. You can get the completed, plug-and-play [LayerLapse here.](https://whopperprinting.com/)

Each LayerLapse kit includes:

- The compact, fully assembled LayerLapse mainboard
- A dedicated magnetic hall effect sensor board
- A 3.5mm male-to-male cable (connects the mainboard to the sensor board)
- A pre-installed 2.5mm female shutter jack (connects to your camera)
- A small 5×5×2mm neodymium magnet for mounting to your print head

The board is powered via USB-C (cable **not** included by default — available as an add-on).
Camera shutter cables (2.5mm to your camera brand) are also **not** included by default, but are available as optional add-ons.

LayerLapse also comes with an extra GPIO pin for custom expansion — add a servo, LED, infrared, or other mods.

For those who prefer to build their own, a full DIY guide is included in this repository. While the DIY route is completely possible using off-the-shelf components, LayerLapse was created to save time, simplify the process, and deliver beautiful results right out of the box.

---

## 🛠️ Getting Started (Quick Setup)

1. Plug in the components:
   - Connect the 3.5mm cable between the mainboard and the sensor board
   - Plug in a USB-C power cable
   - Connect the 2.5mm shutter cable from the mainboard to your camera
2. Mount the magnet to your 3D printer's toolhead (use the included 5×5×2mm magnet).
3. Place the sensor near the printer’s parked position — ideally within ~10mm of the magnet at its closest pass.
4. Add G-code (like a custom layer change script) in your slicer to move the print head to that sensor location (e.g., G1 X0 Y200) after each layer.

Once set up, LayerLapse will automatically trigger your camera after every layer, creating smooth and consistent timelapse footage!

---

## 🎯 Features

- Triggers after each layer via a hall effect sensor + magnet
- Optional camera delay to reduce vibration blur from printer movements
- Compatible with DSLR/mirrorless cameras (2.5mm shutter trigger jack)
- Plug-and-play simplicity — just power it, mount the sensor and magnet, and go
- Fully customizable firmware — tweak timing, behavior, and logic to fit your setup
- Breakout GPIO pin for expansion — add a servo, LED, infrared, or other mods
- Open-source firmware (hardware is proprietary)
- DIY-friendly guide included for building your own version with off-the-shelf parts

---

## 🔧 Uploading Firmware (Only needed if you're customizing — LayerLapse is shipped preloaded and ready to use)

Steps:
1. Copy the code from [`code/LayerLapse_firmware.txt`](code/DIY_LayerLapse_firmware.txt)
2. Paste it into the Arduino IDE
3. Select the correct board/port and upload

---

## 🧠 Want to Build Your Own?

Sure! I've made a DIY guide so you can prototype your own version with an Arduino. Check out the DIY guide:  
👉 [`docs/diy-build-guide.md`](docs/diy-build-guide.md)

You’ll need:
- Microcontroller (like an Arduino)
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

See full list of compatibility: 
📂 [`docs/camera_compatibility.md`](docs/camera_compatibility.md)
Want to help? Submit a PR or open an issue!

---

## 🤝 Contributing

Want to improve the firmware, add camera compatibility info, or help make this project better?
Please read the [`Contributing Guidelines`](CONTRIBUTING.md) before submitting a pull request or opening an issue.

---

## 🛡️ License

The code in this repo is licensed under the **MIT License** — for firmware only.  

> 🛠️ You are welcome to build your own DIY version using Arduino components and the open firmware provided.🚫 However, the official hardware design (PCB layout, enclosure, and branding) is proprietary and not licensed for reproduction, resale, or modification.

See the full license here: [`LICENSE`](LICENSE)

---

## 💬 Support & Contact

Created by **Whopper Printing**  

For questions, feedback, or orders:  
📩 Email: whopperprinting@gmail.com  
🔗 Website: [whopperprinting.com](https://whopperprinting.com/) <- Purchase LayerLapse here!  
📷 Instagram: [@whopperprinting](https://instagram.com/whopperprinting)  
🕒 TikTok: [@whopperprinting](https://www.tiktok.com/@whopperprinting?is_from_webapp=1&sender_device=pc)
