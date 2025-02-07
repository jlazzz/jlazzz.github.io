---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Hey, I'm Josh! I have a BSc in Engineering Physics from the University of Alberta. I've had the pleasure of working on many cool projects with many cool people. Here's a bit about them.

* TOC
{:toc}

# Work Experience
- Test Specialist at Xiphos Systems Corporation
- Systems, Embedded HW and SW roles at AlbertaSat
- Systems Engineering Intern at the Canadian Space Agency
- Medical Physics Research Internship at the Cross Cancer Institute

# AlbertaSat

[AlbertaSat](https://albertasat.ca/) is a student group that makes satellites. Throughout my undergrad, I worked on getting three satellites designed, built, and tested: Ex-Alta 2, YukonSat, and AuroraSat. An overview of the initiative was presented at the 2021 Small Satellite Conference: [https://digitalcommons.usu.edu/smallsat/2021/all2021/119/](https://digitalcommons.usu.edu/smallsat/2021/all2021/119/)

## Integration and Testing

I managed all testing activities for Northern SPIRIT satellites. We took an iterative approach to testing, utilizing rapid prototyping, engineering models, and FlatSats (pictured below) to rapidly test and find problems as early as possible.
![flatsat](/images/flatsat.png)

After sweat, tears (no blood, luckily), thermal and vibration testing we had three functional ready-to-launch satellites!
![cubesats](/images/cubesats.jpg)

## Systems Engineering

As systems lead, I managed:
- Test planning
- Interface control
- Trade studies
- COTS supplier procurement
- System design (including harnessing...)
- Over 300 system requirements (including RfW, RfD, and NCR handling)
- Configuration management of mission-critical documents

This project presented a unique systems engineering challenge, since most AlbertaSat members are undergraduate student volunteers with limited time available to commit. This also leads to a high turnover rate and short average tenure, since most people leave the group once they graduate.

My team presented a poster on this work at the Small Satellite Conference in 2023:

Applications of Systems Engineering Methodologies to an Undergraduate Student Volunteer-Led CubeSat Constellation [https://digitalcommons.usu.edu/smallsat/2023/all2023/140/](https://digitalcommons.usu.edu/smallsat/2023/all2023/140/)

<iframe src="files/systems_eng_methodologies.pdf" width="100%" height="600px"></iframe>

## Embedded Hardware Design

### Athena On-Board Computer

#### Motivation
The “brain” of a satellite is the onboard computer (OBC), which performs computations and sends/receives commands and data with other subsystems. With commercial Cube Satellite OBCs costing around $5 000 to $23 000 USD or more (excluding software), the Athena II OBC aims to lower the barrier to space through its fully open-source design and hardware cost of less than $600 per unit while retaining many features that minimize risk of damage and upsets due to radiation.

Three Athena II OBCs were launched to space on the Ex-Alta 2, YukonSat, and AuroraSat CubeSats in 2022.

**Features:**
- Follows PC/104 form factor and in-house standard (Open CubeSat Platform Bus Specification)
- Interfaces w/ other subsystems CAN (x2), UART (x4), SPI (x3), I2C (x1), GPIO (x14)
- Real-time clock w/ backup power capacitor, temperature sensors, 9-axis inertial measurement unit, and current sensors
- 3-axis magnetorquer control
- Solar panel interface w/ overcurrent protection: power, data, and deployable burnwire control
- Error-correcting code on all storage media (except SD Card)
- Designed to -40 to +85 °C operational temperature range
- Latch-up protection for on-board buck converter

<img src="/images/athena_block_diagram.png" alt="block_diagram" width="400"/>
<img src="/images/athena_altium.png" alt="altium" width="200"/>
<img src="/images/athena_pcb.png" alt="pcb" width="200"/>

### Software-Defined Radio
I created and tested the signal processing and link layer processing chain for AlbertaSat's UHF and S-Band ground stations, which use the [Ettus Research USRP B205mini-i SDR](https://www.ettus.com/all-products/usrp-b205mini-i/)

[https://github.com/AlbertaSat/ex2_sdr/tree/master/gnuradio](https://github.com/AlbertaSat/ex2_sdr/tree/master/gnuradio)

UHF
- Half-duplex w/ automatic push-to-talk handling for RF frontend switching
- Frequency shift keying
- Doppler shift correction via gpredict orbit prediction
- Adjustable baud rate: 1200 to 19200 b/s
- Adjustable modulation index
- Interfaces with ground station backend code

S-Band
- Receive-only
- Quadrature phase shift keying
- Doppler shift correction via gpredict orbit prediction
- Adjustable baud rate: 2 to 10 Mb/s
- Descrambler

![UHF](/images/uhf_sdr_gnuradio.png)

### Charon GPS Receiver

I designed, built, and tested Charon, an open-source GPS receiver PCB. It also does a few other mission-specific things (thermistor interface, payload connector adapter, power switch latch).

![pcb](/images/charon.png)

## Software Development
Developed the driver code for ICs and peripherals on the Athena OBC, including SD card integration with file system and telemetry integration with FreeRTOS: [https://github.com/AlbertaSat/ex2_obc_software](https://github.com/AlbertaSat/ex2_obc_software)
Integrated ground station software data handling with GNURadio frontend, including beacon parsing and decoding: [https://github.com/AlbertaSat/ex2_ground_station_software](https://github.com/AlbertaSat/ex2_ground_station_software)

# Capstone Project - Open-Source CubeSat Optical Downlink Receiver and Processing System 
In my final year of Engineering Physics I realized a high-performance lasercom system with two of my colleagues and presented the poster at [SmallSat](https://smallsat.org/) 2022 in Logan, Utah. I learned a lot about signal processing and implemented it C, which was run on an embedded system with high-speed DAC and ADC.

[https://github.com/joshdellaz/laser_satellite_receiver](https://github.com/joshdellaz/laser_satellite_receiver)

<iframe src="files/capstone_poster.pdf" width="100%" height="600px"></iframe>


# Misc.

## Full-Stack Development: Habit Tracker

I wanted a barebones and extremely simple web-based habit tracker, so I made one! It gave me a bit more experience with html, javascript, and SQL databases: [https://github.com/joshdellaz/habit_tracker](https://github.com/joshdellaz/habit_tracker)

## Orbit Modelling w/ Ansys STK for Satellite Return Rate

I created a simple simulation in ![STK](https://www.ansys.com/products/missions/ansys-stk) to estimate downlink time at various ground stations in Canada, given a specific antenna radiation pattern.

## Toaster Reflow Oven

![reflow](/images/toaster_reflow.png)

#### Motivation

Unfortunately COVID-19 caused shutdown of the facilities necessary for AlbertaSat to solder circuit boards, so a workaround was needed to avoid falling behind schedule. 

Professional solder reflow ovens are typically quite expensive, but luckily I was able to get my hands on a toaster oven and retrofit it to use a PIC microcontroller board to reflow circuit boards for at-home work.

#### Overview

With the ability to custom-program temperature profiles, the oven can reach > 250 °C and has sufficient stability to successfully solder 0.8 mm pitch, tin-ball, ball grid array (BGA) chips (performance w/ smaller pitch components has not yet been tested). Temperature profile testing and optimization was done to ensure performance was sufficient before being used to solder expensive hardware.


# Other...

Some other areas that fascinate me and that I want to learn and create in:
- Virtual/mixed/augmented reality
- Web3
- AI
- Brain-computer interfaces
- IT systems engineering: AWS and Kubernetes
- Propulsion systems
- Video game design
