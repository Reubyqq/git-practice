# git-practice
just a practice
Hello Mission to Mars!, how is your day/night?

## Story 1: Building the Rover
I found the coding part **easy** once I adjusted to it. The **tricky** sector was setting up Git, but I am very glad I learned it.

### Code for Story 1: Arduino LED Flash

The code below **should** successfully meets the criteria of flashing the onboard LED on and off for 1 second.

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
