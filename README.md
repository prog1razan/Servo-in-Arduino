# TASK2 : Servo-in-Arduino

## Table of Contents⚙️
- [Project Description](#project-description)
- [Technologies Used](#technologies-used)
- [File Structure](#file-structure)

## Project Description📝

## Technologies Used 🔧

- **Tinkercad**

https://www.tinkercad.com/things/59HdNsQHZPX-6servo/editel?sharecode=t7gyHpfuC_p0DrUZI6CyVbk5uE302a-OWPY90WyetLs

```
#include <Servo.h> //servo library
Servo myservo1; 
Servo myservo2;
Servo myservo3; 
Servo myservo4;
Servo myservo5; 
Servo myservo6;

void setup()
 {
  myservo1.attach(3);
  pinMode(A5,INPUT);
  
  myservo2.attach(5);
  pinMode(A4,INPUT);
  
   myservo3.attach(6);
  pinMode(A3,INPUT);
  
  myservo4.attach(9);
  pinMode(A2,INPUT);
  
  myservo5.attach(10);
  pinMode(A1,INPUT);
  
   myservo6.attach(11);
  pinMode(A0,INPUT); 
}

void loop() {
  int potValue;

  potValue = analogRead(A5);
  potValue = map(potValue, 0, 1023, 0, 180);
  myservo1.write(potValue);

  potValue = analogRead(A4);
  potValue = map(potValue, 0, 1023, 0, 180);
  myservo2.write(potValue);

  potValue = analogRead(A3);
  potValue = map(potValue, 0, 1023, 0, 180);
  myservo3.write(potValue);

  potValue = analogRead(A2);
  potValue = map(potValue, 0, 1023, 0, 180);
  myservo4.write(potValue);

  potValue = analogRead(A1);
  potValue = map(potValue, 0, 1023, 0, 180);
  myservo5.write(potValue);

  potValue = analogRead(A0);
  potValue = map(potValue, 0, 1023, 0, 180);
  myservo6.write(potValue);

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
raghd Alshammari - sadeem alresaini - razan alothaim.


