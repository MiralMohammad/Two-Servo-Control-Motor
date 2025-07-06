# 🔁 Dual Servo Motor Control with Arduino

This project demonstrates how to control two servo motors using an Arduino Uno board. Each servo is connected to a different digital pin and performs a series of angle rotations in sync or opposite directions.

---

## 🔌 Components Used

- 1x Arduino Uno R3
- 2x Servo Motors (SG90 or similar)
- Jumper wires
- Breadboard (optional)

---

## 🧠 How It Works

- **Servo 1 (myServo)** is connected to digital pin **9**.
- **Servo 2 (myServo2)** is connected to digital pin **10**.
- The servos alternate their angles every second:
  - First: myServo at 0°, myServo2 at 180°
  - Second: Both at 90°
  - Third: myServo at 180°, myServo2 at 0°

This creates a mirrored movement pattern between the two servos.

---

## ⚙️ Circuit Connections

| Servo Pin  | Arduino Pin     |
|------------|-----------------|
| Signal     | 9 (myServo)     |
| Signal     | 10 (myServo2)   |
| VCC        | 5V              |
| GND        | GND             |

---

## 💻 Code

```cpp
#include <Servo.h>

Servo myServo;
Servo myServo2;

void setup() {
  myServo.attach(9);
  myServo2.attach(10);
}

void loop() {
  myServo.write(0);
  myServo2.write(180);
  delay(1000);

  myServo.write(90);
  myServo2.write(90);
  delay(1000);

  myServo.write(180);
  myServo2.write(0);
  delay(1000);
}
