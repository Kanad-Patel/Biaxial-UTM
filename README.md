# Universal Testing Machine (UTM) with Dual Stepper Motors, Load Cells, and Strain Gauge

_Note: This is a work in progress project and any feedback is much appreciated._

This project involves creating a **Universal Testing Machine (UTM)** using two **NEMA 17 stepper motors**, **load cells**, a **strain gauge**, and an **Arduino Uno**. The system is capable of controlling stepper motors, logging strain and load data, and using limit switches for safety.

## Overview

This UTM is designed to test material properties by applying a controlled load and measuring the resulting strain. The setup includes multiple sensors and electronic components to enable precise control and measurement. The data is logged through a serial interface to analyze the material's characteristics.

## Features

- Dual **NEMA 17 stepper motors** with precise control.
- Two **load cells** for accurate measurement of applied force.
- One **strain gauge** to measure material deformation.
- **Limit switches** to prevent over-travel and protect the system.
- Data logging via **serial communication** to monitor strain and load in real-time.

## Components

### Motors and Motor Drivers
- **2 x NEMA 17 Stepper Motors**: High torque motors used to apply force to the test specimen.
- **2 x A4988 Stepper Motor Drivers**: Motor drivers to control the stepper motors' direction and movement.

### Sensors
- **2 x Load Cells**: Used to measure the force applied by the motors. Connected through **HX711** amplifiers.
  - **HX711 Amplifiers**: Used to amplify the signal from the load cells for precise force measurement.
- **1 x Strain Gauge Module**: Measures the deformation of the material under load.

### Electronics
- **Arduino Uno**: Microcontroller used for controlling the motors, reading sensor data, and logging data.
- **Limit Switches**: Two switches to detect and prevent over-travel of the stepper motors.

### Wiring and Power Supply
- **Power Supply**: 12V or 24V power supply to power the motors and other components.
- **Connecting Wires** and **Breadboard**: For prototyping and connecting components.

## How to Set Up

1. **Connect Stepper Motors** to the A4988 drivers:
   - Connect **STEP**, **DIR**, and **ENABLE** pins from the motor drivers to the Arduino.
   - Wire the motor coils to the driver outputs (1A, 1B, 2A, 2B).
   - Provide power to the A4988 driver (VMOT to 12V/24V, GND to common ground).

2. **Connect Load Cells** to HX711 modules:
   - Wire the load cell outputs to the HX711 amplifier (E+, E-, A+, A-).
   - Connect **DT** and **SCK** pins from the HX711 to the Arduino.

3. **Connect Strain Gauge**:
   - Connect the strain gauge signal output to an **analog input** on the Arduino.

4. **Connect Limit Switches**:
   - Wire each limit switch between **GND** and an **input pin** on the Arduino.

5. **Power Up**:
   - Connect the Arduino to your computer via USB for programming and data logging.
   - Power the motors using an external 12V or 24V power supply.

## Code

The Arduino code is written to control the stepper motors, read data from the load cells and strain gauge, and log the data via serial communication.

### Key Features of the Code
- Moves both motors **simultaneously** for **4 seconds** in a backward direction while logging strain and load data.
- Reads data from two load cells via **HX711** amplifiers and from a **strain gauge** connected to an analog pin.
- Logs **absolute values** of strain and load, converted to **kg** for easy interpretation.

## How to Use
1. **Upload the Code**: Use the Arduino IDE to upload the provided code to the Arduino Uno.
2. **Power the Setup**: Connect the power supply for the motors and connect the Arduino to the computer.
3. **Start the Test**: The motors will move for 4 seconds while logging data from the sensors.
4. **Monitor the Data**: Open the **serial monitor** in the Arduino IDE to view real-time strain and load data in CSV format.

## Dependencies
- **HX711 Library**: To read data from the load cells.
- **Stepper Motor Control**: Using basic GPIO pins to drive the **A4988** motor drivers.

## Future Improvements
- Add a **graphing interface** to visualize strain vs. load in real-time.
- Implement an **SD card module** for offline data logging.
- Integrate a **PID controller** for more precise control of motor movement.

## License
This project is open-source and licensed under the **MIT License**.

## Contributing
Feel free to contribute to this project by submitting **pull requests** or **issues** on GitHub. Any suggestions for improvements are always welcome!



