# Mission to Mars
This is my repo for all of my stories!

## Story 1: Building the Rover
I found the coding part *easy* once I adjusted to it. The *tricky* sector was setting up Git, but I am very glad I learned it.

### Code for Story 1: Onboard LED Flash


```cpp
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); 
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000);
}
```
**Story 2: Alternate LED Flash**
The task was to get two external LEDs (Red and Green) to flash alternately every 1 second (1000ms). This Was very tricky for me but i eventually learnt it

**Code for Story 2**

```cpp
void setup() {
  pinMode(ledRed, OUTPUT);
  pinMode(ledGreen, OUTPUT);
}

void loop() {
  digitalWrite(ledRed, 1);
  digitalWrite(ledGreen, 0);
  delay(1000); 
  digitalWrite(ledRed, 0);
  digitalWrite(ledGreen, 1);
  delay(1000); 
}
```
**Story 3: Forward, stop, reverse sequence**
The task was to get lights to symbolize a rover moving forward(5), stop(1), and reverse(2). This looked complicated but i believe story 2 helped improve my problem solving skills
**Code for Story 3**

```cpp
int rl=13, gl=12, yl=11, yr=9, rr=8, gr=7;

void setup(){
  pinMode(rl,1);pinMode(gl,1);pinMode(yl,1);
  pinMode(yr,1);pinMode(rr,1);pinMode(gr,1);
}

void loop(){
  digitalWrite(gl,1);digitalWrite(gr,1);
  delay(5000);
  digitalWrite(gl,0);digitalWrite(gr,0);

  digitalWrite(yl,1);digitalWrite(yr,1);
  delay(1000);
  digitalWrite(yl,0);digitalWrite(yr,0);

  digitalWrite(rl,1);digitalWrite(rr,1);
  delay(2000);
  digitalWrite(rl,0);digitalWrite(rr,0);
}
```
**Story 4: Functions**
**Code for Story 4**

```cpp
int
 rl=13, gl=12, yl=11, yr=9, rr=8, gr=7;

void a(int p, int s){
  digitalWrite(p, s);
}

void b(long t){
  delay(t);
}

void setup(){
  pinMode(rl, 1);
  pinMode(gl, 1);
  pinMode(yl, 1);
  pinMode(yr, 1);
  pinMode(rr, 1);
  pinMode(gr, 1);
}

void loop(){
  a(gl, 1);
  a(gr, 1);
  b(5000);
  a(gl, 0);
  a(gr, 0);

  a(yl, 1);
  a(yr, 1);
  b(1000);
  a(yl, 0);
  a(yr, 0);

  a(rl, 1);
  a(rr, 1);
  b(2000);
  a(rl, 0);
  a(rr, 0);
}
```
**Story 5:**
i have tried altering the code to make the rover snake along as such, this was *tricky* becasue i had to get my head around the process
**Code for Story 5**

```cpp
int a=13,b=12,c=11,d=9,e=8,f=7;

void g(int h,int i){digitalWrite(h,i);}
void j(long k){delay(k);}

void setup(){
pinMode(a,1);pinMode(b,1);pinMode(c,1);pinMode(d,1);pinMode(e,1);pinMode(f,1);
}

void loop(){
g(b,1);g(f,1);j(2000);g(b,0);g(f,0);
g(c,1);g(d,1);j(2000);g(c,0);g(d,0);
g(a,1);g(e,1);j(2000);g(a,0);g(e,0);
g(c,1);g(d,1);j(2000);g(c,0);g(d,0);
g(a,1);g(e,1);j(2000);g(a,0);g(e,0);
}
```
**Story 6:**
this code succesfully counts the pushes of the buttons aswell as stops the process once it reaches 10 (i have changed the numbers because im *not* willing to press over 400 times)
**Code for Story 6**

```cpp
const int LEFT_FEEDBACK = 2;
const int RIGHT_FEEDBACK = 3;
const int LEFT_MOTOR = 4;
const int RIGHT_MOTOR = 5;


volatile int leftCounter = 0;
volatile int rightCounter = 0;

void setup() {
  Serial.begin(115200);

  
  pinMode(LEFT_MOTOR, OUTPUT);
  pinMode(RIGHT_MOTOR, OUTPUT);

  
  digitalWrite(LEFT_MOTOR, HIGH);
  digitalWrite(RIGHT_MOTOR, HIGH);

 
  attachInterrupt(digitalPinToInterrupt(LEFT_FEEDBACK), LeftMotorISR, RISING);
  attachInterrupt(digitalPinToInterrupt(RIGHT_FEEDBACK), RightMotorISR, RISING);
}

void loop() {
  
  Serial.print("Left: ");
  Serial.println(leftCounter);
  Serial.print("Right: ");
  Serial.println(rightCounter);

  
  if (leftCounter >= 10 || rightCounter >= 10) {
    
   
    digitalWrite(LEFT_MOTOR, LOW);
    digitalWrite(RIGHT_MOTOR, LOW);
    
    Serial.println("Target reached. Stopping.");
    
    
    exit(0);
  }
}


void LeftMotorISR() {
  leftCounter++;
}

void RightMotorISR() {
  rightCounter++;
}
```
**Story 7:**
i have done as story 7 has instructed me and i have used the codes provided in Arduino IDE, i found Arduino surprisingly straight forward except the way it outputs did confuse me
**Code for Story 7**

```cpp
#include <NewPing.h> 

#define TRIGGER_PIN 4
#define ECHO_PIN 5
#define MAX_DISTANCE 200 
NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

int LF=5, LB=6, RF=9, RB=10; 

void setup() {
  pinMode(LF, OUTPUT); 
  pinMode(LB, OUTPUT);
  pinMode(RF, OUTPUT); 
  pinMode(RB, OUTPUT); 
  
  Serial.begin(9600); 
}

void loop() {
 
  digitalWrite(LF, HIGH); digitalWrite(RF, HIGH);
  delay(2000);

 
  for (int i = 0; i < 4; i++) {
    
    digitalWrite(LF, HIGH); digitalWrite(RF, HIGH);
    delay(1500);

    
    digitalWrite(LB, HIGH); digitalWrite(RF, HIGH); 
    delay(850);
  }

  
  for (int i = 0; i < 4; i++) {
   
    digitalWrite(LF, HIGH); digitalWrite(RF, HIGH);
    delay(1500);

   
    digitalWrite(LF, HIGH); digitalWrite(RB, HIGH); 
    delay(850);
  }

  
  digitalWrite(LB, HIGH); digitalWrite(RB, HIGH);
  delay(2000);
  
  
  digitalWrite(LF, LOW); digitalWrite(RF, LOW); 
  digitalWrite(LB, LOW); digitalWrite(RB, LOW);

 
  while(true); 
}
```
**Story 8:**
i have used what ive learnt and applied this to the instructions, i am *fairly* confident i have succeeded in this 
**Code for Story 8**

```cpp
int trigPin = 9;
int echoPin = 10;
int leftMotorForward = 3;
int leftMotorBackward = 4;
int rightMotorForward = 5;
int rightMotorBackward = 6;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(leftMotorForward, OUTPUT);
  pinMode(leftMotorBackward, OUTPUT);
  pinMode(rightMotorForward, OUTPUT);
  pinMode(rightMotorBackward, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  long duration;
  int distance;

  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;
```


