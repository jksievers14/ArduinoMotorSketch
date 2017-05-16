# ArduinoMotorSketch
/*
 Adafruit Arduino - Lesson 14. Knob
 */
#include <Servo.h>

int potPin = 0;
int servoPin = 9;
Servo servo;


void setup() 
  // put your setup code here, to run once:
{
  servo.attach(servoPin);
}

void loop() {
  // put your main code here, to run repeatedly:

  // scan from 0 to 180
  
  int reading = analogRead(potPin);
  int angle =reading / 6;
  servo.write(angle);
  
  for(angle = 0; angle < 180; angle++)
{
  servo.write(angle);
  delay(15);
  }
  // now scan back from 180 to 0 degrees
  for(angle = 180; angle > 0; angle--)
  {
    servo.write(angle);
    delay(15);
  }
}
  
