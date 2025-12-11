# git-practice
just a practice
Hello Mission to Mars!, how is your day/night?

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
**Story 5: **
i have tried altering the code to make the rover snake along as such
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

