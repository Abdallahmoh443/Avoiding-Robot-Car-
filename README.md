Avoiding-Robot-Car
This project is an autonomous robot car designed to navigate around obstacles using an Arduino microcontroller. It uses ultrasonic sensors to detect obstacles and servos to adjust direction, allowing the car to avoid collisions and move smoothly through its environment.

Components Used
Arduino Uno
Servo Motor
Ultrasonic Sensor (HC-SR04)
Motor Driver (L298N)
DC Motors
Wheels
Power Supply
Jumper Wires
Breadboard
Pin Configuration
Ultrasonic Sensor:
Trig Pin: 11
Echo Pin: 12
Motor Driver (L298N):
IN1: 2
IN2: 3
IN3: 4
IN4: 7
ENA: 5
ENB: 6
Servo Motor: 9
Switch: A5
Code Description
The code controls the movement of the robot car based on the distance detected by the ultrasonic sensor. The car moves forward if no obstacle is detected within 30 cm. If an obstacle is detected within 30 cm, the car stops and measures the distance on the right and left to determine the best path. The car then turns accordingly to avoid the obstacle.

Functions
void compression(int r, int l);: Determines the best direction to turn based on the distances on the right and left.
void off(void);: Stops all motor activity.
void reverse(void);: Reverses the car for a short distance.
void tleft90(void);: Turns the car 90 degrees to the left.
void tright90(void);: Turns the car 90 degrees to the right.
void forward(void);: Moves the car forward.
void tleft180(void);: Turns the car 180 degrees to the left.
int fdistance(void);: Measures the distance to the nearest obstacle using the ultrasonic sensor.
Setup
Connect the components as per the pin configuration.
Upload the provided code to the Arduino Uno.
Power the Arduino and the motor driver.
Observe the robot car avoiding obstacles autonomously.
Usage
Make sure all connections are secure.
Power the system.
The robot car will start moving forward.
If it detects an obstacle within 30 cm, it will decide whether to turn left, right, or reverse based on the obstacle's position.
Notes
The servo motor initially positions the ultrasonic sensor at 85 degrees.
The car's movement and obstacle avoidance decisions are based on simple distance measurements and predefined distance thresholds.
Ensure the power supply is sufficient for both the Arduino and the motors to function properly.
