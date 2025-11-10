# Welcome to the World of Arduino!

Arduino is an open-source electronics platform based on easy-to-use hardware and software. It's intended for anyone making interactive projects. Whether you're a student, artist, designer, or hobbyist, Arduino offers a low-cost, simple way to build devices that interact with their environment using sensors and actuators.

## What is an Arduino Board?

An Arduino board is a microcontroller, which is like a tiny, simplified computer. You can program it to read inputs—like light on a sensor, a finger on a button, or a Twitter message—and turn it into an output, such as activating a motor, turning on an LED, or publishing something online.

The most common Arduino board is the **Arduino UNO**. It has:

-   **Digital Pins:** These pins can be either ON (HIGH) or OFF (LOW). They are great for simple inputs and outputs, like turning an LED on or off.
-   **Analog Pins:** These pins can read a range of values, which is useful for reading sensors that have a variable output, like a temperature sensor.
-   **A USB Port:** This is used to connect the Arduino to your computer for programming and power.
-   **A Power Jack:** For external power when your Arduino is not connected to a computer.
-   **A Microcontroller Chip:** The "brain" of the board. On the UNO, this is the ATmega328P.

## The Structure of an Arduino Sketch

An Arduino program is called a "sketch." Every sketch has two essential parts:

### 1. `setup()`

This function runs once, at the very beginning, when your Arduino board is powered on or reset.

```cpp
void setup() {
  // put your setup code here, to run once:
}
```

**Purpose**: To initialize variables, pin modes, and start using libraries. It's the preparation phase of your sketch.

**Parameters**: None.

**Example**:

```cpp
void setup() {
  // Set pin 13 as an output for the built-in LED
  pinMode(13, OUTPUT);
}
```

### 2. `loop()`

After `setup()` has finished, the `loop()` function runs over and over again, allowing your program to change and respond.

```cpp
void loop() {
  // put your main code here, to run repeatedly:
}
```

**Purpose**: This is where the main logic of your program goes. It will run continuously as long as the Arduino has power.

**Parameters**: None.

**Example**:

```cpp
void loop() {
  digitalWrite(13, HIGH);   // Turn the LED on
  delay(1000);              // Wait for a second
  digitalWrite(13, LOW);    // Turn the LED off
  delay(1000);              // Wait for a second
}
```

## Common Arduino Functions

Here are some of the most common functions you'll use in your Arduino sketches.

### 1. `pinMode()`

Configures the specified pin to behave either as an input or an output.

```cpp
pinMode(pin, mode);
```

**Purpose**: To set the mode of a pin (e.g., to read from a sensor or to control an LED).

**Parameters**:

- `pin` (required): The number of the pin you want to configure.
- `mode` (required): Can be `INPUT`, `OUTPUT`, or `INPUT_PULLUP`.

**Example**:

```cpp
void setup() {
  pinMode(13, OUTPUT); // Sets pin 13 to be an output
  pinMode(2, INPUT);   // Sets pin 2 to be an input
}
```

### 2. `digitalWrite()`

Writes a HIGH or a LOW value to a digital pin.

```cpp
digitalWrite(pin, value);
```

**Purpose**: To turn a digital pin on or off.

**Parameters**:

- `pin` (required): The number of the pin.
- `value` (required): `HIGH` or `LOW`.

**Example**:

```cpp
void loop() {
  digitalWrite(13, HIGH); // Turns the LED on
}
```

### 3. `digitalRead()`

Reads the value from a specified digital pin, either HIGH or LOW.

```cpp
digitalRead(pin);
```

**Purpose**: To read the state of a digital input, like a button press.

**Parameters**:

- `pin` (required): The number of the pin you want to read.

**Example**:

```cpp
void loop() {
  int buttonState = digitalRead(2); // Reads the state of the button on pin 2
}
```

### 4. `analogRead()`

Reads the value from a specified analog pin.

```cpp
analogRead(pin);
```

**Purpose**: To read the value from an analog sensor. The Arduino board has a 10-bit analog to digital converter, so this function returns a value from 0 to 1023.

**Parameters**:

- `pin` (required): The number of the analog pin to read from (e.g., `A0`, `A1`).

**Example**:

```cpp
void loop() {
  int sensorValue = analogRead(A0); // Reads the value from the sensor on analog pin A0
}
```

### 5. `analogWrite()`

Writes an analog value (PWM wave) to a pin.

```cpp
analogWrite(pin, value);
```

**Purpose**: To dim an LED or control the speed of a motor. Not all digital pins support `analogWrite()`. On the Arduino Uno, these are pins 3, 5, 6, 9, 10, and 11.

**Parameters**:

- `pin` (required): The number of the pin.
- `value` (required): The duty cycle, between 0 (always off) and 255 (always on).

**Example**:

```cpp
void setup() {
  pinMode(9, OUTPUT);
}

void loop() {
  analogWrite(9, 128); // Sets the LED on pin 9 to half brightness
}
```

### 6. `delay()`

Pauses the program for the amount of time (in milliseconds) specified as a parameter.

```cpp
delay(ms);
```

**Purpose**: To create a pause in your program.

**Parameters**:

- `ms` (required): The number of milliseconds to pause.

**Example**:

```cpp
void loop() {
  digitalWrite(13, HIGH);
  delay(1000); // Waits for 1 second
  digitalWrite(13, LOW);
  delay(1000);
}
```

### 7. `Serial.begin()`

Sets the data rate in bits per second (baud) for serial data transmission.

```cpp
Serial.begin(speed);
```

**Purpose**: To start serial communication, so you can send and receive data to and from the computer.

**Parameters**:

- `speed` (required): The baud rate, typically 9600.

**Example**:

```cpp
void setup() {
  Serial.begin(9600);
}
```

### 8. `Serial.print()`

Prints data to the serial port as human-readable ASCII text.

```cpp
Serial.print(data);
```

**Purpose**: To send data to the Serial Monitor for debugging or display.

**Parameters**:

- `data` (required): The data to print (e.g., a string, a variable).

**Example**:

```cpp
void loop() {
  int sensorValue = analogRead(A0);
  Serial.print("Sensor value: ");
  Serial.print(sensorValue);
}
```

### 9. `Serial.println()`

Prints data to the serial port as human-readable ASCII text followed by a carriage return and newline.

```cpp
Serial.println(data);
```

**Purpose**: Same as `Serial.print()`, but adds a new line at the end.

**Parameters**:

- `data` (required): The data to print.

**Example**:

```cpp
void loop() {
  int sensorValue = analogRead(A0);
  Serial.println(sensorValue);
  delay(100);
}
```

## Your First Sketch: Blinking an LED

The "Blink" sketch is the "Hello, World!" of the hardware world. It's a simple program that turns the built-in LED on an Arduino board on and off.

### The Code

```cpp
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}
```

### How it Works

1.  **`setup()`**: In the `setup()` function, we use `pinMode(LED_BUILTIN, OUTPUT);` to tell the Arduino that we want to use the built-in LED pin as an output. `LED_BUILTIN` is a constant that is the number of the pin connected to the on-board LED (usually pin 13).

2.  **`loop()`**: The `loop()` function is where the action happens.
    *   `digitalWrite(LED_BUILTIN, HIGH);` turns the LED on by sending 5 volts to the pin.
    *   `delay(1000);` pauses the program for 1000 milliseconds (1 second).
    *   `digitalWrite(LED_BUILTIN, LOW);` turns the LED off by sending 0 volts to the pin.
    *   `delay(1000);` pauses the program for another second.

This cycle repeats indefinitely, making the LED blink.
