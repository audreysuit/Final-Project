# BAE 305 Final Project: Foamtastic

- Megan Fister
- Audrey Suit
- Shika Uppala

 # Summary
  
Our project is an automated cold-foam dispensing system designed to streamline a key step in specialty coffee preparation. The machine operates with minimal user input, requiring only the placement of a coffee cup on a sensor pad and occasional refilling of cream and syrup reservoirs. Once the cup is detected by an analog QRE1113 reflectance sensor, the system initiates a sequence that first dispenses syrup and cream through two 3.3V submersible pumps. Next, a stepper-motor-driven linear rail lowers a milk frother into the cup. A servo motor activates the frother, which prepares cold foam directly inside the cup. After frothing, the rail returns the frother to its original position, and a second servo can perform a follow-up action, such as dispensing or completing the foam layer. The system is designed for consistency, ease of use, and hands-free operation, demonstrating how automation can improve efficiency and reduce labor demands in beverage preparation.

# Design Description

### Materials

- Arduino Uno
- 1x QRE1113 Analog Reflectance Sensor
- 1x 3.3V Submersible Pump
- 1x NPN Transistor (e.g., 2N2222 or TIP120)
- 2x 1kΩ Resistors (for transistor bases)
- 2x Flyback Diodes (e.g., 1N4001 or 1N4007)
- 1x L9110S Dual Motor Driver Module
- 1x 4-wire Stepper Motor with Lead Screw Linear Rail
- 2x Servo Motors (e.g., MG90S or SG90)
- External 3.3V Power Supply or Buck Converter
- Breadboard and Jumper Wires
- Pushbutton (for manual pump control testing)
- 10kΩ Resistor (for button pull-down)
- USB Cable (for Arduino programming and serial monitoring)
- Power distribution wires and common ground connections

# Testing Description

# Design Decision Discussion

# Test Results
