# Arduino Nano Keyboard Emulator

This project allows you to use an **Arduino Nano** with connected buttons as a **virtual keyboard**, sending key presses to your PC.  
It includes an **Arduino sketch** and a **Python script** to receive button events and emulate keyboard keys.

## Contents
- `DDR_Nano.ino`: Arduino sketch with 11 buttons and built-in **debounce**.  
- `ddr_buttons.py`: Python script that automatically detects the Nano (CH340) and emulates keyboard keys.

## Features
- Up to 11 buttons mapped to keyboard keys by default.  
- Keyboard-like behavior: key stays pressed while the button is held and releases when the button is released.  
- VID/PID filtering to detect only the Arduino Nano and avoid conflicts with other Arduinos connected.  
- Software debounce to prevent **double presses on the first touch**.

## Usage
1. Connect the Arduino Nano to your PC.  
2. Open `DDR_Nano.ino` in Arduino IDE and upload it to the Nano.  
3. Install Python 3 and the required libraries:
   ```bash
   pip install pyserial pynput
4. Run the Python script: python ddr_buttons.py
5. Your buttons will now behave like a physical keyboard in any application that accepts keyboard input.

Customization

Change the key mapping by editing the mapa dictionary in ddr_buttons.py.

Adjust the number of buttons or debounce behavior directly in the Arduino sketch.

Notes

Currently supports Arduino Nano with CH340 chip (VID: 1A86, PID: 7523).

Other Arduino models may require modifying the filtering in the Python script.
