<p align="center">
  <img src="icon.png" alt="snorlax icon" width="150"/>
</p>

# snorlax
This repo contains the files to run a snoring detection model on Arduino Nicla voice connected to a motor driver controlling an air pump and a electric valve to regulate the air pressure inside a bladder that's to be placed under the pillow.

## Equipments
1. Arduino Nicla Voice
2. AC to DC Adapter
3. Buck Converter (12V to 5V)
4. L293D Motor Driver
5. Air pump
6. Electric valve
7. Bladder
8. USB micro-B to USB A cable

## Hardware Set-up
1. Connect Ardiuino Nicla Voice (1) to the USB A port on the Buck Converter (3) with the USB cable (8)
2. Connect the barrel jack of the DC Adapter (2) to the port on Buck Converter (3).
3. The Vin and Vout ports of the Buck Converter (3) should already be connected (and screwed in) to 12V and GND of the motor driver (4) respectively
4. The ports M1 through M4 should also already be connected as such:

| Ports on Motor Driver (4) | Connections |
|----------|----------|
| M1  | Positive (red wire) of Air Pump  |
| M2  | Ground (black wire) of Air Pump  |
| M3 | Ground (black wire) of Electric valve  |
| M4  | Positive (red wire) of Electric valve  |

5. Some more connections on the motor driver:

| Ports on Motor Driver (4) | Connections |
|----------|----------|
| IN4  | Ground of Motor Driver (4)  |
| IN3  | 5V pin of Motor Driver (4)  |
| EN2 | Pin 1 of Nicla Voice (1)  |
| 5V  | IN3 pin of Motor Driver (4)  |
| IN2  | Ground of Motor Driver (4) |
| IN1  | 5V pin of Motor Driver (4)  |
| EN1 | Pin 2 of Nicla Voice (1)  |
| 5V  | IN1 pin of Motor Driver (4)  |

6. You can now plug in the DC adapter to a wall socket and switch it ON.

Visual wiring diagram: https://www.tldraw.com/f/s7IBKXQYeQvr3On8GsMOI?d=v-2696.-3339.6172.8331.9kc033r-xZe3sAvQ6U0_-

## Functionality
When installed and switched on, the onboard microphone on the Nicla Voice (1) will start listening for snoring noises within 10 seconds. When it detects a snoring sound, a green LED lights up on the board. When it detects 3 snoring sounds in a 1 minute interval, it blocks air passage through the electric valve (6) and start pumping air through the Air Pump (5) for 50 seconds. Post that, it stop the pump and retains the bladder's (7) inflated state for another 50 seconds. And finally, it opens up the electric valve (6) and lets the bladder deflate. And starts the cycle again.

Nicla Voice is configured to continuously sends out logs via serial over USB at the baud rate 115200. It can be read by installing Arduino IDE and [using Arduino Serial Monitor tool](https://docs.arduino.cc/software/ide-v2/tutorials/ide-v2-serial-monitor/#using-the-serial-monitor-tool)


## Making changes to the algorithm
1. Git clone this repo
2. Make changes to the code in `firmware-arduino-nicla-voice/src/ei_syntiant_ndp120.cpp`
3. Connect Nicla Voice via the USB cable (8) to your computer
4. Go to the `arduino-nicla-voice-firmware` directory and run the following command:
```
cd ../firmware-arduino-nicla-voice
./arduino-build.sh --build
cp firmware-arduino-nicla-voice.ino.elf ../arduino-nicla-voice-firmware
cd ../arduino-nicla-voice-firmware
mv firmware-arduino-nicla-voice.ino.elf firmware.ino.elf
./flash_mac.command
```

## About the Model

| **Dataset**         | **Size**       |
|---------------------|----------------|
| Training dataset    | 797 × 1 second |
| Testing dataset     | 194 × 1 second |
| **Final Accuracy**  | **97.42%**     |

Confusion matrix:
| Actual / Predicted | Snoring | Z_Openset | Uncertain |
|--------------------|---------|-----------|-----------|
| **Snoring**        | 97.9%   | 1.0%      | 1.0%      |
| **Z_Openset**      | 2.0%    | 96.9%     | 1.0%      |


## Credits
- Edge Impulse's [Snoring Detection Guide](https://docs.edgeimpulse.com/experts/audio-projects/arduino-nicla-voice-syntiant-snoring-detection)
- Edge Impulse's [Custom Nicla Voice Firmware](https://cdn.edgeimpulse.com/firmware/arduino-nicla-voice-firmware.zip)
- Tareq Khan's [Snoring dataset on Kaggle](https://www.kaggle.com/datasets/tareqkhanemu/snoring)
