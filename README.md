# Initial setup
Project was created with [pico-project-generator](https://github.com/raspberrypi/pico-project-generator) from repos dir.  May require SDK installation first (check pico docs)

python3 pico-project-generator/pico_project.py -p vscode amiga_keyboard

# Building
VScode will build it.  Use GCC for arm-none-eabi
## TinyUSB setup
Follow the steps [here](https://github.com/raspberrypi/tinyusb/blob/pico/docs/getting_started.md)
or just copy the tinyusb lib contents from the examples dir into the project

# Download / debugging
Best to use a raspberry pi as we need to use SWD to program because the USB port is in use
## Connections
| Pico pin | Pi pin |
--- | ---
| SWDIO | 18 (GPIO 24) |
| GND | 20 |
| SWCLK | 22 (GPIO 25) |

May need to install OpenOCD and gdb first.  Check [this guide](https://www.electronicshub.org/programming-raspberry-pi-pico-with-swd/)
Will also need power (connect 5v from pi pin 2 to DB9 pin 7)

# Design
## Pin mapping

| DB9 pin | Pico Pin | GPIO | Description |
--- | --- | --- | ---
| 1 | 21 | 16 | vpulse |
| 2 | 22 | 17 | hpulse |
| 3 | 19 | 14 | vqpulse |
| 4 | 20 | 15 | hqpulse |
| 5 | n/c | | button3 (middle) |
| 6 | 24 | 18 | button1 (left) |
| 7 | 40 | | +5v |
| 8 | GND | | Gnd |
| 9 | 17 | 13 | button2 (right) |
