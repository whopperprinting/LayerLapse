# LayerLapse – 3D Printing Timelapse Trigger Device

**LayerLapse** is a camera trigger built for 3D printing that captures a photo on every new layer using a hall effect sensor and a small magnet mounted to your print head. It creates buttery-smooth, layer-by-layer timelapse footage — perfect for makers, designers, content creators, or anyone who wants to see their prints from a fresh new perspective.

👉 [Timelapse taken with LayerLapse](https://www.instagram.com/reel/DHZqo8mtuyH/?utm_source=ig_web_button_share_sheet&igsh=MzRlODBiNWFlZA==)

The LayerLapse system is completely independent electronically from your printer; nothing actually plugs into the printer. It requires no printer firmware modifications, soldering, or programming, nor does it make physical contact with any moving parts — meaning no unnecessary wear and tear on your printer (like a physical limit switch would cause.) You simply add a few lines of gcode in your slicer, and LayerLapse simply listens for the magnet and triggers your camera accordingly. A built-in dial lets you adjust the delay between magnet detection and photo capture (0–5 seconds, alterable), allowing your printer time to settle and eliminating blur caused by vibrations or motion that would otherwise show up on the final timelapse.

The official LayerLapse device is a plug-and-play solution using a compact custom PCB, designed, built, and sold by **Whopper Printing**. You can get the completed, plug-and-play [LayerLapse kit here.](https://whopperprinting.com/) (Releasing April 2025)

### Printer Agnostic

LayerLapse is completely printer-agnostic — from an Ender 3 to an X1C!
It works with virtually any 3D printer as long as you can mount the sensor somewhere near the toolhead and add a simple line of G-code in your slicer to pause the head briefly after each layer. I've included a [STEP file of the sensor board](docs/HallSensorTest.step) so you can fit test it on your setup to ensure it works for you before purchasing. Just print it out to test! I'm also including the STEP files so you can create your own enclosures and mounting brackets for any printer that you may have. (Coming soon)

### Camera Compatibility

**The [camera compatibility list](docs/camera_compatibility.md) is a work in progress.** So far, I can only confirm the cameras on this list work with 100% certainty, but theoretically it should work with any camera given one end is a 2.5mm jack. I am still gathering more information. LayerLapse does come with a spare GPIO pin, so if you did happen to have issues, you could theoretically make it work with some creativity.

### Each LayerLapse kit includes:

- The compact, fully assembled LayerLapse mainboard
- A dedicated magnetic hall effect sensor board
- A 1 foot long, 3.5mm male-to-male cable (connects the mainboard to the sensor board)
- A small 5×5×2mm neodymium magnet for mounting to your print head

### Not Included (can be added soon):
- The board is powered via USB-C (cable **not** included by default — available as an add-on soon)
- Camera shutter cables (2.5mm to your camera brand) are also **not** included by default, but will be available as optional add-ons soon

### Modifying the Board:

LayerLapse ships pre-programmed and ready to use, but if you'd like to upload custom firmware, you absolutely can! The board includes a 4-pin header for easy programming — three pins for flashing (VCC, GND, UPDI) and one extra GPIO pin for custom expansion. **You will need a UPDI programmer.**

The extra GPIO pin opens the door for creative mods: add a servo, LED, infrared module, or anything else you'd like to trigger on each layer change, provided your add-on is able to be adequately powered by 5V. For example, you could attach a servo to physically press a remote shutter — making LayerLapse compatible with virtually any camera system, even those without a shutter jack.

> #### **Note:** You'll need a UPDI programmer (3-pin: GND, VCC, UPDI) to upload custom firmware.

## DIY Option:

For those who prefer to build their own timelapse device, I have written a [full DIY guide](docs/diy-build-guide.md). While the DIY route is completely possible using off-the-shelf components, **LayerLapse was created to save time, simplify the process, and deliver beautiful results right out of the box.** No soldering, wiring, or programming.

---

## 🛠️ Getting Started (Quick Setup)

1. Plug in the components:
   - Connect the 3.5mm cable between the mainboard and the sensor board
   - Plug in a USB-C power cable
   - Connect the 2.5mm shutter cable from the mainboard to your camera
2. Mount the magnet to your 3D printer's toolhead (use the included 5×5×2mm magnet or use your own.)
3. Place the sensor near the printer’s parked position (that you choose in gcode) — ideally within ~10mm of the magnet at its closest pass so the sensor can pickup the magnet.
4. Add G-code (like a custom layer change script) in your slicer to move the print head to that sensor location (e.g., G1 X0 Y200) after each layer. [Custom gcode available here.](code/custom-gcode)

Once set up, LayerLapse will automatically trigger your camera after every layer, creating smooth and consistent timelapse footage!

### ✨ Tips:

- Set a delay that is reasonable. If you take a photo right after triggering, you'll get vibrations in your timelapse.
- Make sure to set your focus wisely before starting. I reccomend placing an object where you're going to print and focus on that. You don't want to look at your timelapse in the end and see it's out of focus.
- Make sure your camera's standby time is high enough to not cause lag during the capture. I had my camera set to go into standby mode after a few seconds. This caused a lag between the trigger and the camera actually taking the photo, ruining timelapses until I figured out the issue. But again, every camera is different.
- Use an AC dummy battery for your camera. You wouldn't want your camera dying halfway through a print.

---

## 🧩 Custom Mounts/Enclosures

I am working on making custom brackets to easily attach the sensors to my printers. My hope is that others will post their mounts as well for their own setups and printers. I am also working on an enclosure for the LayerLapse device, but I will also be uploading the final STEP file for the board so anyone can design their own enclosure!

---

## 🔧 Uploading Firmware (Only needed if you're customizing — LayerLapse is shipped preloaded and ready to use from the box)

Steps:
1. Copy the [code from here](code/DIY_LayerLapse_firmware.txt) for a starting point
2. Paste it into the Arduino IDE
3. Connect your UPDI programmer to the board (3-pin: GND, VCC, UPDI)
4. Select the correct board/port and upload

---

## 🎯 Features

- Triggers a camera after each layer using a hall effect sensor + magnet
- Adjustable camera delay (0–5 seconds) to eliminate blur from printer vibrations
- Compatible with DSLR and mirrorless cameras using 2.5mm shutter jacks
- Plug-and-play — no firmware mods, no printer connection, no hassle
- Compact, custom PCB with a built-in dial and pre-installed shutter jack
- Extra GPIO pin for expansion — add a servo, LED, IR module, etc.
- Open-source firmware — customize timing, logic, or camera behavior if desired
- Optional DIY guide included for building your own version from scratch

---

## 🧠 Want to Build Your Own?

Awesome! I want everyone of all skills to enjoy their own timelapses! I've made a DIY guide with a list of materials so you can prototype your own version with an Arduino. [Check out the DIY guide!](docs/diy-build-guide.md)  
  
---

## 🤝 Contributing

Want to improve the firmware, add camera compatibility info, or help make this project better?
Please read the [contributing guidelines](CONTRIBUTING.md) before submitting a pull request or opening an issue.

---

## 🛡️ License

The code in this repo is licensed under the **MIT License** — for firmware only.  

> 🛠️ You are welcome to build your own DIY version using Arduino components and the open firmware provided.🚫 However, the PCB and branding are not licensed for reproduction or resale.

[Click to view full license](LICENSE)

---

## 💬 Support & Contact

Created by **Whopper Printing**  

For questions, feedback, or orders:  
📩 Email: whopperprinting@gmail.com  
🔗 Website: [whopperprinting.com](https://whopperprinting.com/) <- Purchase LayerLapse here!  
📷 Instagram: [@whopperprinting](https://instagram.com/whopperprinting)  
🕒 TikTok: [@whopperprinting](https://www.tiktok.com/@whopperprinting?is_from_webapp=1&sender_device=pc)

**LayerLapse™ and Whopper Printing™ are trademarks of Whopper Printing. All rights reserved.**
