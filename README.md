# NotSoBasicArduino

## Hello Functions

<img src="https://hackster.imgix.net/uploads/attachments/208605/radar.jpg?auto=compress%2Cformat&w=900&h=675&fit=min" width="392px"/>
 
 ## What are Hello Functions?
 - A Hello Function is basic code for programming a Radar. You can use these functions to find the distance and location of an object.  I also used an ultrasonic sensor and a servo, so that the Sensor can swivle around to see whats next to it (but unfortunetly not behind).
<img src="https://hackster.imgix.net/uploads/image/file/150528/IMG_20160407_141058.jpg?auto=compress%2Cformat&w=740&h=555&fit=max" width="392px"/>
-look how cute it looks!

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
     printDistance();
  }

  for(int i=165;i>15;i--)
  {
    servo.write(i);
    delay(100);
    distance=calculateDistance();
 printDistance();
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


void printDistance(){
    Serial.print(i);
    Serial.print(",");
    Serial.print(distance);
    Serial.println(".");
}
-(this was NOT easy)

## What/I learned...
  * I learned how to calculate distance so if it gets to a certain distance from something.
 * I learned how to create an ultrasonic radar.
*This assignment teaches you how to use an ultra-sonic sencor and a servo.
 *this assignment also gave me and my group the inspiration for THOMAS THE DANK TANK.
 __________________________________________________________________________________________________________________________________
 
 # New Ping.()ino
 
 <img src="https://www.real.discount/wp-content/uploads/2017/10/1187666_c150.jpg" width="392px"/>

 # How to

https://www.real.discount/offer/arduino-radar-step-by-step-guide/
-mr.H and dylan helped
 
 ## What is NewPing.()?
  - New Ping() is a code you can use to simplify things like a hello function, or any funtion for that matter
  but helps by simplifying the code all the way down so you just have to type NewPing().
  - For this assignment you basicly have to do hello funtions but simplifying it using new ping, plug it in to a servo to make it change direction. This might sound harder than hello functions, but with the NewPing() code, it's a breeze. 
  
 
 ### Code
 
#include <NewPing.h>
#include <Servo.h>
Servo myservo;
#define TRIGGER_PIN 7
#define ECHO_PIN 6
#define MAX_DISTANCE 200

int cm = 0;
NewPing myHCSR04(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);
 
void setup() {
 Serial.begin(9600);
 myservo.attach(9);
} 
void loop() {
    cm = myHCSR04.ping_cm();
     Serial.println(cm);
     delay(50); 
    if ( cm != 0 && cm < 150)
  {
    if (cm < 10) {
      myservo.write(100);
    }
    if (cm > 10) {
       myservo.write(80);
    }
  }
}

-(see how much easyer it is?)

<img src="https://hackster.imgix.net/uploads/attachments/208605/radar.jpg?auto=compress%2Cformat&w=900&h=675&fit=min" width="392px"/>


## What/I Learned...

*before this assighnment I really didnt understand functions, but thinking of newping as a library and a funtion as a book really helped me out
*OH MY GOD ARDUINO IS SO MUUCH EASER


__________________________________________________________________________________________________________________________________
-PS
-credit to dylan for images and code (we made all the assighnments together)
-https://github.com/dhensle63/NotSoBasicArduino/blob/master/README.md
