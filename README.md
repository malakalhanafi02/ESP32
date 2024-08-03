# 💡LED Blinking with Pushbutton Control

This project demonstrates how to control an LED using an ESP32 and a pushbutton. The LED will blink at a regular interval by default, and when the pushbutton is pressed, the LED will stay on.



https://github.com/user-attachments/assets/52376a8a-d446-453b-a457-8342c4c5ad2c



## Components
- ESP32
- LED 
- Resistor (220 ohms)
- Pushbutton
- Breadboard
- Jumper wires

## Connections

#### LED
- Connect the longer leg (anode) of the LED to GPIO23 on the ESP32 through a 220-ohm resistor.
- Connect the shorter leg (cathode) of the LED to GND on the ESP32.

#### Pushbutton
- Connect one side of the pushbutton to GPIO22 on the ESP32.
- Connect the other side of the pushbutton to GND.

## Code
- The setup function initializes the serial communication and sets the pin modes for the LED and pushbutton.
- The loop function continuously reads the state of the pushbutton. If the pushbutton is pressed (buttonState is LOW), the LED is turned on. Otherwise, the LED blinks with a 1-second interval.

```bash
const int ledPin = 23;    // LED pin
const int buttonPin = 22; // Pushbutton pin

void setup() {
  // Initialize serial communication
  Serial.begin(115200);
  
  // Set the LED pin as output
  pinMode(ledPin, OUTPUT);
  
  // Set the button pin as input with internal pull-up resistor
  pinMode(buttonPin, INPUT_PULLUP);
}

void loop() {
  // Read the state of the pushbutton
  int buttonState = digitalRead(buttonPin);
  
  // If the button is pressed, turn on the LED
  if (buttonState == LOW) {
    digitalWrite(ledPin, HIGH);
  } else {
    // Otherwise, blink the LED
    digitalWrite(ledPin, HIGH);
    delay(500);
    digitalWrite(ledPin, LOW);
    delay(500);
  }
}

```
## Explanation

- ESP32: The microcontroller reads the state of the pushbutton and controls the LED.
- LED: Lights up to indicate its state (on or blinking).
- Pushbutton: Used to control the state of the LED.


