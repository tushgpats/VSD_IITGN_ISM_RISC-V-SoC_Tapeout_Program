# VSD_IITGN_ISM_RISC-V-SoC_Tapeout_Program

Here we Delve into actual implementation of the Tapeout. First let us look at the system requirements and the tools required for RTL Synthesis and Simulation.

## Linux Configuration

This is the often overlooked aspect but it is a very crutial one. It is essential that the system supports the workload.

### so the system Requirements are as Follows:
- 6 GB RAM
- 50 GB HDD
- Ubuntu 20.04 or higher
- 4 vCPU

## Installation of Yosys, Iverilog and gtkwave.

### <ins>**Yosys**</ins>

Yosys is an open-source framework for digital logic synthesis, widely used in FPGA and ASIC design flows. 
It converts RTL designs (typically written in Verilog) into gate-level netlists, applying optimizations and technology mapping along the way. 
Its flexibility, extensibility through plugins, and integration with tools like OpenLane and ABC make it a cornerstone of the open-source EDA ecosystem.

Following are the Steps to Installing Yosys

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
<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic7" src="https://github.com/user-attachments/assets/1ab88adf-d77c-49c0-b6aa-dd930e96640d" />

<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic8" src="https://github.com/user-attachments/assets/b753881e-d643-4357-be97-7a04039302f0" />

<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic9" src="https://github.com/user-attachments/assets/ee761fea-a16f-4740-8c41-7eebd900687a" />

<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic10" src="https://github.com/user-attachments/assets/8af448ac-e5f2-49f0-a4e9-304da81b6b0a" />

<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic11" src="https://github.com/user-attachments/assets/434165c9-edbe-4a59-991d-d8baf44e4efd" />

<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic20" src="https://github.com/user-attachments/assets/7426cda9-e3e4-444a-9eb9-0c44212d6774" />

<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic22" src="https://github.com/user-attachments/assets/1c307144-26ad-4404-b35b-74f0d803da3d" />


#### And Voila !!!

<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic23" src="https://github.com/user-attachments/assets/304a2257-3d29-42d5-ab35-892808de6c8a" />


You may encounter issues with Bison version mismatching. Its Very easy to fix though. Just Download Bison from web using the wget command and installing it manually will fix the problem.


### <ins>**Iverilog**</ins>

Icarus Verilog (Iverilog) is an open-source Verilog simulation and synthesis tool. 
It’s mainly used for compiling and running Verilog HDL code, making it ideal for testing digital logic designs before synthesis. 
Lightweight and widely adopted in academia and open-source projects, it works seamlessly with tools like GTKWave for waveform viewing.

Following are the Steps to Installing Iverilog:

```bash
$ sudo apt-get update
$ sudo apt-get install iverilog
```


<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic25" src="https://github.com/user-attachments/assets/d1ce241c-9623-4e09-a13a-97abfbf7a2fe" />


<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic26" src="https://github.com/user-attachments/assets/112ee510-2d75-4c7e-af8b-db7d0c33b969" />



### <ins>**gtkwave**</ins>

GTKWave is an open-source waveform viewer used to visualize simulation results from tools like Icarus Verilog and VHDL simulators.
It allows engineers to inspect signal transitions, timing behavior, and debug digital logic designs interactively. 
Its support for standard dump formats (VCD, FST, LXT) makes it a key tool in open-source verification workflows.

Following are the Steps to Installing:

```bash
$ sudo apt-get update
$ sudo apt install gtkwave
```


<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic27" src="https://github.com/user-attachments/assets/d5a9459f-595f-4054-8c7c-380172e56867" />


<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic29" src="https://github.com/user-attachments/assets/c8595749-5c87-4d4e-b169-29f6c7671ccf" />


<img width="960" height="540" alt="VSD_IITGN_RISC-V_Tapeout_Week0_Task0_pic30" src="https://github.com/user-attachments/assets/dde2eeb5-a093-41de-97a5-dbcaf54baa34" />








