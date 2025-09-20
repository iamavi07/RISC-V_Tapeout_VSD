### 🏗 Digital VLSI SoC Design and Planning

Digital VLSI System-on-Chip (SoC) design is the process of integrating millions to billions of transistors on a single chip to build complex digital systems such as processors, controllers, and accelerators. The design flow begins with specification and RTL coding, followed by functional verification, logic synthesis, and design-for-testability (DFT). After that, the design moves into the physical design phase, which includes floorplanning, placement, clock tree synthesis, routing, and finally sign-off checks like timing closure and power analysis.

SoC planning also involves partitioning the design into modules, defining the interconnect architecture, and optimizing performance, power, and area (PPA). With the rise of open-source tools and RISC-V architecture, learning SoC design provides engineers with both practical skills and industry-relevant exposure to modern chip development flows.## RISC-V_Tapeout_VSD
## Tool Installation Guide

This repository documents the essential setup required to run RISC-V open-source toolchains for tapeout projects. Follow the steps carefully to prepare your system environment.

### 🔧 System Requirements

Before starting, make sure your machine meets the following requirements:

RAM: Minimum 6 GB

Disk Space: At least 50 GB free

Operating System: Ubuntu 20.04 (or newer)

Processor: 4 vCPUs recommended

🖥 Adjusting Ubuntu Window Size

If you are running Ubuntu inside VirtualBox and the display does not fit the screen, install the required headers and VirtualBox Guest Additions:

### **Resizing the Ubuntu window to fit the screen**
```bash
$ sudo apt update
$ sudo apt install build-essential dkms linux-headers-$(uname -r)
$ cd /media/spatha/VBox_GAs_7.1.8/
$ ./autorun.sh
```

## ✅ Tool Installation & Verification
### 1. Yosys (Synthesis Tool)

Yosys is the open-source framework for RTL synthesis. To build and install it:
```bash
$ sudo apt-get update
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys
$ sudo apt install make               # If make is not installed
$ sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
# Yosys build depends on a Git submodule called abc, which hasn't been initialized yet. You need to run the following command before running make
$ git submodule update --init --recursive
$ make 
$ sudo make install
```
<img width="1032" height="610" alt="image" src="https://github.com/user-attachments/assets/8d3eb8e2-c3fe-4c9b-b9f1-7eff0d0a8a69" />


#### 2. Icarus Verilog (iverilog)

For simulation of Verilog designs, install Icarus Verilog:
```bash
$ sudo apt-get update
$ sudo apt-get install iverilog
```
<img width="1192" height="456" alt="Screenshot 2025-09-20 120824" src="https://github.com/user-attachments/assets/7f5de4bd-cbd6-4958-a9ed-b1532ceadb47" />


#### 3. GTKWave

GTKWave is a waveform viewer used to debug simulation outputs. Install it as:
```bash
$ sudo apt-get update
$ sudo apt install gtkwave
```
!<img width="747" height="143" alt="image" src="https://github.com/user-attachments/assets/1b1f4c9f-d3c4-43a8-8933-48f56c6945c0" />

