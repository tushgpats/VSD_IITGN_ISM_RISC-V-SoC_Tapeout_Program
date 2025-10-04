# Fundamentals of SoC Design and Presynthesis Simulation of VSDBabySoC. #
<br></br>
## Background behind emergence of SoCs ##

For much of the Second half of the century, the Central Processing Unit (CPU) was designed as a standalone chip responsible only for executing instructions. In order to build a 
complete system, this CPU had to be connected to several external peripherals such as memory chips (RAM and ROM), timers, counters, and I/O controllers. All of these components were 
mounted on a printed circuit board and linked together using data, address, and control buses. 
In the earliest days of computing, from the 1950s through the 1970s, the CPU was treated as a standalone unit. Early machines used boards or even cabinets full of discrete logic. Even 
when the microprocessor arrived in the 1970s with chips like Intel’s 4004 (1971), 8080 (1974), and Motorola’s 6800 (1974), the idea still stayed the same.
<br></br>
<h4> While this approach worked, it had significant drawbacks, including larger board area, higher power consumption, longer interconnect delays, and increased cost since multiple chips had to be manufactured, packaged, and tested separately.</h4>
<br></br>
Intel’s 8051 (1980) marked the birth of the microcontroller, which combined a CPU with RAM, ROM, and I/O on a single chip.Throughout the 1980s this approach spread, shrinking system 
size and cost while boosting reliability. By the 1990s the idea expanded further into full-fledged System-on-Chips (SoCs), which added memory controllers, DSPs, allowing designers to 
place most of a system’s functionality on one piece of silicon.
Today, SoCs power nearly all modern electronic devices, from smartphones and laptops to cars, IoT devices, and networking equipment. High-performance examples such as Apple’s M1 and M2 
chips or Qualcomm’s Snapdragon processors combine CPUs, GPUs, DSPs, memory controllers, and even AI accelerators within one integrated solution.

<img width="2400" height="800" alt="CPU_to_SoC_Timeline" src="https://github.com/user-attachments/assets/b9074e1c-c51b-416e-998d-deca2ea0a19d" />

## System-on-Chip (SoC) ##

An SoC is a complete computing system fabricated on a single chip, integrating the CPU or multiple cores along with memory controllers, peripheral interfaces, and often specialized 
hardware accelerators.SoCs help chip designers achieve compact, energy-efficient, and cost-effective systems using a single piece of silicon.

![Apple-M4-Max-chip-CPU-performance_big jpg large_2x](https://github.com/user-attachments/assets/5982bc11-6e0b-4c31-b4f2-9691c7a2ab77)

