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

The cold foam dispensing system integrates various electronic components to automate the mixing and dispensing of cold foam onto a coffee beverage. The main control board is a SparkFun RedBoard, mounted on a prototyping base along with a solderless breadboard for circuit prototyping.

Circuit Components and Configuration:
1.	Microcontroller (SparkFun RedBoard)
- Acts as the central control unit.
- Powered via USB and connected to various digital I/O pins.
2.	Analog Reflectance Sensor
- Mounted at the base of the platform to detect the presence of a coffee mug.
- When a cup is detected, it signals the RedBoard to initiate the sequence.
3.	Mini Submersible Water Pump
- Powered via a digital output pin (likely through a transistor for sufficient current drive).
- Draws milk or syrup from a reservoir through clear tubing into the mixing cup.
4.	Stepper Motor + Linear Rail Assembly
- A stepper motor is used to raise and lower the mixing cup (likely the one holding milk and syrup).
- The movement is controlled through a motor driver circuit wired on the breadboard.
5.	Foam Frother Motor
- Mounted vertically on a wooden post.
- Controlled via the RedBoard, it rotates a whisk to froth the liquid in the mixing cup.
6.	Servo Motor (Not directly shown, may be part of rail or dispensing arm)
- Used to rotate the arm or cup back to its original position after frothing is complete.
7.	Power and Wiring
- Jumper wires connect all components to the RedBoard and breadboard.
- Power is supplied to components via 5V and GND rails.
- Control signals run from the RedBoard’s digital pins to the motor driver, pump, and sensors.

