# Color Detection Using TCS3200 Sensor

This project is an Arduino-based color detection system that detects RED, GREEN, and BLUE colors using a TCS3200 color sensor and displays the detected color on a 16×2 I2C LCD.

## Working

- White light falls on the object.
- The object reflects specific RGB components of the light.
- The TCS3200 sensor receives the reflected light.
- The sensor contains photodiodes with Red, Green, and Blue filters.
- The S2 and S3 pins are used to select one color filter at a time.
- The selected photodiodes convert the received light into electrical current.
- The current is proportional to the intensity of the detected color.
- The TCS3200 converts the current into a frequency (square-wave output).
- Higher light intensity produces a higher output frequency.
- Lower light intensity produces a lower output frequency.
- The output frequency is provided through the OUT pin.
- The Arduino Uno reads the frequency through a digital input pin.
- The Arduino measures the pulse duration using `pulseIn()`.
- The RGB readings are compared to determine the color with the highest intensity.
- The detected color is identified as RED, GREEN, or BLUE.
- The detected color and RGB readings are displayed on the LCD.

## Components Used

- Arduino Uno
- TCS3200 Color Sensor
- 16×2 I2C LCD
- Breadboard
- Jumper Wires

## Pin Connections

| TCS3200 | Arduino Uno |
|---|---|
| S0 | 8 |
| S1 | 9 |
| S2 | 11 |
| S3 | 12 |
| OUT | 10 |

## LCD

The LCD uses the I2C interface with address `0x27`.

If the LCD does not work, the address may need to be changed to `0x3F`.

## Output

The system detects:

- RED
- GREEN
- BLUE
- UNCLEAR

The RGB sensor readings and detected color are displayed on the 16×2 I2C LCD.

## Library Required

This project uses the `LiquidCrystal_I2C` library.

Install the library through the Arduino IDE Library Manager before uploading the code.

## How to Run

1. Connect the TCS3200 sensor and LCD to the Arduino Uno.
2. Open the `color_sensor_lcd.ino` file in Arduino IDE.
3. Install the `LiquidCrystal_I2C` library.
4. Select the correct Arduino board and COM port.
5. Upload the code to the Arduino Uno.
6. Place a colored object in front of the TCS3200 sensor.
7. The sensor detects the color and displays the result on the LCD.
