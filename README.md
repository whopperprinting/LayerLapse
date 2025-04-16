# LayerLapse – 3D Printing Timelapse Trigger Device

![art_layerlapse-editedv3](https://github.com/user-attachments/assets/2097b3df-e72d-49cb-b7d9-a4a1cb618153)

### What is LayerLapse?

**LayerLapse** is a camera trigger designed specifically for 3D printing. It captures a photo on every new layer using a hall effect sensor (magnet sensor) and a small magnet mounted to your print head — producing buttery-smooth, layer-by-layer timelapse footage. Perfect for makers, designers, content creators, or people who just want to see their prints from a new perspective.

The official LayerLapse device is a plug-and-play solution using a compact custom PCB designed, hand-built, and sold by me, **Whopper Printing**!
You can get the completed, plug-and-play:  
  
👉 [LayerLapse kit here.](https://whopperprinting.com/products/layerlapse)
  
📷 [Timelapse taken with LayerLapse](https://www.instagram.com/reel/DHZqo8mtuyH/?utm_source=ig_web_button_share_sheet&igsh=MzRlODBiNWFlZA==)

### Plug & Play

The LayerLapse system is completely independent electronically from your printer; nothing actually plugs into the printer. It requires no printer firmware modifications, soldering, or programming, nor does it make physical contact with any moving parts — meaning no unnecessary wear and tear on your printer (like a physical contact limit switch would cause.) You simply add a few lines of gcode in your slicer, and LayerLapse simply listens for the magnet and triggers your camera accordingly. A built-in dial lets you adjust the delay between magnet detection and photo capture (0–3 seconds, alterable), allowing your printer time to settle and eliminating blur caused by vibrations or motion that would otherwise show up on the final timelapse.

### Works With Any Printer

LayerLapse is completely printer-agnostic — from an Ender 3 to an X1C! You're not locked down to an ecosystem!
It works with virtually any 3D printer as long as you can mount the sensor somewhere near the toolhead and add a simple line of G-code in your slicer. I've included a [STEP file of the sensor board](docs/HallSensorTest.step) so you can fit test it on your setup to ensure it works for you before purchasing. Just print it out to test! I'm also including the STEP files so you can create your own enclosures and mounting brackets for any printer that you may have. (Coming soon)

### Camera Compatibility

**The [camera compatibility list](docs/camera_compatibility.md) is a work in progress.** I am still gathering more information. However, LayerLapse does come with a spare GPIO pin, so if you did happen to have issues, you could theoretically make it work with some creativity.

For example, the GPIO pin can control a bluetooth remote for mobile phones! Tutorial coming soon.

### Each LayerLapse kit includes:

- The compact, fully assembled LayerLapse mainboard
- A dedicated magnetic Hall effect sensor board
- 1 foot long, 3.5mm male-to-male sensor cable (3 foot long cable available as an add-on)
- A small 5×5×2mm neodymium magnet for mounting to your print head (can use your own)

### Not Included (can be added soon):
- The board is powered via USB-C (cable **not** included by default — available as an add-on soon)
- Camera shutter cables (2.5mm to your camera brand) are also **not** included by default, but will be available as optional add-ons soon

### Modifying the Board:

LayerLapse ships pre-programmed and ready to use, but if you'd like to upload custom firmware, you absolutely can! The board includes a 4-pin header for easy programming — three pins for flashing (VCC, GND, UPDI) and one extra GPIO pin for custom expansion. **You will need a UPDI programmer.**

The extra GPIO pin opens the door for creative mods: add a servo, LED, infrared module, or anything else you'd like to trigger on each layer change, provided your add-on is able to be adequately powered by 5V. For example, you could attach a servo to physically press a remote shutter — making LayerLapse compatible with virtually any camera system, even those without a shutter jack. [See pinout documentation.](docs/pinout.md)

> #### **Note:** You'll need a UPDI programmer (3-pin: GND, VCC, UPDI) to upload custom firmware.

---

## 🛠️ Getting Started (Quick Setup)

1. Plug in the components:
   - Connect the 3.5mm cable between the mainboard and the sensor board
   - Plug in a USB-C power cable
   - Connect the 2.5mm shutter cable from the mainboard to your camera
2. Mount the magnet to your 3D printer's toolhead (use the included 5×5×2mm magnet or use your own.)
3. Place the sensor near the printer’s parked position (that you choose in gcode) — ideally within ~10mm of the magnet at its closest pass so the sensor can pickup the magnet.
4. Duplicate your existing printer profile so you don't mess up your regular prints. This way, with the click of a button, you can change your printer from regular mode to timelapse mode and back.
5. Add G-code (like a custom layer change script) in your slicer to move the print head to that sensor location (e.g., G1 X0 Y200) after each layer. [Custom gcode available here.](code/custom-gcode)

Once set up, LayerLapse will automatically trigger your camera after every layer, creating smooth and consistent timelapse footage!

Go to the [Quick Setup page](docs/quick-setup.md) for detailed instructions on setup.

### ✨ Tips:

- Set a delay that is reasonable. If you take a photo right after triggering, you'll get vibrations in your timelapse.
- Make sure to set your focus wisely before starting. I recommend placing an object where you're going to print and focus on that. You don't want to look at your timelapse in the end and see it's out of focus.
- Make sure your camera's standby time is high enough to not cause lag during the capture. I had my camera set to go into standby mode after a few seconds. This caused a lag between the trigger and the camera actually taking the photo, ruining timelapses until I figured out the issue. But again, every camera is different, so test out your own settings before committing to a print.
- Use an AC dummy battery for your camera. You wouldn't want your camera dying halfway through a print.

---

## 🧩 Custom Mounts/Enclosures

[3D Files](docs/3D-files)
  
I am working on making custom brackets to easily attach the sensors to my printers. My hope is that others will post their mounts as well for their own setups and printers. I am also working on an enclosure for the LayerLapse device, but I will also be uploading the final STEP file for the board so anyone can design their own enclosure!

---

## 🔧 Uploading Firmware (Only needed if you're customizing — LayerLapse is shipped preloaded and ready to use from the box)

Steps:
1. Copy the [code from here](code/DIY_LayerLapse_firmware.txt) for a starting point
2. Paste it into the Arduino IDE
3. Connect your UPDI programmer to the board (3-pin: GND, VCC, UPDI)
4. Select the correct board/port and upload

---

## 🧠 Want to Build Your Own?

For those who prefer to build their own timelapse device, I have written a [full DIY guide](docs/diy-build-guide.md). While the DIY route is completely possible using off-the-shelf components, **LayerLapse was created to save time, simplify the process, and deliver beautiful results right out of the box.** No soldering, wiring, or programming.

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

Support me [on Patreon!](https://www.patreon.com/whopperprinting)

For questions, feedback, or orders:  
📩 Email: whopperprinting@gmail.com  
🔗 Website: [whopperprinting.com](https://whopperprinting.com/) <- Purchase LayerLapse here!  

### Socials

📷 Instagram: [@whopperprinting](https://instagram.com/whopperprinting)  
🕒 TikTok: [@whopperprinting](https://www.tiktok.com/@whopperprinting?is_from_webapp=1&sender_device=pc)

**LayerLapse™ and Whopper Printing™ are trademarks of Whopper Printing. All rights reserved.**
