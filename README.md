# PCA9685---Servo-Motor-Controller-Interface

Test code for the Servo Motors.  The following tutorial contains information about the servoboard, the library, and its usage: https://www.youtube.com/watch?v=y8X9X10Tn1k

In order to run these scripts, the PCA685 arduino library must be properly downloaded and set up: https://github.com/adafruit/Adafruit-PWM-Servo-Driver-Library.  See 5:41 in the video for instructions.  Before using/testing a new motor, make sure to calibrate it with the servo_config.ino script.

## servo_config.ino
Used to configure SERVOMIN and SERVOMAX for each motor.  SERVOMIN and SERVOMAX represent duty cycles out of 4096.  To find SERVOMIN, find the lowest possible value before the motor begins to hum (try to start at a higher value, since running a servo with an extremely low duty cycle for too long can be damaging). To find SERVOMAX, find the value that causes the motor to rotate 180 degrees.  For more details, see 10:56 in the video.

## Servo_Test_v1.ino
A script that simply rotates the motor 0->180->0 degrees.  This is a proof of concept script to make sure we can properly control the motors.  Once SERVOMIN, SERVOMAX have been configured, there is a simple mapping function that can be used to control the number of degrees the motor turns.  See 15:12 in the tutorial video for more information.

The PCA9685 board can support 16 servomotors.  To test multiple motors at the same time, modify the "num_servos_tested" define statement on line 20.  This will cause each motor from channel 0 to num_servos_test-1 to rotate.  Before connecting more motors, make sure SERVOMIN and SERVOMAX have been configured individually for each motor.
