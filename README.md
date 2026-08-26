# ATmega32 Calculator

A simple calculator project implemented using **ATmega32**, **LCD**, and **4x4 Keypad**.
The project was developed in **Embedded C** and simulated using **Proteus**.

## 📌 Project Overview

This project implements a basic calculator using an ATmega32 microcontroller.

The user enters numbers and selects mathematical operations using a **4x4 Keypad**, and the result is displayed on a **16x2 LCD**.

### Supported Operations

* Addition `+`
* Subtraction `-`
* Multiplication `×`
* Division `÷`
* Clear `ON/C`
* Enter `=`

---

## 🛠️ Hardware Components

* ATmega32 Microcontroller
* 16x2 LCD
* 4x4 Keypad
* Crystal Oscillator
* Power Supply
* Proteus for simulation

---

## 🔌 Pin Configuration

### LCD

The LCD is connected to the ATmega32 and is controlled using the LCD driver.

| LCD Pin | Function   |
| ------- | ---------- |
| VSS     | GND        |
| VDD     | +5V        |
| VEE     | Contrast   |
| RS      | Control    |
| RW      | Read/Write |
| E       | Enable     |
| D0-D7   | Data Lines |

### Keypad

The 4x4 Keypad is connected to **PORTC**.

| Keypad  | ATmega32  |
| ------- | --------- |
| Rows    | PC0 - PC3 |
| Columns | PC4 - PC7 |

---

## 📂 Project Structure

```text
Calculator
│
├── INCLUDE
│   ├── HAL
│   │   ├── KEYPAD
│   │   │   ├── KEYPAD_CFG.h
│   │   │   ├── KEYPAD_INTERFACE.h
│   │   │   └── KEYPAD_PRIVATE.h
│   │   │
│   │   └── LCD
│   │       ├── LCD_CFG.h
│   │       ├── LCD_INTERFACE.h
│   │       └── LCD_PRIVATE.h
│   │
│   ├── LIB
│   └── MCAL
│
├── SOURCE
│   ├── DIO_PROGRAM.c
│   ├── KEYPAD_PROGRAM.c
│   ├── LCD_PROGRAM.c
│   └── main.c
│
├── Binaries
├── Debug
└── Proteus Simulation
```

---

## ⚙️ Software Architecture

The project follows a layered driver architecture:

```text
Application Layer
       │
       ▼
   main.c
       │
       ▼
     HAL
  ┌────┴────┐
 LCD      Keypad
  │          │
  └────┬─────┘
       ▼
     MCAL
      DIO
```

### Drivers Used

* **DIO Driver**

  * Handles ATmega32 GPIO pins.

* **LCD Driver**

  * Initializes the LCD.
  * Sends commands.
  * Sends/display characters.
  * Displays strings and numbers.

* **Keypad Driver**

  * Initializes the keypad.
  * Scans the keypad.
  * Detects the pressed key.

---

## 🚀 How It Works

1. The ATmega32 initializes the DIO, LCD, and Keypad.
2. The calculator waits for a key press.
3. The user enters the first number.
4. The user selects an arithmetic operation.
5. The user enters the second number.
6. The `=` key is pressed.
7. The calculator performs the selected operation.
8. The result is displayed on the LCD.
9. The `ON/C` key can be used to clear the current calculation.

---

## 🧪 Simulation

The project was simulated using **Proteus**.

The simulation contains:

* ATmega32
* 16x2 LCD
* 4x4 Keypad
* Required connections and power supply

---

## 💻 Technologies Used

* Embedded C
* ATmega32
* AVR Microcontroller
* Proteus
* LCD
* 4x4 Keypad
* Driver-Based Architecture

---

## 👩‍💻 Author

**Axani Ayman**

Embedded Systems Project — ATmega32 Calculator
