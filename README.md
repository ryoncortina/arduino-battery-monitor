# Arduino Battery Voltage Monitor

A personal Arduino project built to learn more about analog voltage measurement, relay control, protection circuits, and basic control logic.

The system monitors a higher DC voltage using a voltage divider and Arduino analog input. Based on the measured voltage, the Arduino controls a relay and RGB status LED to indicate the current operating condition.

## Project Goals

The goal of this project was to get hands-on experience with:

- Analog voltage measurement
- Voltage divider circuits
- Arduino ADC readings
- Relay control
- Voltage threshold logic
- Basic circuit protection
- RGB status indication
- Serial monitoring and troubleshooting

## Hardware

- Arduino Uno
- 100kΩ resistor
- 10kΩ resistor
- 4.7V Zener diode
- Capacitor
- 1A fuse and fuse holder
- Relay module
- RGB LED
- Bench power supply
- Breadboard and jumper wiring
- Multimeter

## Voltage Sensing

Because the voltage being monitored is higher than the Arduino analog input can safely accept, a voltage divider is used to reduce the voltage before it reaches the analog input.

The divider uses:

- R1 = 100kΩ
- R2 = 10kΩ

The Arduino measures the divided voltage through an analog input and the program calculates the original source voltage.

The sensing circuit also includes additional protection for the Arduino analog input.

## Control Logic

The program continuously monitors the calculated battery voltage and determines the system state.

The relay can be used to disconnect a load when the battery voltage falls below the programmed threshold.

The RGB LED provides a visual indication of system status.

Example states include:

- Normal operating voltage
- Low voltage warning
- Low voltage cutoff
- Charging/recovery state

## Testing

A bench power supply was used to simulate different battery voltages during development.

This allowed the voltage to be raised and lowered while comparing:

1. Bench power supply voltage
2. Multimeter measurement
3. Arduino calculated voltage
4. Relay response
5. RGB LED status

This made it possible to test the control logic without connecting the circuit to the actual battery system during development.

## What I Learned

This project helped me better understand the relationship between a real-world analog voltage and the value seen by a microcontroller.

It also gave me practice combining hardware and software troubleshooting, including checking voltage at different points in the circuit, verifying voltage-divider calculations, adjusting control logic, and testing system behavior at different voltage levels.

## Future Improvements

Possible future additions include:

- Adjustable voltage thresholds
- Hysteresis to prevent relay cycling near the cutoff point
- Improved enclosure and permanent wiring
- Voltage calibration
- Data logging
- Display for battery voltage and system status
- Additional fault detection

## Disclaimer

This is a personal learning project and is not intended to replace a commercial battery management system or certified low-voltage disconnect.
