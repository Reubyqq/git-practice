# git-practice
just a practice
Hello Mission to Mars!, how is your day/night?

## Story 1: Building the Rover
I found the coding part *easy* once I adjusted to it. The *tricky* sector was setting up Git, but I am very glad I learned it.

### Code for Story 1: Onboard LED Flash

The code below successfully meets the criteria of flashing the onboard LED on and off for 1 second.

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

#define ledRed 12
#define ledGreen 13
```cpp
void setup() {
  pinMode(ledRed, OUTPUT);
  pinMode(ledGreen, OUTPUT);
}

void loop() {
  digitalWrite(ledRed, 1);
  digitalWrite(ledGreen, 0);
  delay(1000); // Red ON, Green OFF
  digitalWrite(ledRed, 0);
  digitalWrite(ledGreen, 1);
  delay(1000); // Red OFF, Green ON
}
