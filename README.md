# Multi-Laser Controller

A Python-based graphical interface for controlling multiple lasers through an Arduino microcontroller via serial communication.

## Overview

This system consists of two main components:
1. **MultiLaserController** - Python class for serial communication with Arduino
2. **LaserControlGUI** - PyQt6 graphical interface for user interaction

## Requirements

### Software Dependencies

```bash
pip install pyserial PyQt6
```

- Python 3.7 or higher
- pyserial 3.5+
- PyQt6 6.0+

### Hardware Requirements

- Arduino board (Uno, Mega, Nano, etc.)
- Arduino firmware for laser TTL control (not included in this repository)
- Up to 3 lasers connected to Arduino digital outputs
- USB cable for Arduino connection

## Installation

1. Clone or download this repository
2. Install required Python packages:
   ```bash
   pip install pyserial PyQt6
   ```
3. Ensure both `multi_laser_controller.py` and `laser_control_gui.py` are in the same directory
4. Upload the appropriate firmware to your Arduino

## Usage

### Starting the GUI

Run the GUI application:

```bash
python laser_control_gui.py
```

### Connecting to Hardware

1. **Select COM Port** - Choose your Arduino's port from the dropdown menu
   - Windows: typically `COM3`, `COM4`, etc.
   - Linux: typically `/dev/ttyUSB0`, `/dev/ttyACM0`
   - macOS: typically `/dev/cu.usbserial-*` or `/dev/cu.usbmodem-*`

2. **Select Baud Rate** - Choose the baud rate matching your Arduino firmware (default: 9600)

3. **Click Connect** - Establishes serial connection and initialises all lasers to OFF state

### Controlling Lasers

Once connected, you can:

- **Toggle Individual Lasers** - Click "Toggle Laser 1/2/3" buttons
- **Turn All On** - Activate all lasers simultaneously
- **Turn All Off** - Deactivate all lasers simultaneously
- **Emergency Stop** - Immediately turn off all lasers (with confirmation)

### LED Indicators

- **Green** - Laser is ON
- **Grey** - Laser is OFF

### Disconnecting

Click the "Disconnect" button to safely close the serial connection. All lasers will be turned off before disconnecting.
