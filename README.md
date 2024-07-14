# ARDUINO

## Common arduini functions

### 1.  `pinMode(pin, mode)`

Sets the mode of a specified pin to either input or output.

```cpp
pinMode(13, OUTPUT);
``` 

-   **Purpose:** Configures the specified pin to behave either as an input or an output.
-   **Parameters:**
    -   `pin`: The number of the pin whose mode you wish to set.
    -   `mode`: `INPUT`, `OUTPUT`, or `INPUT_PULLUP`.

### 2.  `digitalWrite(pin, value)`

Writes a HIGH or a LOW value to a digital pin.

```cpp 
digitalWrite(13, HIGH);
``` 

-   **Purpose:** Sets the digital pin to HIGH or LOW.
-   **Parameters:**
    -   `pin`: The number of the pin.
    -   `value`: `HIGH` or `LOW`.

### 3.  `digitalRead(pin)`

Reads the value from a specified digital pin, either HIGH or LOW.

```cpp
int buttonState = digitalRead(2);
``` 

-   **Purpose:** Reads the value from a specified digital pin.
-   **Parameters:**
    -   `pin`: The number of the pin to read from.

### 4.  `analogRead(pin)`

Reads the value from a specified analog pin.

```cpp
int sensorValue = analogRead(A0);
``` 

-   **Purpose:** Reads the value from the specified analog pin.
-   **Parameters:**
    -   `pin`: The number of the analog pin to read from.

### 5.  `analogWrite(pin, value)`

Writes an analog value (PWM wave) to a pin.

```cpp
analogWrite(9, 128);
``` 

-   **Purpose:** Writes an analog value to a specified pin.
-   **Parameters:**
    -   `pin`: The number of the pin.
    -   `value`: The duty cycle: between 0 (always off) and 255 (always on).

### 6.  `delay(ms)`

Pauses the program for the amount of time (in milliseconds) specified as parameter.

```cpp
delay(1000);
``` 

-   **Purpose:** Pauses the program for a specified amount of time.
-   **Parameters:**
    -   `ms`: The number of milliseconds to pause.

### 7.  `millis()`

Returns the number of milliseconds since the Arduino board began running the current program.

```cpp
unsigned long time = millis();
``` 

-   **Purpose:** Returns the number of milliseconds since the program started.
-   **Parameters:** None.

### 8.  `Serial.begin(baudrate)`

Sets the data rate in bits per second (baud) for serial data transmission.

```cpp
Serial.begin(9600);
``` 

-   **Purpose:** Initializes serial communication at a specified baud rate.
-   **Parameters:**
    -   `baudrate`: The baud rate (speed of communication).

### 9.  `Serial.print(data)`

Prints data to the serial port as human-readable ASCII text.

```cpp
Serial.print("Hello, world!");
``` 

-   **Purpose:** Prints data to the serial port.
-   **Parameters:**
    -   `data`: The data to print (e.g., a string, a variable).

### 10.  `Serial.println(data)`

Prints data to the serial port as human-readable ASCII text followed by a carriage return character and a newline character.

```cpp
Serial.println("Hello, world!");
``` 

-   **Purpose:** Prints data to the serial port followed by a new line.
-   **Parameters:**
    -   `data`: The data to print (e.g., a string, a variable).

