// Pin Definitions
const int ledPin = 13;    // Built-in LED on the Arduino Nano 33 IoT
const int buttonPin = 2;  // Pin for the push button

// Morse Code for each letter in "Deepanshu"
String nameMorseCode[] = {
  "-..",    // D
  ".",      // E
  ".",      // E
  ".--.",   // P
  ".-",     // A
  "-.",     // N
  "...",    // S
  "....",   // H
  "..-"     // U
};

int nameLength = sizeof(nameMorseCode) / sizeof(nameMorseCode[0]);  // Calculate the number of letters

void setup() {
  pinMode(ledPin, OUTPUT);      // Set LED pin as output
  pinMode(buttonPin, INPUT_PULLDOWN);  // Set button pin as input with internal pull-down resistor
  Serial.begin(9600);           // Initialize serial communication for debugging (optional)
}

void loop() {
  // Check if the button is pressed
  if (digitalRead(buttonPin) == HIGH) {
    delay(50);  // Debounce delay to avoid multiple triggers
    blinkMorseCode();  // Call function to blink the name in Morse code
  }
}

void blinkMorseCode() {
  // Loop through each letter in the name
  for (int i = 0; i < nameLength; i++) {
    String morseChar = nameMorseCode[i];  // Get the Morse code for the current letter
    
    // Loop through each symbol (dot or dash) in the letter
    for (int j = 0; j < morseChar.length(); j++) {
      if (morseChar[j] == '.') {
        blinkDot();  // Blink a dot
      } else if (morseChar[j] == '-') {
        blinkDash(); // Blink a dash
      }
      delay(500);  // Wait between symbols in the same letter
    }
    delay(600);  // Wait between letters
  }
  delay(700);  // Wait before repeating the sequence or ending
}

void blinkDot() {
  digitalWrite(ledPin, HIGH);  // Turn the LED on
  delay(200);          // Wait for the duration of a dot
  digitalWrite(ledPin, LOW);   // Turn the LED off
}

void blinkDash() {
  digitalWrite(ledPin, HIGH);  // Turn the LED on
  delay(600);         // Wait for the duration of a dash
  digitalWrite(ledPin, LOW);   // Turn the LED off
}
// Pin Definitions
const int ledPin = 13;    // Built-in LED on the Arduino Nano 33 IoT
const int buttonPin = 2;  // Pin for the push button

// Morse Code for each letter in "Deepanshu"
String nameMorseCode[] = {
  "-..",    // D
  ".",      // E
  ".",      // E
  ".--.",   // P
  ".-",     // A
  "-.",     // N
  "...",    // S
  "....",   // H
  "..-"     // U
};

int nameLength = sizeof(nameMorseCode) / sizeof(nameMorseCode[0]);  // Calculate the number of letters

void setup() {
  pinMode(ledPin, OUTPUT);      // Set LED pin as output
  pinMode(buttonPin, INPUT_PULLDOWN);  // Set button pin as input with internal pull-down resistor
  Serial.begin(9600);           // Initialize serial communication for debugging (optional)
}

void loop() {
  // Check if the button is pressed
  if (digitalRead(buttonPin) == HIGH) {
    delay(50);  // Debounce delay to avoid multiple triggers
    blinkMorseCode();  // Call function to blink the name in Morse code
  }
}

void blinkMorseCode() {
  // Loop through each letter in the name
  for (int i = 0; i < nameLength; i++) {
    String morseChar = nameMorseCode[i];  // Get the Morse code for the current letter
    
    // Loop through each symbol (dot or dash) in the letter
    for (int j = 0; j < morseChar.length(); j++) {
      if (morseChar[j] == '.') {
        blinkDot();  // Blink a dot
      } else if (morseChar[j] == '-') {
        blinkDash(); // Blink a dash
      }
      delay(500);  // Wait between symbols in the same letter
    }
    delay(600);  // Wait between letters
  }
  delay(700);  // Wait before repeating the sequence or ending
}

void blinkDot() {
  digitalWrite(ledPin, HIGH);  // Turn the LED on
  delay(200);          // Wait for the duration of a dot
  digitalWrite(ledPin, LOW);   // Turn the LED off
}

void blinkDash() {
  digitalWrite(ledPin, HIGH);  // Turn the LED on
  delay(600);         // Wait for the duration of a dash
  digitalWrite(ledPin, LOW);   // Turn the LED off
}
