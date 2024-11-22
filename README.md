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
  - Remove the dumb controller and strip the wires, then follow the steps as explained further below.

## Wiring Instructions:
  1. Lamp-red-wires(power) to PicoW-pin(VBUS)
      **Explanation:** The red LED wires are connected to the collector pin of the second transistor. This configuration controls the current flow through the red LEDs.
  3. Lamp-white-wires(blue LEDs) to #1-transistor-pin(2-collector)
  4. Lamp-black-wires(red LEDs) to #2-transistor-pin(2-collector)
  5. #1-resistor(A) to #1-transistor-pin(1-base) to PicoW-pin(16-blue)
  6. #2-resistor(A) to #2-transistor-pin(1-base) to PicoW-pin(17-red)
  7. From #1-resistor(B) to #1-transistor-pin(3-emitter) to #2-resistor(B) to #2-transistor-pin(3-emitter) to PicoW-pin(GND)

