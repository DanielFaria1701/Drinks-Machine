# AAB (Alcoholic Arduino Bar) - Drink Machine

An Arduino-based automated drink-mixing system controlled through a mobile app via Bluetooth.  
The user selects a drink on the app, and the machine automatically pumps the correct liquids into the cup.  
A payment module ensures drinks are only dispensed when the correct amount is inserted.

> **Note:**  
> The demonstration video is in **European Portuguese (Portugal)** and some code comments may also be written in PT-PT.

---

## Project Overview

This project implements a fully automated drink dispenser ("Drink Machine") controlled wirelessly through a smartphone app.

The mobile app:
- Shows a drink menu with descriptions  
- Sends the selected drink to the machine via Bluetooth  
- Also serves as the system’s display interface  

The Arduino:
- Receives the drink selection via the **HC-05 Bluetooth module**  
- Activates the appropriate pumps through a **relay module**  
- Mixes and dispenses the chosen drink  
- Checks credit before dispensing (payment module)  
- Uses sensors to monitor and secure the process

All pumping is handled by **12V DC pumps**, connected through silicone tubing.

---

## Components Used

- **Arduino UNO**  
- Jumper wires (male/male, male/female)  
- **Relay module 4-channel 5V**  
- **Bluetooth module HC-05**  
- Breadboard  
- **12V DC Pump**  
- **IR sensor**  
- **16x2 Alphanumeric LCD**  
- **I2C module for 16x2 LCD (1602)**  
- **AC to 12V DC 10A converter**  
- 4m silicone hose (6×9mm)  
- 0.1 µF capacitors  
- Red & black wires (0.75 mm²)  
- **1 kΩ resistor**  
- **2 kΩ resistor**  

---

## System Workflow

1. **User selects a drink** on the mobile app.  
2. App sends the drink ID to the Arduino via **Bluetooth (HC-05)**.  
3. Arduino receives the command and checks:  
   - Is the correct amount of money inserted?  
4. If payment is correct:  
   - Arduino activates the corresponding pump(s) via the relay board  
   - Liquid flows from the containers through the silicone tubes into the cup  
5. The LCD displays:  
   - Payment status  
   - Drink currently being dispensed  
   - Final confirmation  

If the payment is incorrect, the machine refuses to serve the drink.

---

## Functional Modules

### **Bluetooth Communication**
- Receives the drink code from the app  
- Sends feedback to the app if needed  

### **Drink Selection Handler**
- Maps drink IDs to pump combinations  
- Defines drink recipes (quantities and timing)  

### **Pump Control**
- Relay module switches 12V pumps  
- Pumps draw each liquid through silicone tubing  

### **Payment Module**
- Validates that the correct amount was inserted  
- Uses IR sensor or manual input simulation  

### **Display System**
- Uses LCD 16x2 with I2C module  
- Shows system status, money inserted, drink name, etc.  

---

## Video Demonstration

A full demonstration of the project is available here:

👉 **[Insert your video link here]**

> The video is presented in **European Portuguese (Portugal)**.

---

## Notes

- Some parts of the source code and comments may be written in **European Portuguese (Portugal)**.  
- Ensure pumps have proper power isolation (they run on 12V through a relay).  
- Recommended to test each pump individually before creating drink recipes.  

---

## Authors

Daniel Faria  
Miguel Loureiro
