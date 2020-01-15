# NotSoBasicArduino

## Hello Functions

<img src="https://hackster.imgix.net/uploads/attachments/208605/radar.jpg?auto=compress%2Cformat&w=900&h=675&fit=min" width="392px"/>

# How to...

https://create.arduino.cc/projecthub/ryujenny3/servo-motor-ultrasonic-sensor-f951fe
 https://howtomechatronics.com/projects/arduino-radar-project/
 
 ## What are Hello Functions?
 - A Hello Function is basic code for programming a Radar. You can use these functions to find the distance and location of an object.  I also used an ultrasonic sensor and a servo, so that the Sensor can swivle around to see whats next to it (but unfortunetly not behind).

### -Code

#include<Servo.h>
int trigPin=2;
int echoPin=3;

long duration;
int distance;
Servo servo;

void setup()
{
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
  servo.attach(9);
}

void loop()
{
  for(int i=15;i<=165;i++)
  {
    servo.write(i);
    delay(100);
    distance=calculateDistance();
    
    Serial.print(i);
    Serial.print(",");
    Serial.print(distance);
    Serial.println(".");
  }

  for(int i=165;i>15;i--)
  {
    servo.write(i);
    delay(100);
    distance=calculateDistance();
    
    Serial.print(i);
    Serial.print(",");
    Serial.print(distance);
    Serial.println(".");
  }
}
int calculateDistance()
{
  digitalWrite(trigPin,LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin,HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin,LOW); 
  duration=pulseIn(echoPin,HIGH);
  distance=duration*0.034/2;
  return distance;
}  

<img src="https://hackster.imgix.net/uploads/image/file/150528/IMG_20160407_141058.jpg?auto=compress%2Cformat&w=740&h=555&fit=max" width="392px"/>

## What/I learned...
 
 * This assignment teaches you how to use a ultra-sonic sencor and a servo.
 * I learned how to create a simple radar and now know certain things that it's used for.
 * I learned how to calculate distance so if it gets to a certain distance from something, it could react to it.
 *this assignment also gave me and my group the inspiration for THOMAS THE DANK TANK.
 __________________________________________________________________________________________________________________________________
 
 # New Ping.()ino
 
 <img src="https://www.real.discount/wp-content/uploads/2017/10/1187666_c150.jpg" width="392px"/>

 # How to

https://www.real.discount/offer/arduino-radar-step-by-step-guide/
 
 ## What is NewPing.()?
  - New Ping() is a code you can use to simplify things like a hello function, or any funtion for that matter
  but helps by simplifying the code all the way down so you just have to type NewPing().
  - For this assignment you basicly have to do hello funtions but simplifying it using new ping, plug it in to a servo to make it change direction. This might sound harder than hello functions, but with the NewPing() code, it's a breeze. 
  
 
 ### Code
 
 #include <Servo.h>

#include <NewPing.h>

const int ServoPin = 9;
const int TriggerPin = 3;
const int EchoPin = 2;

// 100 = maxDistance
NewPing  sonar(TriggerPin, EchoPin, 100);
Servo servo;

void setup() {
  Serial.begin(9600);
    servo.attach(ServoPin);
}

void loop(){
    int cm = sonar.ping_cm();
  Serial.println(cm);

int angle = map(cm, 2, 15, 15, 165 )
  servo.write(angle);

    delay(60);
}
-(see how much easyer it is?)

<img src="https://hackster.imgix.net/uploads/attachments/208605/radar.jpg?auto=compress%2Cformat&w=900&h=675&fit=min" width="392px"/>


## What/I Learned...

* This assignment is a simpler hello functions but everytime the ultra S. reads someone or something, the servo goes the other direction.
* I learned that NewPing() can be used to simplify codes for me.


__________________________________________________________________________________________________________________________________
