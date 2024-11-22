# Smart-LED-Grow-Light
DIY project to turn a regular LED grow light with a dumb controller to a smart one with a Raspberry Pi PicoW which you can integrate to Home Assistant with ESPHome.

## Necessary components:
  ##1. 2 head grow light, full spectrum red & blue, 5V USB lamp, 2 x 20 LEDs, 80W.
  2. Micro-USB cable with data transfer (for both charging and compiling).
  3. Any 5V 1A phone charger or 5V USB poer supply.
  4. Raspberry Pi PicoW.
  5. 2x8 cm double-sided PCB prototype board.
  6. Jumper wires (DuPont - female).
  7. 2 x TIP132 NPN Transistor 5V (1 for red & 1 for blue).
  8. 2 x 1 kΩ ±5% Resistor (1 for red & 1 for blue).
  9. Printed case.

## Preparing the lamp:
  1. Remove the dumb controller and strip the wires, then follow the steps as explained further below.

## Wiring:
  1. Lamp-red-wires(power) to PicoW-pin(VBUS)
  2. Lamp-white-wires(blue LEDs) to #1-transistor-pin(2-collector)
  3. Lamp-black-wires(red LEDs) to #2-transistor-pin(2-collector)
  4. #1-resistor(A) to #1-transistor-pin(1-base) to PicoW-pin(16-blue)
  5. #2-resistor(A) to #2-transistor-pin(1-base) to PicoW-pin(17-red)
  6. From #1-resistor(B) to #1-transistor-pin(3-emitter) to #2-resistor(B) to #2-transistor-pin(3-emitter) to PicoW-pin(GND)

