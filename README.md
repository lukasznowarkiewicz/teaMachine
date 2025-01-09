# teaMachine

---

### Table of Contents

1. [Project Overview](#project-overview)
2. [Motivation](#motivation)
3. [General Project Assumptions](#general-project-assumptions)
4. [Development](#development)
   - [Mechanics](#mechanics)
   - [Hardware](#hardware)
   - [Software](#software)
   - [Firmware](#firmware)
5. [Repositories Overview](#repositories-overview)

---

### Project Overview

The **teaMachine** project combines software, hardware, and mechanical design to create an innovative tea maker. The system integrates various technologies to offer a robust and modular solution for making tea, akin to coffee machines. This repository acts as the master directory to organize and link all subprojects.

---

### Motivation

The project stemmed from the idea of making productive use of free time during studies. The goals included:
- Creating a proper machine for making tea, similar to coffee machines.
- Combining knowledge from mechatronics, electronics, automation, programming, and embedded systems.
- Using the project as a bachelor’s thesis and later as a master’s thesis.
- Leveraging the project as credit work for various subjects during studies.

---

### General Project Assumptions

- Design a modular base to develop various parts of the machine.
- Use as many COTS (Commercial Off-The-Shelf) components as possible to expedite development.
- Develop software for the machine and test different approaches to refine functionality.

---

### Development

#### Mechanics
![Mechanical Development](./images/mechanicalDevelopment.jpeg)
- The mechanical design utilizes 2020 aluminum profiles for the frame, with copolycarbonate sides for structure and visibility.
- As a prototype, most components were 3D-printed to allow rapid iteration.
![3D Printed Parts - Slicer](./images/3dPrintedPartsSlicer.png)
![3D Printed Parts - Printer](./images/3dPrintedPartsPrinter.jpeg)
![3D Printed Parts - Printer 2](./images/3dPrintedPartsPrinter2.jpeg)
- The design incorporates COTS motors, sensors, pumps, and flow heaters.
- The design evolved over time, with significant changes to containers and assembly approaches as development progressed.
![Assembly Step 1](./images/assembly1.jpeg)
![Assembly Step 2](./images/assembly2.jpeg)
![Assembly Step 3](./images/assembly3.jpeg)
![Assembly Step 4](./images/assembly4.jpeg)
- Designed in Fusion 360
[Fusion Timelapse](./videos/fusion_timelapse.mp4)

#### Hardware
- The hardware was wired to integrate high-voltage and low-voltage elements effectively:
  - 1 SSR (Solid State Relay) for controlling high-voltage elements like heaters and water pumps.
  - Mechanical relays for low-voltage equipment such as small pumps and motors.
![Wiring Step 0](./images/wireing0.jpeg)
![Wiring Step 1](./images/wireing1.jpeg)
![Wiring Step 2](./images/wireing2.jpeg)
![Wiring Step 3](./images/wireing3.jpeg)
![Wiring Step 4](./images/wireing4.jpeg)
![Wiring Step 5](./images/wireing5.jpeg)

- A custom-designed `teaMachineControlBoard` was developed for the Raspberry Pi Pico to manage machine operations.
![PCB Design](./images/pcbDesign.jpeg)
![PCB Testing](./images/teaMachineControlPCBTesting.jpeg)
![PCB Thermals](./images/teaMachineControlPCBThermals.jpg)
- The system features a front panel initially controlled by an RPi 2 and later replaced with an RPi Zero 2W, displaying the user interface on a screen.
- ![Front Panel Development](./images/frontPanelDevelopment.JPG)
- ![Front Panel Development - Alternative](./images/frontPanelDevelopment0.jpeg)
- ![Front Panel Development 2](./images/frontPanelDevelopment2.JPG)

#### Software
- **Windows 10 IoT Core**
  - First attempt: Designed a sample app in .NET Core (C#) and installed the OS on a Raspberry Pi 2.
  - Results: Functional but slow. Windows 10 IoT Core appeared to be nearing discontinuation.
[Windows 10 IoT Test](./videos/windows10iot_test.mp4)
![Windows 10 IoT Walkthrough](./images/windows10IOTWalkthrough.jpeg)

- **Vue + Vite on Debian**
  - Attempted running Vue and Vite on Debian on the Raspberry Pi 2.
  - Challenges: Cross-compilation took time to configure, and performance was slow due to the lack of OpenGL acceleration on the SBC.

[Dashboard Vue Demo](./videos/dashboard_vue.mp4)
![Dashboard - Vue](./images/dashboard_vue.jpeg)
- **Python App Using customTKinter**
  - Developed an app in Python with the customTKinter library for the user interface.
  - Requirements: Only Python interpreter and a few libraries.
  - Results: Worked well on Debian and later on the Raspberry Pi Pico 2W, where it ran smoothly.


#### Firmware
- Firmware was created to control and manage the tea machine components effectively. See related repositories for details.
[PCB Test Program](./videos/teaMachineControlPCB_test_program.mp4)
---

### Repositories Overview

Each subrepository handles a specific aspect of the teaMachine project:

1. **[teaMachineDashboard](#)**
   A Python-based web dashboard for controlling and monitoring the tea maker.

2. **[teaMachineVisionSystem](#)**
   Vision-based ingredient measurement and verification, implemented in Python using OpenCV.

3. **[teaMachinePicoFirmware](#)**
   C++ firmware for the Raspberry Pi Pico controlling sensors, motors, and other hardware.

4. **[teaMachineMechanical](#)**
   CAD models and design files for the mechanical components of the tea maker.

5. **[TeaMachineControlBoard](#)**
   Control board PCB design in KiCad.

6. **[teaMachineFCBMicroUSBAdapter](#)**
   Hardware design for a USB adapter to connect the Raspberry Pi 2 with a touchscreen.

7. **[teaMachineSomOS](#)**
   Linux-based OS for the tea maker’s System on Module (SoM).

8. **[teaMachineFuzzyController](#)**
   Scripts, applications, and resources for the fuzzy controller, including integration with flow heaters and sensors.

---