![Frame](https://github.com/audreysuit/Final-Project/blob/main/Foamtastic%20Circuit.jpg)


### Code

The code for this project can be viewed using the link below. This script is intended to be run in the Arduino IDE software. There are comments within the code describing the purpose of each line.

https://github.com/audreysuit/Final-Project/blob/e46cff29bf43b364e0ddb217e1055918d41da11a/Foamtastic%20Code

### Assembly

![image](https://github.com/user-attachments/assets/1386f666-135a-4ec8-a411-12efd97bb55d)

Assembly began with the wooden base described in the previous "Frame" section. We attached the linear rail to the wooden post and the frother to the linear rail using zip ties (1). We elevated the cream tank and zip-tied the tubing to the post (2), pointing into the mixing cup. The mixing cup was trimmed to size to fit the system.  Below the tubing outlet, we drilled a small block of wood to the post and zip-tied a servo to the block (3). The servo is hot-glued and zip-tied to the mixing cup for ensured support and stability. The frother button pushing servo was attached to the frother using hot glue. The analog reflectance sensor nested in the cupholder is seen in (4). We used tape to secure the sensor and its wiring. The circuit board is elevated and placed on the back of the board behind the post.


# Design Decision Discussion

### Frame

We initially considered using perforated metal sheets and rods to assemble the frame. After a discussion with Dr. Jarro, he informed us that this would be quite expensive and heavy, and recommended we use wood instead. By using wood, we were able to use pieces from former 305 projects and receive great assistance from Dr. Jarro. It was easy to size exactly what we needed by sawing pieces and simply drilling them together. The cupholder plate was from a previous project and already had a hole in it, so it was perfect and easy to integrate. We added the extra piece of wood to the top of the post because the frother needed to sit farther away from the post to lower into the cup properly. 

### Frother

The frother needed an easily pressed top button. At first, the servo wasn't strong enough to push the button and power the frother. Dr. Jarro helped us take it apart, and we ended up removing the spring that was giving resistance to the button. By removing the spring, the servo was able to turn the frother on. Looking at servo specifics, we decided to attach the servo to the frother itself, rather than at the top of the rail. Using hot glue was effective and ensured the servo would never miss the button.

### Pump

Our first choice for a pump was a peristaltic pump, but we wouldn't have gotten the part in time, so we went with a submersible pump. This wasn't ideal, since the pump is typically intended for water, and our system uses a thicker and harder to clean fluid: half and half. The pump had to be elevated a few inches to push the cream through, but it responds quickly and with stability.

### Sensor

An analog reflectance sensor was also recommended by Dr. Jarro. Initially, we had the idea of using some kind of weight-activated system, like a pressure sensor pad. There were already some reflectance sensors in the lab, so it was an economical decision to use what was available instead of purchasing something new. 

# Testing Description
To begin our testing phase, we connected each component to the Arduino and developed the control code, with assistance from ChatGPT, to automate the entire process.

### Stepper Motor Linear Rail
We connected the 4-wire stepper motor linear rail and wrote code to move it fully down and back up. This required fine-tuning the steps_per_move value to achieve consistent and accurate motion.

### Servo Motors
We used two servo motors from the SparkFun kit, testing various rotation angles based on their specific tasks:

- One servo was hot glued to the top of the frother, with 90 degrees of rotation calibrated to press the frother's power button.

- The second servo was zip-tied to the vertical wooden support, with a hot-glued attachment to the mixing cup. We determined that rotating 120 degrees would effectively tilt the cup and pour the cold foam into the mug.

### Submersible Pump
We tested the pump using water, experimenting with different heights for the container holding the liquid. The elevation affected flow rate, so we adjusted both the container height (eventually placing it just below the tube outlet) and the pump's run time to avoid overfilling or splashing during frothing.

### Reflectance Sensor
The reflectance sensor was tested using the serial monitor to record its baseline value and the value when a mug was placed on top. We selected a setpoint between those readings to reliably trigger the system when a mug is detected.

### Final Assembly & Full System Test
Once all individual components were calibrated, we assembled the complete system and ran tests to ensure the entire sequence operated smoothly and reliably.

# Test Results Discussion
Throughout development, we encountered several challenges that required creative problem-solving:

### Frother Activation Issue
Initially, the servo motor did not apply enough force to press the frother's power button. With guidance from Dr. Jarro, we disassembled the frother and removed a spring inside, significantly reducing the required force and allowing the servo to activate it reliably.

### Cup Stability Problem
During testing, the weight of the liquid caused the mixing cup to detach from the servo. To resolve this, we reinforced the attachment by wrapping the cup with zip ties and securing the servo arm underneath. We also added hot glue to stabilize the connection and ensure reliable tilting during pouring.

### Power Distribution Failure
When the pump was added to the system, the entire setup failed due to insufficient power distribution. To address this, we integrated a 4-channel output module rack to separate the control and power circuits.

- Instead of the Arduino supplying power directly to the pump, it now sends a low-power signal to an opto-isolator on the module, which switches the pump on and off.

- Although the pump is still powered through the Arduino’s 5V pin, this configuration isolates the pump’s current draw from the Arduino’s logic pins, preventing voltage drops and signal interference.

- This solution provided more consistent power to the pump and improved overall system stability.

# Test Results
### System Functionality
When a mug is placed over the reflectance sensor, the system is activated. First, the pump turns on and pumps the cream and syrup mixture into the mixing cup for 5 seconds. Next, the stepper motor linear rail lowers the frother into the cup. Once the frother reaches the bottom, a servo motor mounted on top of it activates after a short delay, pressing the frother's power button and running it for 10 seconds to create a cold foam consistency. Finally, another servo motor rotates the mixing cup over the mug, allowing the cold foam to pour onto the coffee, then returns the cup to its original position.

### Mechanical Limitations
After repeated use over several days, the plastic mount on the stepper motor linear rail began to wear down due to the weight of the frother. The friction between the rail’s metal components and the plastic attachment caused gradual degradation, eventually preventing the actuator from fully lifting the frother without additional support from below.

### Design Enhancements
This issue could be addressed by upgrading to more durable, higher quality components such as metal mounts or a more robust linear actuator to better handle the mechanical stress and extend the system's lifespan.
