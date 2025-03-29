# 📌 LayerLapse Pinout (ATtiny1604)

This table outlines the key pin assignments for the LayerLapse device using the ATtiny1604 microcontroller.

| Function              | ATtiny1604 Pin # | Name | Direction | Description                             |
|----------------------|------------------|------|-----------|-----------------------------------------|
| Shutter Trigger      | 7                | PB2  | Output    | Controls camera shutter via transistor (tip + ring) |
| LED Indicator        | 6                | PB3  | Output    | Status LED for visual feedback          |
| Hall Effect Sensor   | 9                | PB0  | Input     | Detects magnet to trigger photo         |
| Potentiometer Dial   | 11                | PA1  | Input     | Adjusts delay (0–5 seconds)             |
| GPIO Expansion       | 12                | PA2  | Output    | Optional expansion (servo, IR, etc.)    |
| UPDI Programming     | 10               | PA0 (Reset/UPDI)  | I/O       | Used for flashing firmware              |
| GND                  | 14                | GND  | —         | Ground                                   |
| VCC                  | 1                | VDD  | —         | 5V power input (via USB-C)              |

## Pinout Diagram

![ATTiny1604pinout](https://github.com/user-attachments/assets/44c14b94-aa45-4a28-9825-55f1770bce04)
