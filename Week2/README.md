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

<h4> SoCs helped overcome the drawbacks of standalone CPUs by reducing board area, lowering power consumption, minimizing interconnect delays, and cutting costs through the integration of multiple components into a single chip.</h4>

## System-on-Chip (SoC) ##

An SoC is a complete computing system fabricated on a single chip, integrating the CPU or multiple cores along with memory controllers, peripheral interfaces, and often specialized 
hardware accelerators.SoCs help chip designers achieve compact, energy-efficient, and cost-effective systems using a single piece of silicon.

![Apple-M4-Max-chip-CPU-performance_big jpg large_2x](https://github.com/user-attachments/assets/5982bc11-6e0b-4c31-b4f2-9691c7a2ab77)

<h4> Despite all the good points supporting the design of SoCs, there are a few issues with them such as complex design requirements, potential heat buildup from packing many 
  components into a small area, and reduced flexibility since each SoC is tailored for specific tasks and difficult to modify once fabricated. </h4>

<h4> Components of SoC </h4>
  <img width="2000" height="1600" alt="SoC_KeyParts_Arrows" src="https://github.com/user-attachments/assets/b18ccb09-d1f2-4fbf-a687-f2ae8e0e8ebe" />

## SoC Design Flow ##

<img width="2777" height="59" alt="SoC_Infographic" src="https://github.com/user-attachments/assets/58985843-4b74-4ae3-93cf-adff53e1e452" />

## VSDBabySoC ##

<img width="2270" height="1260" alt="image" src="https://github.com/user-attachments/assets/8bc66fa7-28a2-4e71-81e4-e20974b83ec8" />

The **VSDBabySoC** integrates three main components,RVMYTH (RISC-V CPU),Phase-Locked Loop (PLL) and Digital-to-Analog Converter (DAC).

- **RVMYTH (RISC-V CPU core)** : A simple, RISC-V processor that executes instructions and serves as the computing engine of the SoC.  

- **Phase-Locked Loop (PLL) 8xPLL** : Provides a stable, high-frequency system clock by multiplying and conditioning the input clock, ensuring reliable CPU and peripheral operation.  

- **10-bit DAC (Digital-to-Analog Converter)** : Converts digital outputs from the CPU into analog signals, enabling mixed-signal interfacing (useful for testing and demonstration).  

### Phase-Locked Loop (PLL) ###

<img width="600" height="178" alt="image" src="https://github.com/user-attachments/assets/40f25f41-d50f-4e7b-a18b-67a3188ea369" />


A **Phase-Locked Loop (PLL)** is a feedback control system that generates a stable output signal locked to a given reference input frequency. It is widely used in clock generation, communication systems, and frequency synthesis because of its ability to maintain synchronization. It mainly consists of three components

- **Phase Detector (PD):** Compares the phase of the input frequency (*f_in*) with the feedback/output frequency (*f_out*) and produces a voltage proportional to their phase difference.  
- **Active Low-Pass Filter (LPF):** Eliminates high-frequency components from the PD output, leaving a clean DC voltage that represents phase error while also amplifying the signal.  
- **Voltage-Controlled Oscillator (VCO):** Produces an output signal whose frequency varies according to the DC voltage received from the LPF.  

Through the combined action of these three components, the PLL adjusts the VCO until its output frequency matches the input frequency, achieving stable and synchronized operation.

## 🖥️ Digital-to-Analog Converter (DAC)

A **Digital-to-Analog Converter (DAC)** converts digital (binary) signals into continuous analog signals. DACs are widely used in systems where digital processors or controllers must interact with the analog world — such as audio systems, communication devices, and mixed-signal SoCs.  
There are two common types of DACs:  

---
![binary_weighted_resistors](https://github.com/user-attachments/assets/0e1ce4c8-5ad4-4fe1-997c-ae717070d5d8)

### 1️⃣ Weighted Resistor DAC  
A **Weighted Resistor DAC** uses resistors of different values, each weighted according to the binary significance of the input bits.  
- Each bit of the digital input controls a switch that either connects the resistor to a reference voltage or to ground.  
- Higher-order bits control resistors with lower resistance values, meaning they contribute more to the output voltage.  
- The resistors are connected into an op-amp inverting adder circuit, producing an analog output proportional to the binary input.  

---
![ladder_dac](https://github.com/user-attachments/assets/49ef0d9d-2d11-4159-9b47-26a67d56700b)

### 2️⃣ R-2R Ladder DAC  
The **R-2R Ladder DAC** solves the precision problem by using only two resistor values: `R` and `2R`.  
- This ladder-like resistor network distributes the binary input weights naturally.  
- Each digital bit controls a switch connecting the ladder to reference voltage or ground.  
- Because only two resistor values are required, it is much easier to fabricate and scale to higher resolutions.  


### 🎯 Relevance of VSDBabySoC  

The **VSDBabySoC** is more than just a simple teaching design — it is a compact mixed-signal SoC integrating a RISC-V CPU (RVMYTH), a PLL, and a DAC. Its real strength lies in how it connects **education, research, and prototyping** into one open-source framework.  

#### 📚 Education  
- Acts as a complete educational bridge to learn the **entire SoC design flow** (RTL → synthesis → PnR → signoff → tapeout).  
- Unlike standalone CPU projects, it includes **analog IP integration** (PLL, DAC), giving students exposure to mixed-signal challenges.  

#### 🔧 Hobby Projects  
- Serves as a **reference design** to build your own small SoCs for experimentation.  

#### 🔬 Research  
- Useful for studying **noise isolation, DRC/STA debugging, and mixed-signal integration** in real chip contexts.  
- Already validated in actual **VSD tapeouts**, making it a trustworthy starting point for academic research.  

#### 🚀 Prototyping & Sandbox  
- Provides a sandbox to try **new digital accelerators or blocks** (like a systolic array for ML/Edge AI).  
- Can be extended with **memory-mapped peripherals** (GPIO, UART, SPI, ADC) for building IoT-class SoCs.  
- Ideal for **prototyping tiny embedded systems** and testing new IP ideas in a realistic flow.  

✨ **In short:** VSDBabySoC is a ready-made platform that connects *learning, experimenting, and innovating* in SoC design — whether for academics, hobby projects, or research extensions.  

### Lab Setup ###

We First install Sandpiper. SandPiper converts TL-Verilog to standard Verilog. this is because Iverilog (Icarus Verilog) Doesn't Support TL-Verilog.
```
sudo apt install python3-pip
pip3 install pyyaml click sandpiper-saas

```
We then Clone the Repository that has all the relevant files.

```
git clone https://github.com/manili/VSDBabySoC

```

### File Structure ###

```
VSDBabySoC/
├── src/
│   ├── include/              # Header files (*.vh)
│   ├── module/               # Verilog + TLV modules
│   │   ├── vsdbabysoc.v      # Top-level SoC module integrating CPU, PLL, and DAC
│   │   ├── rvmyth.tlv        # TL-Verilog source for RVMYTH CPU
│   │   ├── avsdpll.v         # Phase-Locked Loop (PLL)
│   │   ├── avsddac.v         # Digital-to-Analog Converter (DAC)
│   │   ├── clk_gate.v        # Clock gating logic for power management
│   │   ├── sandpiper.vh      # TL-Verilog include header (used during TLV-to-Verilog translation)
│   │   └── testbench.v       # Testbench for simulation and verification
└── output/                   # Simulation, synthesis, and waveform outputs
```

### TL-Verilog to Verilog Conversion ###
This an important step as Iverilog cannot understand TL-Verilog. We accomplish this using sandpiper-saas by RedwoodEDA. Icarus Verilog does have some support for System Verilog but its not complete, therefore it is advisable to stick to converting to Verilog and not trying to allow the sandpiper tool to get away with letting some conversions being in SV. as it can cause unexpected errors when running with Icarus Verilog specifically if you use -g2012 flag with it to force it to allow SV constucts such as "always @(ff)".
The following command was used to ensure conversion to Verilog was done correctly and no remanant SV code was present in generated file.

```
sandpiper-saas -i ./src/module/rvmyth.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/

```
### Presynthesis Simulation ###

We first use Icarus Verilog (iverilog) to compile the testbench and run simulations. The simulation generates a dump file (.vcd), which is later used to visualize signal waveforms in GTKWave.

```
iverilog -o output/pre_synth_sim.out -DPRE_SYNTH_SIM -I src/module src/module/testbench.v
cd output
./pre_synth_sim.out

```

<img width="800" height="600" alt="Screenshot from 2025-10-04 13-18-36" src="https://github.com/user-attachments/assets/5646f12a-8235-44e3-a36c-2fe9f7268738" />


#### Simulation Waveforms ####

We now use GTKWave to view the Waveforms.

```
gtkwave pre_synth_sim.vcd

```

<img width="800" height="600" alt="Screenshot from 2025-10-04 13-16-28" src="https://github.com/user-attachments/assets/b255c8d7-79ce-4cd4-9f6f-654b45614fe3" />

<img width="800" height="600" alt="Screenshot from 2025-10-04 13-16-34" src="https://github.com/user-attachments/assets/b84c82be-3c55-4bba-8d9d-e815b102e4f3" />

##  VSDBabySoC Simulation Analysis using GTKWave

The simulation demonstrates the working of the **VSDBabySoC**, which integrates three major components:
**RVMYTH (RISC-V CPU Core)**, **AVSDPLL (Phase-Locked Loop)**, and **AVSDDAC (Digital-to-Analog Converter)**.  
Each component plays a crucial role in this mixed-signal SoC, and their interactions can be observed in the waveform outputs generated through GTKWave.

---

<details>
<summary> <b>RVMYTH (RISC-V CPU Core)</b></summary>

The **RVMYTH CPU** acts as the brain of the SoC — executing instructions, reading and writing data, and producing digital outputs that drive the DAC.

| **Signal Name** | **Description** | **What It Shows in GTKWave** |
|------------------|------------------|-------------------------------|
| `CPU_dmem_addr_a4[3:0]` | 4-bit data memory address bus. | Toggles rapidly — CPU accessing different memory locations. |
| `CPU_dmem_rd_data_a5[31:0]` | 32-bit read data bus. | Initially undefined (`xxxx`), stabilizes once CPU reads valid data. |
| `CPU_ld_data_a5[31:0]` | Load data into registers. | Reflects valid read data after each `rd_en` pulse. |
| `clkP_CPU_dmem_rd_en_a5` | Read enable for data memory. | Pulses high when CPU requests a memory read. |
| `clkP_CPU_rd_valid_a5` | Data valid signal. | Goes high when the read data is ready. |
| `OUT[9:0]` | Digital output to DAC. | Represents processed 10-bit data for analog conversion. |

 **Interpretation:**  
When `rd_en` and `rd_valid` align, the CPU is completing a read-execute-write cycle.  
The changes in `OUT[9:0]` reflect processed outputs sent to the DAC for conversion.

</details>

---

<details>
<summary>⚡ <b>AVSDPLL (Phase-Locked Loop)</b></summary>

The **PLL** provides a clean, high-frequency system clock for synchronous operation.  
It multiplies a low-frequency input (e.g., 5 MHz or 12.5 MHz) to generate a stable higher frequency (40 MHz – 100 MHz).

| **Signal Name** | **Description** | **GTKWave Behavior** |
|------------------|------------------|------------------------|
| `REF` | Input reference clock. | Slow periodic waveform — baseline frequency. |
| `VCO_IN` | VCO input signal. | High-frequency oscillation — shows multiplication effect. |
| `CLK` | Output clock to SoC. | Stabilizes at ~40 MHz once PLL locks. |
| `ENB_CP` | Charge-pump enable. | High during phase-correction phase. |
| `ENB_VCO` | VCO enable. | Indicates active oscillation. |
| `period` | Output clock period (ns). | ~35.4 ns corresponds to ~28–40 MHz. |
| `refpd` | Reference phase difference. | Settles once phase lock achieved. |

 **Interpretation:**  
Once the PLL locks, the output `CLK` stabilizes and drives the CPU and DAC.  
The `period` and `refpd` signals flatten, confirming stable frequency and phase.

</details>

---

<details>
<summary> <b>AVSDDAC (Digital-to-Analog Converter)</b></summary>

The **DAC** converts 10-bit digital data from the CPU into analog voltages, enabling mixed-signal interfacing.

| **Signal Name** | **Description** | **GTKWave Behavior** |
|------------------|------------------|------------------------|
| `D[9:0]` / `Dext[10:0]` | Digital input lines. | Changes with CPU outputs — triggers new analog values. |
| `OUT` | Intermediate DAC output. | Shows step-like transitions of conversion. |
| `OUT(real)` | Analog output voltage. | Smooth variations proportional to digital input. |
| `VREFH` / `VREFL` | High and low voltage references. | Define the output voltage range (e.g., 0 V – 1 V). |
| `EN` | Enable signal. | High when DAC is active. |
| `NaN` | Undefined state indicator. | Appears during startup, clears once references stabilize. |

 **Interpretation:**  
The DAC continuously converts digital CPU outputs into analog voltages.  
When `OUT[9:0] = 2E5`, the analog output reaches ~0.724 V — confirming correct D/A conversion.

#### 🔢 DAC Output Calculation

For a 10-bit DAC, the analog output voltage \( V_{OUT} \) is given by:

\[
V_{OUT} = \frac{D}{2^{10} - 1} \times (V_{REFH} - V_{REFL}) + V_{REFL}
\]

Where:  
- \( D \) = Digital input (in decimal)  
- \( 2^{10} - 1 = 1023 \)  
- \( V_{REFH} = 1\,V \)  
- \( V_{REFL} = 0\,V \)

---

\[
2E5_{(hex)} = 2 \times 16^2 + 14 \times 16 + 5 = 741_{(dec)}
\]

---

\[
V_{OUT} = \frac{741}{1023} \times 1V = 0.7243\,V
\]

---

✅ **Result:**
When `OUT[9:0] = 2E5`, the analog output ≈ **0.724 V**, confirming correct D/A conversion.

</details>

---


**All three blocks — Digital, Analog, and Timing — are functioning coherently, validating the complete SoC design from RTL to analog interface.**


#### Troubleshooting ####

- Ensure that the files are included only once as it may give rise to redefinition errors. the files can be included in the testbench or in the CLI.
- Ensure that TL-Verilog to Verilog conversion is done correctly. use flags such as "" "" to ensure it. I-Verilog has very limited Support for System Verilog and very frequently Sandpiper puts SV constructs in the generated Files.



## Acknowledgements ##
**www.Tutorialspoint.com** [ https://www.tutorialspoint.com/linear_integrated_circuits_applications/linear_integrated_circuits_applications_phase_locked_loop_ic.htm https://www.tutorialspoint.com/linear_integrated_circuits_applications/linear_integrated_circuits_applications_digital_to_analog_converters.htm ]

**Hemanth Kumar's Repository** [https://github.com/hemanthkumardm/SFAL-VSD-SoC-Journey/tree/main/11.%20Fundamentals%20of%20SoC%20Design https://github.com/hemanthkumardm/SFAL-VSD-SoC-Journey/tree/main/12.%20VSDBabySoC%20Project]

**Manili's Repository**https://github.com/manili/VSDBabySoC?tab=readme-ov-file



