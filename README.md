# PCA9685---Servo-Motor-Controller-Interface

Test code for the Servo Motors.  The following tutorial contains information about the servoboard, the library and its usage: https://www.youtube.com/watch?v=y8X9X10Tn1k&t=828s

In order to run these scripts, the PCA685 arduino library must be properly downloaded and set up: https://github.com/adafruit/Adafruit-PWM-Servo-Driver-Library.  See 5:41 in the video for instructions.

## servo_config.ino
Used to configure SERVOMIN and SERVOMAX for each motor.  To find SERVOMIN, find the lowest possible value before the motor begins to hum.  To find SERVOMAX, find the value that causes the motor to spin 180 degrees.  For more details, see 10:56 in the video.

## Servo_Test_v1.ino
A script that simply turns the motor 0->180->0 degrees.  This is a proof of concept script to make sure we can properly control the motors.  Once SERVOMIN, SERVOMAX have been configured, there is a simple mapping function that can be used to control the number of degrees the motor turns.  See 15:12 in the tutorial video for more information.
