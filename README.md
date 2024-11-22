# Smart-LED-Grow-Light
DIY project to turn a regular LED grow light with a dumb controller to a smart one with a Raspberry Pi PicoW which you can integrate to Home Assistant with ESPHome.

## Requirements:
  - 2 head grow light, full spectrum red & blue, 5V USB lamp, 2 x 20 LEDs, 80W.
  - Micro-USB cable with data transfer (for both charging and compiling).
  - Any 5V 1A phone charger or 5V USB poer supply.
  - Raspberry Pi PicoW.
  - 2x8 cm double-sided PCB prototype board.
  - Jumper wires (DuPont - female).
  - 2 x TIP132 NPN Transistor 5V (1 for red & 1 for blue).
  - 2 x 1 kΩ ±5% Resistor (1 for red & 1 for blue).
  - Printed case.

## Preparations:
  1. Remove the dumb controller and strip the wires.
  2. Solder the two transistors to the PCB prototype board (make sure to keep a fair distance between them), then follow the steps as explained further below.

## Wiring Instructions:
  1. **Lamp-red-wires(power) to PicoW-pin(VBUS).**
     - **Explanation:** Connect both the lamp's red wires to a DuPont female cable (remove one end and strip it), then connect the cable to the Pico's VBUS pin (no soldering).
  2. **Lamp-white-wires(blue LEDs) to #1-transistor-pin(2-collector)**
     - **Explanation:** Connect both the lamp's white wires (in my case these wires give control over the blue LEDs) to a DuPont cable (remove both ends and strip them), then solder the cable to #1 transistor's pin2.
  3. **Lamp-black-wires(red LEDs) to #2-transistor-pin(2-collector)**
     - **Explanation:** Connect both the lamp's black wires (in my case these wires give control over the red LEDs) to a DuPont cable (remove both ends and strip them), then solder the cable to #2 transistor's pin2.
  4. **#1-resistor(A) to #1-transistor-pin(1-base) to PicoW-pin(16-blue)**
     - **Explanation:** Solder a resistor's end(A) to the #1 transistor's pin1, then solder a DuPont cable's end to both (remove one end and strip it), connecting the other end to the Pico's pin16 (for blue).
  5. **#2-resistor(A) to #2-transistor-pin(1-base) to PicoW-pin(17-red)**
     - **Explanation:** Solder a resistor's end(A) to the #2 transistor's pin1, then solder a DuPont cable's end to both (remove one end and strip it), connecting the other end to the Pico's pin17 (for red).
  6. **From #1-resistor(B) to #1-transistor-pin(3-emitter) to #2-resistor(B) to #2-transistor-pin(3-emitter) to PicoW-pin(GND)**

