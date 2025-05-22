This is code that was sent to me by a LayerLapse user.

This parks the printer on the left side between layers. I don't personally have this printer, so please use discretion.

Here's what it looks like in the PrucaSlicer under "Printers" "custom G-code" and "After_Layer_Change"

;Move printer head to far left corner for picture  
G0 X0 Y500  
;pause for picture  
G4 S1