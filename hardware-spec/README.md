<p align="center">
  <img src="icon.png" alt="snorlax icon" width="150"/>
</p>

# Open Hardware spec for Snorlax
This repo contains the files to run a snoring detection model on Arduino Nicla voice connected to a motor driver controlling an air pump and a electric valve to regulate the air pressure inside a bladder that's to be placed under the pillow.

## Equipments
### 1. Arduino Nicla Voice
<p align="center">
  <img src="./1.png"  width="200"/>
</p>

- [Datasheet](https://robu.in/wp-content/uploads/2023/02/ABX00061-datasheet.pdf)

2. AC to DC Adapter

Standard 12V 3A Power Supply with 5.5mm DC Plug Desktop Type

<p align="center">
  <img src="./hardware-spec/hardware-spec/2.png"  width="200"/>
</p>

- [Datasheet](https://robu.in/wp-content/uploads/2024/12/adapter-spec-12VDC-3.0A.pdf)

3. Buck Converter (12V to 5V)
24V/12V to 5V 5A Power Module DC-DC XY-3606 Power Converter

<p align="center">
  <img src="./hardware-spec/hardware-spec/3.png"  width="200"/>
</p>

- [Diagram](https://robu.in/wp-content/uploads/2021/05/975683.jpg)

4. STM Electronics' L293D Motor Driver

| Parameter                 | Value                          |
|--------------------------|--------------------------------|
| Current Rating (A)       | 0.6                            |
| Voltage Rating (V)       | 4.5 to 12                      |
| Driver Model             | L293D                          |
| Operating Voltage (VDC)  | 4.5 ~ 12                       |
| Peak Current (A)         | 0.6                            |
| No. of Channels          | 1                              |
| Polarity Protection      | No                             |
| Dimensions (L x W x H) mm| 48 x 34 x 14                   |
| Weight (g)               | 15                             |

<p align="center">
  <img src="./hardware-spec/hardware-spec/4.png"  width="200"/>
</p>

- [Datasheet](https://robu.in/wp-content/uploads/2015/10/H-bridge_motor_driver.pdf)

5. Air pump

370 DC Air Pump 12VDC

| Parameter                | Value     |
|-------------------------|-----------|
| Voltage Rating (V)      | 12VDC     |
| Operating Current (A)   | 0.3       |
| Flow Rate (L/Hr)        | 240       |
| Length (mm)             | 68        |
| Diameter (mm)           | 24.4      |
| Weight (g)              | 30        |

<p align="center">
  <img src="./hardware-spec/hardware-spec/5.png"  width="200"/>
</p>


6. Electric valve

<p align="center">
  <img src="./hardware-spec/hardware-spec/6.png"  width="200"/>
</p>

7. Bladder

Sahyog Wellness Arm Blood Pressure BP Rubber Bladder Having Double Tube for Sphygmomanometer Bp Monitor (Black)

<p align="center">
  <img src="./hardware-spec/hardware-spec/7.png"  width="200"/>
</p>

- [Amazon](https://www.amazon.in/dp/B0BW5PGWZJ?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)

8. USB micro-B to USB A cable

<p align="center">
  <img src="./hardware-spec/hardware-spec/8.png"  width="200"/>
</p>
