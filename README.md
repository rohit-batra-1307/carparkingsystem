# RFID Based Car Parking System

## Overview

This project is an RFID-based car parking system designed using the 8051 microcontroller. The system allows authorized users to access a parking area by swiping an RFID card. The microcontroller reads the card information, verifies it against a predefined database, and controls the motor to open or close the parking gate accordingly. The project also includes an LCD for displaying messages to the user.

## Components Used

- **8051 Microcontroller (AT89C51)**
- **RFID Reader and RFID Tags**
- **LCD Display (16x2)**
- **DC Motor for Gate Control**
- **Miscellaneous: Resistors, Capacitors, Crystal Oscillator, etc.**

## Features

1. **RFID Authentication**:
   - The system reads the RFID card data and checks if it matches a predefined set of authorized users.
   
2. **Motor Control**:
   - The system controls the motor to open or close the gate based on the authentication result.

3. **LCD Display**:
   - Provides real-time feedback and instructions to the user.
   - Displays messages such as "Swipe Your Card", "Access Granted", "Access Denied", "Door Opening", and "Door Closing".

## Functional Description

### Initialization
- The system initializes the LCD and serial communication during startup.
- Displays welcome messages like "RFID BASED CAR PARKING SYSTEM" and "MADE BY TEAM 26".

### Main Operation Loop
- The system continuously waits for an RFID card swipe.
- Upon detecting a card swipe, it reads the RFID data and echoes it back for verification.

### Authentication
- The system checks the RFID data against a predefined authorized user ID.
- If the ID matches, the system displays "ASSOCIATION MEMBER" and the user's name on the LCD.
- If the ID does not match, it displays "OUTSIDE PERSON" and "NO SLOT FOR YOU".

### Motor Control
- For authorized users, the system activates the motor to open the gate, displays "DOOR OPENING" and "ALLOW INSIDE".
- After a delay, it stops the motor and then activates it in the reverse direction to close the gate, displaying "DOOR CLOSING".

## Code Structure

- **`void main()`**: Main function that initializes the system and handles the main operational loop.
- **`void serial_init()`**: Initializes the serial communication for reading RFID data.
- **`void lcd_init()`**: Initializes the LCD display.
- **`void check()`**: Checks the RFID data against predefined user IDs and controls the gate accordingly.
- **`void lcdcmd(unsigned char val)`**: Sends a command to the LCD.
- **`void lcddat(unsigned char val)`**: Sends data to the LCD.
- **`void lcddis(unsigned char *s)`**: Displays a string on the LCD.
- **`void delay()`**: Generates a delay for timing purposes.
- **`void mdelay()`**: Generates a longer delay for motor control timing.

## Connections

- **RFID Reader**: Connected to the microcontroller via the serial port.
- **LCD Display**: Connected to Port 1 (Data lines) and specific pins of Port 2 (Control lines: rs, rw, en).
- **Motor Control**: Controlled via Port 2 pins (doorp and doorn).

## Usage

1. **Power on the System**:
   - The system initializes and displays the welcome messages.

2. **Swipe RFID Card**:
   - Swipe the RFID card over the reader.
   - The system reads and verifies the card data.

3. **Gate Operation**:
   - If the card is authorized, the gate opens and allows entry.
   - If the card is not authorized, the system denies access.

## Future Improvements

- Integrate a database for more flexible user management.
- Add features for logging entry and exit times.
- Implement a network interface for remote monitoring and control.

## Conclusion

This RFID-based car parking system provides a secure and automated solution for managing parking access. It demonstrates the use of microcontroller programming, serial communication, and motor control in an embedded system application.
