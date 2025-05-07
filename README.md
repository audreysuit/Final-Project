# BAE 305 Final Project: Foamtastic

- Megan Fister
- Audrey Suit
- Shika Uppala

 # Summary
  
Our project is an automated cold-foam dispensing system designed to streamline a key step in specialty coffee preparation. The machine operates with minimal user input, requiring only the placement of a coffee cup on a sensor pad and occasional refilling of cream and syrup reservoirs. Once the cup is detected by an analog QRE1113 reflectance sensor, the system initiates a sequence that first dispenses syrup and cream through a 3.3V submersible pump. Next, a stepper-motor-driven linear rail lowers a milk frother into the cup. A servo motor activates the frother, which prepares cold foam directly inside the cup. After frothing, the rail returns the frother to its original position, and a second servo can perform a follow-up action, such as dispensing or completing the foam layer. The system is designed for consistency, ease of use, and hands-free operation, demonstrating how automation can improve efficiency and reduce labor demands in beverage preparation.

# Design Description

### Materials
- Arduino Uno – for controlling the system components
- 1x QRE1113 Analog Reflectance Sensor
- 1x 3–5V DC Micro Submersible Mini Water Pump – pumps the milk/syrup mixture into the frothing cup
- 1x L9110S Dual Motor Driver Module
- 1x DC 5V–12V 2-Phase 4-Wire Stepper Motor Linear Rail (90 mm stroke) – lowers and lifts the frother into/from the cup
- 2x Servo Motors (SG90) -  One to tilt the plastic cup and pour foam into the coffee, one to press the button on the handheld frother to turn it on
- 1x QRE1113 Analog Line Sensor - detects when a coffee mug is placed and starts the system
- 1x External battery pack (Three 1.5 V batteries) – to avoid underpowering components
- 1x G4PB4R – 4-Channel Output Module Rack – to separate logic and power circuits via opto-isolation
- Plastic tubing – to direct the liquid from the pump to the frothing cup
- 1x Plastic cup (frothing container) – holds milk and syrup for frothing
- Breadboard and Jumper Wires – for connecting and prototyping the circuit
- 1x Handheld frother – creates cold foam from the milk/syrup mixture
- Zipties – for securing components like the frother to the actuator and cup to servos
- Mounting brackets / frame materials (wood, acrylic, or 3D printed) – for structural support and alignment of components
- 1x Coffee mug – where the final drink is prepared
- Milk and syrup mixture – for creating cold foam
- 1x USB Cable (for Arduino programming and serial monitoring)
- Power distribution wires and common ground connections


## Frame
The frame of our system is straightforward yet functional. We started with a square wooden base and mounted a thicker vertical wooden slab onto it. This vertical support holds the frother and the cup used for mixing and dispensing the cold foam. Adjacent to the vertical slab, we added a thinner wooden platform with a hole drilled in its center. The sensor is placed in this hole, and when a coffee mug is set on top, it covers the hole and activates the system by triggering the sensor.

![Frame](https://github.com/audreysuit/Final-Project/blob/main/Foamtastic%20Frame.jpg)

### Physical Design

The design flow starts with an analog reflectance sensor nested in a cup-shaped cutout in the baseplate. When a cup is placed on the sensor, the pump system is activated. A submersible pump submerged in a tank pumps cream through plastic tubing into the mixing cup. The mixing cup is mounted to a servo motor, which is attached to a wooden post. Also attached to the post is stepper motor-driven linear rail, which moves the zip-tied milk frother up and down into the cup. After being lowered into the mixing cup, another servo glued to the top of the frother pushes down onto the button, causing it to run and froth the cream. After the cream has been frothed, the frother is moved back to the top. The servo attached to the mixing cup rotates, pouring the cold foam into the starting coffee cup. 

### Circuits

Add description of wiring and parts, photos of the circuit, and potentially schematics.

### Code

The code for this project can be viewed using the link below. This script is intended to be run in the Arduino IDE software. There are comments within the code describing the purpose of each line.

https://github.com/audreysuit/Final-Project/blob/e46cff29bf43b364e0ddb217e1055918d41da11a/Foamtastic%20Code

### Assembly

![image](https://github.com/user-attachments/assets/1386f666-135a-4ec8-a411-12efd97bb55d)

Assembly began with the wooden base described in the previous "Frame" section. We attached the linear rail to the wooden post and the frother to the linear rail using zip ties (1). We elevated the cream tank and zip-tied the tubing to the post (2), pointing into the mixing cup. The mixing cup was trimmed to size to fit the system.  Below the tubing outlet, we drilled a small block of wood to the post and zip-tied a servo to the block (3). The servo is hot-glued and zip-tied to the mixing cup for ensured support and stability. The frother button pushing servo was attached to the frother using hot glue. The analog reflectance sensor nested in the cupholder is seen in (4). We used tape to secure the sensor and its wiring. The circuit board is elevated and placed on the back of the board behind the post.


# Design Decision Discussion

### Frame

We initially considered using perforated metal sheets and rods to assemble the frame. After a discussion with Dr. Jarros, he informed us that this would be quite expensive and heavy, and recommended we use wood instead. By using wood, we were able to use pieces from former 305 projects and receive great assistance from Dr. Jarros. It was easy to size exactly what we needed by sawing pieces and simply drilling them together. The cupholder plate was from a previous project and already had a hole in it, so it was perfect and easy to integrate. We added the extra piece of wood to the top of the post because the frother needed to sit farther away from the post to lower into the cup properly. 

### Frother

The frother needed an easily pressed top button. At first, the servo wasn't strong enough to push the button and power the frother. Dr. Jarros helped us take it apart, and we ended up removing the spring that was giving resistance to the button. By removing the spring, the servo was able to turn the frother on. Looking at servo specifics, we decided to attach the servo to the frother itself, rather than at the top of the rail. Using hot glue was effective and ensured the servo would never miss the button.



# Testing Description
## System Functionality
When a mug is placed over the reflectance sensor, the system is activated. First, the pump turns on and pumps the cream and syrup mixture into the mixing cup for 5 seconds. Next, the stepper motor linear rail lowers the frother into the cup. Once the frother reaches the bottom, a servo motor mounted on top of it activates after a short delay, pressing the frother's power button and running it for 10 seconds to create a cold foam consistency. Finally, another servo motor rotates the mixing cup over the mug, allowing the cold foam to pour onto the coffee, then returns the cup to its original position.

## Mechanical Limitations
After repeated use over several days, the plastic mount on the stepper motor linear rail began to wear down due to the weight of the frother. The friction between the rail’s metal components and the plastic attachment caused gradual degradation, eventually preventing the actuator from fully lifting the frother without additional support from below.

## Design Enhancements
This issue could be addressed by upgrading to more durable, higher quality components such as metal mounts or a more robust linear actuator to better handle the mechanical stress and extend the system's lifespan.


# Test Results
