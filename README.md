- š Hi, Iām @Thida23
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
Thida23/Thida23 is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
#include <SoftwareSerial.h>
#include <Servo.h>
 
SoftwareSerial mySerial(10, 11); // RX | TX
 
Servo servo;  
 
int servoPin = 9;
int servoAngle = 0;   // servo position in degrees
 
char command;
 
void setup() {
   Serial.begin(9600);
   mySerial.begin(9600);
   Serial.println("You're connected via Bluetooth");
   servo.attach(servoPin);
 }
 
 
void loop() {
  if (mySerial.available())
   {
    command=(mySerial.read());
    if (command=='1')
    {
      Serial.println("Servo motor to 90 degrees");
      servo.write(90);              
      delay(500);                  
     
    }
 
    else if (command=='2')
    {
      Serial.println("Servo motor to 0 degrees");
      servo.write(0);              
      delay(500);
    }
 
  }
}
 
