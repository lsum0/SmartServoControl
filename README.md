# 🤖 ServoMotor – Multi-Servo Control System with Arduino UNO

An educational and practical project that demonstrates how to control multiple servo motors with an Arduino UNO using PWM pins. This guide includes the actual components used, wiring photo, logical flowchart, and a professional overview of the hardware.

---

## 🔧 Components Used

Below is a list of the real hardware used in this project:

| Component                  | Quantity | Description                        |
|----------------------------|----------|------------------------------------|
|  Arduino UNO             | 1        | Microcontroller board                |
|  Breadboard              | 1        | For power and signal distribution    |
|  TowerPro SG90 Servo     | 5        | 180° micro servos                    |
| Jumper Wires (M-M)       | 10+      | For signal & power connections       |
| External 5V Power (opt)  | 1        | Optional, for better torque          |

###  Actual Project Setup Photo :
> This is the real photographed setup used in this project:

![Project Components and Wiring](ServoMotor.gif)

---

##  System Flowchart :

This flowchart describes the logic used in the code and system operation:

###  Workflow:
1. Start the system
2. Initialize servo motors
3. Wait for input
4. If input is received → rotate servos
5. End the loop

### 🖼️ Flowchart Diagram

![Flowchart](FlowChart.png) 

---

##  Servo Motor Details :

### Model: **TowerPro SG90 Micro Servo**

- **Rotation Range:** 180°
- **Operating Voltage:** 4.8V – 6.0V
- **Stall Torque:** ~1.8 kg/cm
- **Speed:** 0.1s/60° at 4.8V
- **Gear Type:** Plastic gears
- **Weight:** ~9 grams

  ![TheCommponent](Thecomponent.jpg)

This servo is compact and lightweight, making it ideal for small robotic projects, arms, grippers, and pan/tilt platforms.

### 🖼️ Real Servo Image

![TowerPro SG90](TheServoMotor.jpg)

---

## 💻 Arduino Code Overview

```cpp
#include <Servo.h>
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;
Servo servo5;

void setup()
{
  servo1.attach(3);
  servo2.attach(5);
  servo3.attach(6);
  servo4.attach(9);
  servo5.attach(10);
}

void loop()
{
  for(int i = 0; i <= 180; i = i + 10)
  {
    servo1.write(i); delay(50);
    servo2.write(i); delay(50);
    servo3.write(i); delay(50);
    servo4.write(i); delay(50);
    servo5.write(i); delay(50);
  }
  
  for(int i = 180; i >= 0; i = i - 10)
  {
    servo1.write(i); delay(50);
    servo2.write(i); delay(50);
    servo3.write(i); delay(50);
    servo4.write(i); delay(50);
    servo5.write(i); delay(50);
  }
  
  /*
  for(int j = 0; j <= 180; j = j + 10)
  {
    servo2.write(j);
    delay(500);
  }
  */
  
  
  /*
  for(int j = 180; j >= 0; j = j - 10)
  {
    servo2.write(j);
    delay(500);
  }
  */
}
```
```Text
### Project Structure 📂 :

ServoMotor-Algorithm/
├── ServoMotor.ino          # Arduino code
├── ServoMotor.gif          # Real wiring image
├── flowchart.png           # Flowchart for algorithm
├── servo.jpg               # Real SG90 photo
├── README.md               # This file
```
