# For BambuLab P1P and P1S (presumably X1 printers also)

Copy and paste the code below into "Layer change G-code" in the printer settings in the BambuStudio slicer.

You are welcome to change the **G4 P900** to any other value you'd like. The 900 is 900 milliseconds. If you modify this, make sure you modify the code on LayerLapse to ensure they work in harmony.

```
; layer num/total_layer_count: {layer_num+1}/[total_layer_count]
M622.1 S1 ; for prev firware, default turned on
M1002 judge_flag timelapse_record_flag
M622 J1
{if timelapse_type == 0} ; timelapse without wipe tower
M971 S11 C10 O0
;
{elsif timelapse_type == 1} ; timelapse with wipe tower
G92 E0
G1 E-[retraction_length] F1800
G17
G2 Z{layer_z + 0.4} I0.86 J0.86 P1 F20000 ; spiral lift a little
G92 E0
G1 E-[retraction_length] F1800
G17
G2 Z{layer_z + 0.4} I0.86 J0.86 P1 F20000 ; spiral lift a little
G1 X256 Y200 F20000
G4 P900 ;wait 900 milliseconds before moving after parking
{endif}
M623
; update layer progress
M73 L{layer_num+1}
M991 S0 P{layer_num} ;notify layer change
;
```
In your slicer printer settings, turn on "smooth" under timelapse. You can move the prime tower anywhere on the print plate that is best for you and your camera position.

![smoothtimelapse](https://github.com/user-attachments/assets/ffe6bc2c-1c50-4778-a3cd-e49aea7d678a)
