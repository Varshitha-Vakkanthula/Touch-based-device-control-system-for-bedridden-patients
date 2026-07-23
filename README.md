# 🏥 Touch-Based Device Control System for Bedridden Patients
    ![Block Diagram](Block%20diagram.png)

# 📖 Project Overview
The Touch-Based Device Control System for Bedridden Patients is an embedded systems project developed to improve the quality of life for patients who have limited mobility due to illness, injury, or age. The system enables users to operate electrical appliances through a simple and secure touch-based interface, reducing their dependence on caregivers for routine tasks.
The project is built around the LPC2148 ARM7 microcontroller, which acts as the central controller for all connected peripherals. A 4×4 matrix keypad is used to enter a password, and the entered password is verified against the password stored in the AT25LC512 SPI EEPROM. Only after successful authentication does the system enable the resistive touchscreen, ensuring that appliances cannot be controlled by unauthorized users or through accidental touches.
Once access is granted, the resistive touchscreen becomes the primary user interface. The screen is divided into predefined regions, with each region assigned to a specific appliance. Whenever the user touches one of these regions, the microcontroller detects the corresponding X-Y coordinates, identifies the selected appliance, and changes its operating state. The current status of the devices is continuously displayed on the 16×2 LCD, providing clear feedback to the user.
To further enhance system security and flexibility, an external interrupt-based password update mechanism is implemented. When the interrupt switch is activated, the user is prompted to verify the existing password before entering and confirming a new one. The updated password is then written to the EEPROM through SPI communication, allowing the new credentials to remain stored even after power is switched off.
The project follows a modular Embedded C programming approach, with separate drivers for the LCD, keypad, touchscreen, SPI, EEPROM, UART, and interrupt handling. This modular design improves code readability, simplifies debugging, and allows future enhancements such as IoT connectivity, mobile application integration, wireless communication, or voice-controlled operation.
Overall, this project demonstrates the practical application of Embedded C programming, ARM7 microcontroller interfacing, EEPROM memory management, serial communication protocols, and touchscreen-based human-machine interaction. It provides a secure, reliable, and user-friendly solution that can be extended for healthcare automation, smart hospital environments, elderly assistance systems, and home automation applications.

# 🎯 Project Objectives

- Enable bedridden patients to operate electrical devices easily.
- Protect the system using password authentication.
- Save user passwords securely in EEPROM.
- Provide a simple touch-based control interface.
- Allow password modification using an external interrupt.
- Demonstrate ARM7 LPC2148 programming with Embedded C.

# ⭐ Key Features

- Secure Password Login
- Touchscreen-Based Device Control
- EEPROM Password Storage
- LCD Display Interface
- Matrix Keypad Input
- SPI Communication
- External Interrupt Support
- Modular Embedded C Design
- Easy-to-Use Interface

# 🧩 Hardware Requirements

| Component | Purpose |
|-----------|---------|
| LPC2148 ARM7 | Main Controller |
| Resistive Touch Screen | User Input |
| 16x2 LCD | Display Messages |
| 4x4 Matrix Keypad | Password Entry |
| AT25LC512 EEPROM | Password Storage |
| Buzzer | Alert Indication |
| LEDs | Appliance Simulation |
| External Interrupt Switch | Password Update |


# 💻 Software Requirements

- Embedded C
- Keil uVision
- Flash Magic

---

# 🖼️ Block Diagram

![Block Diagram](Block%20diagram.png)

---

# ⚙️ System Working

### Step 1 – System Initialization

When power is applied, the LPC2148 initializes the LCD, keypad, touchscreen, EEPROM, GPIO pins, and interrupt module. The LCD then displays a welcome message.

### Step 2 – Password Entry

The user enters a password using the matrix keypad.

### Step 3 – Authentication

The controller retrieves the stored password from EEPROM through SPI communication and compares it with the entered password.

- Incorrect Password → Access denied and retry.
- Correct Password → Touchscreen is enabled.

### Step 4 – Touch Activation

To prevent accidental operation, the touchscreen becomes active only after the user performs the required activation touch.

### Step 5 – Appliance Selection

Different touchscreen regions correspond to different appliances.

- 💡 Light
- 🌀 Fan
- 📺 Device 1
- 🔔 Buzzer

The controller identifies the touched area using X-Y coordinates.

### Step 6 – Device Operation

The selected appliance changes between ON and OFF, while the LCD continuously displays the current device status.

### Step 7 – Continuous Monitoring

The controller continuously monitors touch input, allowing users to control appliances without restarting the system.

# 🔐 Password Update

The system allows password modification using an external interrupt.

1. Press the interrupt switch.
2. Enter the current password.
3. Verify the password.
4. Enter a new password.
5. Confirm the new password.
6. Save the updated password to EEPROM.

The modified password remains stored even after power OFF.

# 📡 Communication Interfaces

## SPI
Used for communication between LPC2148 and AT25LC512 EEPROM.

Functions:
- Read Password
- Store Password
- Update Password

## UART

Used for debugging and serial communication during development.

## External Interrupt

Used to activate password update mode.

# 🧩 Software Modules

- LCD Driver
- Keypad Driver
- Touchscreen Driver
- SPI Driver
- EEPROM Driver
- UART Driver
- Interrupt Driver
- Password Authentication Module
- Device Control Module

# 📂 Project Folder Structure

```
Touch-Based Device Control System
│
├── README.md
├── Block diagram.png
├── main.c
├── lcd.c
├── lcd.h
├── kpm.c
├── kpm.h
├── delay.c
├── delay.h
├── spi.c
├── spi.h
├── types.h
└── Other project source files

# 🚀 Applications

- Smart Hospital Rooms
- Patient Assistance Systems
- Elderly Care Solutions
- Home Automation
- Medical Automation
- Rehabilitation Centers

# ✅ Advantages

- Easy to operate
- Secure user authentication
- Reliable password storage
- Low power consumption
- Modular software architecture
- Expandable design

# 📈 Project Outcomes

- Developed an ARM7 LPC2148 embedded application.
- Integrated LCD, keypad, touchscreen, EEPROM, and buzzer.
- Implemented secure password verification.
- Established SPI communication with EEPROM.
- Implemented interrupt-driven password modification.

# 📚 Skills Gained

- Embedded C Programming
- ARM7 LPC2148 Programming
- LCD Interfacing
- Matrix Keypad Interfacing
- Resistive Touchscreen Interfacing
- SPI Communication
- EEPROM Programming
- UART Communication
- Interrupt Programming.

# 🔮 Future Enhancements

- IoT-Based Monitoring
- Mobile App Control
- Bluetooth Connectivity
- Wi-Fi Integration
- Voice Control
- Fingerprint Authentication
- Cloud Connectivity

# 👩‍💻 Author

Varshitha Vakkanthula

Embedded Systems Enthusiast

GitHub: https://github.com/YOUR_USERNAME

⭐ If you found this project useful,
please ⭐star this repository and share it with others.

🙏 Acknowledgement
This project was developed as part of an Embedded Systems learning program to demonstrate secure touch-based appliance control for bedridden patients using the LPC2148 ARM7 Microcontroller and Embedded C.


⭐ Thank you for visiting this repository! ⭐
