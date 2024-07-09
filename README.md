# TASK2 : Servo-in-Arduino

## Table of Contents⚙️
- [Project Description](#project-description)
- [Key Features](#key-features-)
- [Technologies Used](#technologies-used)
- [File Structure](#file-structure)

## Project Description📝
This Arduino program is designed to control six servo motors using six corresponding potentiometers. By rotating the potentiometers, users can adjust the positions of the servos, which will move accordingly. The program utilizes arrays to manage multiple servo objects and their associated pins, simplifying the code and enhancing readability. The Servo library is included to provide the necessary functions for controlling the servo motors.

## Key Features ✨
- **Servo Control**: The program initializes an array of six servo objects, each associated with a specific digital pin.

- **Analog Input**: An array of analog input pins is defined to read the values from the potentiometers.

- **Setup Configuration**: In the setup function, each servo is attached to its respective pin, and the corresponding analog pin is set as an input.

- **Continuous Operation**: The loop function continuously reads the analog values from the potentiometers, maps these values to a range suitable for servo angles (0 to 180 degrees), and adjusts the servo positions accordingly.

- **Efficient Code**: Using arrays and loops reduces the amount of code needed and makes it easier to manage multiple servos and potentiometers.

This program is ideal for projects involving multiple servo motors, such as robotic arms, animatronics, or any application requiring synchronized movement based on user input.

## Technologies Used 🔧

- **Tinkercad**

https://www.tinkercad.com/things/59HdNsQHZPX-6servo/editel?sharecode=t7gyHpfuC_p0DrUZI6CyVbk5uE302a-OWPY90WyetLs

Code before:
```
#include <Servo.h> // Include the servo library

Servo myservo1; // Create a servo object for the first servo
Servo myservo2; // Create a servo object for the second servo
Servo myservo3; // Create a servo object for the third servo
Servo myservo4; // Create a servo object for the fourth servo
Servo myservo5; // Create a servo object for the fifth servo
Servo myservo6; // Create a servo object for the sixth servo

void setup() // Setup function runs once when the program starts
{
  myservo1.attach(3); // Attach the first servo to pin 3
  pinMode(A5, INPUT); // Set pin A5 as an input for the potentiometer

  myservo2.attach(5); // Attach the second servo to pin 5
  pinMode(A4, INPUT); // Set pin A4 as an input for the potentiometer

  myservo3.attach(6); // Attach the third servo to pin 6
  pinMode(A3, INPUT); // Set pin A3 as an input for the potentiometer

  myservo4.attach(9); // Attach the fourth servo to pin 9
  pinMode(A2, INPUT); // Set pin A2 as an input for the potentiometer

  myservo5.attach(10); // Attach the fifth servo to pin 10
  pinMode(A1, INPUT); // Set pin A1 as an input for the potentiometer

  myservo6.attach(11); // Attach the sixth servo to pin 11
  pinMode(A0, INPUT); // Set pin A0 as an input for the potentiometer
}

void loop() // Main loop function runs repeatedly
{
  int potValue = analogRead(A5); // Read the analog value from pin A5
  potValue = map(potValue, 0, 1023, 0, 180); // Map the analog value to a range of 0 to 180 degrees
  myservo1.write(potValue); // Set the first servo to the mapped value
} 

void loop2() // Function to control the second servo
{ 
  int potValue = analogRead(A4); // Read the analog value from pin A4
  potValue = map(potValue, 0, 1023, 0, 180); // Map the analog value to a range of 0 to 180 degrees
  myservo2.write(potValue); // Set the second servo to the mapped value
}

void loop3() // Function to control the third servo
{ 
  int potValue = analogRead(A3); // Read the analog value from pin A3
  potValue = map(potValue, 0, 1023, 0, 180); // Map the analog value to a range of 0 to 180 degrees
  myservo3.write(potValue); // Set the third servo to the mapped value
}

void loop4() // Function to control the fourth servo
{ 
  int potValue = analogRead(A2); // Read the analog value from pin A2
  potValue = map(potValue, 0, 1023, 0, 180); // Map the analog value to a range of 0 to 180 degrees
  myservo4.write(potValue); // Set the fourth servo to the mapped value
}

void loop5() // Function to control the fifth servo
{ 
  int potValue = analogRead(A1); // Read the analog value from pin A1
  potValue = map(potValue, 0, 1023, 0, 180); // Map the analog value to a range of 0 to 180 degrees
  myservo5.write(potValue); // Set the fifth servo to the mapped value
}

void loop6() // Function to control the sixth servo
{ 
  int potValue = analogRead(A0); // Read the analog value from pin A0
  potValue = map(potValue, 0, 1023, 0, 180); // Map the analog value to a range of 0 to 180 degrees
  myservo6.write(potValue); // Set the sixth servo to the mapped value
}

```
Code after:
```
#include <Servo.h>

Servo servos[6]; // Array to hold 6 servo objects
int servoPins[6] = {3, 5, 6, 9, 10, 11}; // Array of servo pin numbers
int analogPins[6] = {A5, A4, A3, A2, A1, A0}; // Array of analog input pin numbers

void setup() {
  for (int i = 0; i < 6; i++) {
    servos[i].attach(servoPins[i]); // Attach each servo to its pin
    pinMode(analogPins[i], INPUT); // Set corresponding analog pin as input
  }
}

void loop() {
  int potValue;

  for (int i = 0; i < 6; i++) {
    potValue = analogRead(analogPins[i]); // Read analog input from current servo's pin
    potValue = map(potValue, 0, 1023, 0, 180); // Map analog input to servo angle range
    servos[i].write(potValue); // Set servo position based on mapped value
  }

  delay(15); // Delay to allow servos to reach position
}

```
## File Structure 🏗️

```
Servo in Arduino/
│
├── README.md
```

- `README.md`: This file, containing information about the project.

made with love by "she codes team "🤍😄
raghad Alshammari - sadeem alresaini - razan alothaim.


