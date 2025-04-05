## 🛠️ LayerLapse Setup

1. Plug in the components:
   - Connect the 3.5mm cable between the mainboard and the sensor board
   - Plug in a USB-C power cable
   - Connect the 2.5mm shutter cable from the LayerLapse mainboard to your camera
2. Mount the magnet to your 3D printer's toolhead (use the included 5×5×2mm magnet or use your own)
   - Note: I use tape, it's easy to remove if I ever need to and I've had no issues on any of my printers. It's also easy to reposition during setup.
4. Place the sensor near the printer’s parked position (that you choose in gcode) — ideally within ~10mm of the magnet at its closest pass so the sensor can pickup the magnet.
   - A blue LED lights up on the mainboard when a magnet is detected. This should help you find the sweet spot for where to park and mount your sensor.
   
  ![DSC_2681](https://github.com/user-attachments/assets/970ea87c-7181-4a04-bec6-e2e3799f22ea)
Use tape to mount the sensor, or design your own custom mount for your printer using the [STEP file](docs/HallSensorTest.step) of the sensor!
Here is a mount I made for the Bambu P1P:
  
6. Duplicate your existing printer profile so you don't mess up your regular prints. This way, with the click of a button, you can change your printer from regular mode to timelapse mode and back. Also so you have a gcode to default back to in case you make mistakes.
7. Add G-code (like a custom layer change script) in your slicer to move the print head to that sensor location (e.g., G1 X0 Y200) after each layer. [Custom gcode available here.](code/custom-gcode)
   - This step will be different for everyone depending on the printer and slicer you are using. Below is how to do it in Bambu Studio for Bambu printers, but the idea is the same for all printers and slicers. You also have the freedom to change the parked position and delay that will best suit your own needs.

---

### Printer Specific Setups:
  
[Setup for X1/P1 Printers](https://github.com/user-attachments/assets/25ab0134-a0c5-4ea9-aa74-b6f47c152dec)  
[Setup for A1 Mini](https://github.com/user-attachments/assets/25ab0134-a0c5-4ea9-aa74-b6f47c152dec)
  
---
## For P1/X1 Printers
1. Click the edit preset button in Bambu Studio.
   
![sliceredit-bambu](https://github.com/user-attachments/assets/25ab0134-a0c5-4ea9-aa74-b6f47c152dec)

---
  
2. Go to the Machine gcode tab. Scroll down to the Layer change G-code section, and copy/paste or modify [the Gcode for your printer.](code/custom-gcode)
   
  ![gcode2](https://github.com/user-attachments/assets/6ab334f6-d3ee-40f0-84a2-4a46daaf92d2)
  
Note: This is an example I made for the P1P, but if you decide to change the position of your magnet or sensor, you'll need to change the position in the gcode. To do that, modify this line in the gcode (the X and Y coordinates):
  
``
G1 X256 Y200 F20000 ; THIS IS THE PARKED POSITION, change this if you want to change the parking position if you put the sensor in a different location (F20000 is the speed, this can be left the same)
``

---
  
3. Save your new preset as a different name (i.e., P1P Timelapse), this way you can swap between timelapse mode and regular printing with the click of a button.
  ![save](https://github.com/user-attachments/assets/f66204df-b03e-49f5-b4b6-fd5c44d8a624)


Once set up, LayerLapse will automatically trigger your camera after every layer, creating smooth and consistent timelapse footage!

---

### For A1 Mini

Follow the setup for the X1/P1 printers, but on step 2, instead of the Layer change section, use the Time lapse G-code section.
  
![AImini](https://github.com/user-attachments/assets/45ee76d3-cf4a-4b3a-adfd-6c09cac00d2b)

Then copy/paste the [A1 Mini specific gcode](code/custom-gcode) into this section.

  Notes:
    
  The parked position will be near the filament wiper on the end. You can change this position and delay by changing these lines in the code:

``
G1 X-1 Y180 F18000 ;THIS IS THE PARKED POSITION, CHANGE THE X AND Y VALUES TO CHANGE THE PARKED POSITION
M400 P300 ; THIS IS THE DELAY BETWEEN PARKING AND CONTIUING PRINTING, CHANGE THE P VALUE TO CHANGE THE DELAY (P300 is 300 miliseconds)
``


--
