# CMOS Circuit Design and SPICE Simulations

## Table of Contents

- [VirtualBox installation](#virtualbox-installation)
- [Day 1: NgSpiceSky130 - Basics of NMOS Drain Current (Id) vs Drain to Source Voltage (Vds)](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#day-1-ngspicesky130---basics-of-nmos-drain-current-id-vs-drain-to-source-voltage-vds)
  * [Introduction to Circuit Design and SPICE Simulations](#introduction-to-circuit-design-and-spice-simulations)
    + [Lecture 1: Why is SPICE Simulation needed?](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-why-is-spice-simulation-needed)
    + [Lecture 2: Introduction to basic elements in Circuit Design - NMOS](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-introduction-to-basic-elements-in-circuit-design---nmos)
    + [Lecture 3: Strong Inversion](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-strong-inversion)
    + [Lecture 4: Threshold voltage with positive substrate potential](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-4-threshold-voltage-with-positive-substrate-potential)
  * [NMOS resistive region and saturation region of operation](#nmos-resistive-region-and-saturation-region-of-operation)
    + [Lecture 1: Resistive region of operation with small drain-source voltage](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-resistive-region-of-operation-with-small-drain-source-voltage)
    + [Lecture 2: Drift current theory](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-drift-current-theory)
    + [Lecture 3: Drain current model for linear region of operation](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-drain-current-model-for-linear-region-of-operation)
    + [Lecture 4: SPICE conclusion to resistive operation](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-4-spice-conclusion-to-resistive-operation)
    + [Lecture 5: Pinch-off region condition](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-5-pinch-off-region-condition)
    + [Lecture 6: Drain current model for saturation region of operation](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-6-drain-current-model-for-saturation-region-of-operation)
  * [Introduction to SPICE](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#introduction-to-spice)
    + [Lecture 1: Basic SPICE setup](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-basic-spice-setup)
    + [Lecture 2: Circuit description in SPICE syntax](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-circuit-description-in-spice-syntax)
    + [Lecture 3: Define technology parameters](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-define-technology-parameters)
    + [Lecture 4: First SPICE simulation](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-4-first-spice-simulation)
    + [Lecture 5: SPICE Lab with sky130 models](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-5-spice-lab-with-sky130-models)
- [Day 2: Velocity saturation and basics of CMOS inverter VTC](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#day-2-velocity-saturation-and-basics-of-cmos-inverter-vtc)
  * [SPICE simulation for lower nodes and velocity saturation effect](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#spice-simulation-for-lower-nodes-and-velocity-saturation-effect)
    + [Lecture 1: WSPICE simulation for lower nodes](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-wspice-simulation-for-lower-nodes)
    + [Lecture 2: Drain current vs gate voltage for long and short channel devices](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-drain-current-vs-gate-voltage-for-long-and-short-channel-devices)
    + [Lecture 3: Velocity saturation at lower and higher electric fields](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-velocity-saturation-at-lower-and-higher-electric-fields)
    + [Lecture 4: Velocity saturation drain current model](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-4-velocity-saturation-drain-current-model)
    + [Lecture 5: Labs Sky130 Id-Vgs](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-5-labs-sky130-id-vgs)
    + [Lecture 6: Labs Sky130 Vt](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-6-labs-sky130-vt)
  * [CMOS voltage transfer characteristics (VTC)](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#cmos-voltage-transfer-characteristics-vtc)
    + [Lecture 1: MOSFET as a switch](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-mosfet-as-a-switch)
    + [Lecture 2: Introduction to standard MOS voltage current parameters](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-introduction-to-standard-mos-voltage-current-parameters)
    + [Lecture 3: PMOS/NMOS drain current v/s drain voltage](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-pmosnmos-drain-current-vs-drain-voltage)
    + [Lecture 4: Step1 – Convert PMOS gate-source-voltage to Vin](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-4-step1--convert-pmos-gate-source-voltage-to-vin)
    + [Lecture 5: Step2 & Step3 – Convert PMOS and NMOS drain-source-voltage to vout](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-5-step2--step3--convert-pmos-and-nmos-drain-source-voltage-to-vout)
    + [Lecture 6: Step4 – Merge PMOS – NMOS load curves and plot VTC](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-6-step4--merge-pmos--nmos-load-curves-and-plot-vtc)
- [Day 3 - CMOS Switching threshold and dynamic simulations](#day-3---cmos-switching-threshold-and-dynamic-simulations)
  * [Voltage transfer characteristics – SPICE simulations](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#voltage-transfer-characteristics--spice-simulations)
    + [Lecture 1: SPICE deck creation for CMOS inverter](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-spice-deck-creation-for-cmos-inverter)
    + [Lecture 2: SPICE simulation for CMOS inverter](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-spice-simulation-for-cmos-inverter)
    + [Lecture 3: Labs Sky130 SPICE simulation for CMOS](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-labs-sky130-spice-simulation-for-cmos)
  * [Static behavior evaluation – CMOS inverter robustness – Switching Threshold](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#static-behavior-evaluation--cmos-inverter-robustness--switching-threshold)
    + [Lecture 1: Switching Threshold, Vm](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-switching-threshold-vm)
    + [Lecture 2: Analytical expression of Vm as a function of (W/L)n and (W/L)p](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-analytical-expression-of-vm-as-a-function-of-wln-and-wlp)
    + [Lecture 3: Analytical expression of (W/L)n and (W/L)p as a function of Vm](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-analytical-expression-of-wln-and-wlp-as-a-function-of-vm)
    + [Lecture 4: Static and dynamic simulation of CMOS inverter](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-4-static-and-dynamic-simulation-of-cmos-inverter)
    + [Lecture 5: Static and Dynamic simulation of CMOS inverter with increased PMOS width](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-5-static-and-dynamic-simulation-of-cmos-inverter-with-increased-pmos-width)
    + [Lecture 6: Applications of CMOS inverter in clock network and STA](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-6-applications-of-cmos-inverter-in-clock-network-and-sta)
- [Day4- CMOS Noise Margin robustness evaluation](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#day4--cmos-noise-margin-robustness-evaluation)
  * [Static behaviour evaluation-CMOS inverter robustness-Noise Margin](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#static-behaviour-evaluation-cmos-inverter-robustness-noise-margin)
    + [Lecture 1: Introduction to Noise Margin](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-introduction-to-noise-margin)
    + [Lecture 2: Noise Margin voltage parameters](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-noise-margin-voltage-parameters)
    + [Lecture 3: Noise margin equation and summary](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-noise-margin-equation-and-summary)
    + [Lecture 4: Noise margin variation with respect to PMOS width](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-4-noise-margin-variation-with-respect-to-pmos-width)
    + [Lecture 5: Sky130 Noise margin labs](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-5-sky130-noise-margin-labs)
 - [Day 5 - CMOS power supply and device variation robustness evaluation](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#day-5---cmos-power-supply-and-device-variation-robustness-evaluation)
  * [Static behavior evaluation – CMOS inverter robustness – Power supply variation](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#static-behavior-evaluation--cmos-inverter-robustness--power-supply-variation)
    + [Lecture 1: Smart SPICE simulation for power supply variations](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-1-smart-spice-simulation-for-power-supply-variations)
    + [Lecture 2: Advantages and disadvantages of using low supply voltage](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-2-advantages-and-disadvantages-of-using-low-supply-voltage)
    + [Lecture 3: Sky130 Supply Variation Labs](https://github.com/ani171/CMOS_Circuit_Design/blob/main/README.md#lecture-3-sky130-supply-variation-labs)
 
# VirtualBox installation
1. Install VirtualBox
    - Download and install the latest stable release of Oracle VirtualBox from the official website: ```https://www.virtualbox.org/wiki/Downloads```
    - Ensure that virtualization is enabled in the system BIOS/UEFI before proceeding.

2. Create a New Virtual Machine
    1. Launch Oracle VirtualBox.
    2. Click **New** to create a virtual machine instance.
    3. Configure the following parameters:

| Parameter | Configuration |
|------------|--------------|
| Name | CMOS (or preferred VM name) |
| Type | Linux |
| Version | Ubuntu 18.04 Bionic Beaver (64-bit) |

3. Configure Memory Allocation
    - Allocate system memory (RAM) based on host capacity.
    - Recommended allocation: **4096 MB (4 GB)** or higher for stable operation.
    - Click **Next** to continue.
4. Attach the Provided VDI File
    1. Select **Use an existing virtual hard disk file**.
    2. Click the folder icon to open the Virtual Media Manager.
    3. Browse to the extracted CMOS VDI file location.
    4. Select the `.vdi` file and click Open
    5. Confirm the selection.
    6. Click **Finish** to create the virtual machine.
5. Launch the Virtual Machine
    1. Select the newly created VM.
    2. Click **Start**.
    3. Log in using the credentials provided with the CMOS image.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/810667cd-80c8-464e-b38d-54e2b0d478f9" />

#### 5. Start the Virtual Machine

1. Select the created VM
2. Click **Start**

# Day 1: NgSpiceSky130 - Basics of NMOS Drain Current (Id) vs Drain to Source Voltage (Vds)

## Introduction to Circuit Design and SPICE Simulations

### Lecture 1: Why is SPICE Simulation needed?
- to verify circuit behavior
- optimize performance
- identify flaws before physical prototyping <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/73c5ea9b-62ea-4038-aa77-176a99e55680" /> <br/>

- The circuit shown above is a CMOS inverter, which serves as the fundamental building block of digital integrated circuits. It implements the logical NOT operation and forms the basis for more complex combinational and sequential logic systems. <br/>
- By appropriately configuring the Pull-Up Network (PUN) and Pull-Down Network (PDN), a wide range of logic gates such as NAND, NOR, and complex logic functions can be realized. These complementary networks define the Boolean functionality of the circuit. <br/>
- By applying different input voltage levels and sweeping the input across its operating range, the corresponding output response can be measured to obtain the voltage transfer characteristics (VTC) or I–V characteristics of the logic gate, as illustrated below. <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/f0c3abb4-1ba3-4fac-8768-3c4e76df4ebb" /> <br/>

- The combined switching behavior of the PMOS and NMOS devices is captured through SPICE simulation, resulting in the corresponding composite waveform <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/0d2227d6-7832-4d98-a2f9-ec890b895fca" /> <br/>

- The propagation delay extracted from the simulated waveform is used to optimize the NMOS-to-PMOS width ratio (Wn/Wp), allowing accurate delay balancing and refinement of the timing model. Proper sizing ensures symmetric rise and fall delays and improves overall switching performance. <br/>

- During Clock Tree Synthesis (CTS), buffers are strategically inserted to distribute the clock signal while driving varying capacitive loads at different nodes. This buffering minimizes clock skew, controls insertion delay, and maintains signal integrity across the clock network. <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/b289b3a4-f12c-45ea-a5e6-e85a157d9704" /> <br/>

- From these spice simulations, we obtain a delay table that includes the input slew and output load <br/>

<img width="2141" height="518" alt="image" src="https://github.com/user-attachments/assets/fdcd03b7-3d62-43ea-94e5-b42515b9f25e" /> <br/>

- Select the row corresponding to the input slew and the column corresponding to the output load; their intersection gives the cell delay value <br/>
- If the exact slew or load is not listed, use interpolation between adjacent values to estimate the delay <br/>
- Each delay table corresponds to a different Wn/Wp ratio, so variations between tables reflect the impact of transistor sizing on propagation delay <br/>
- SPICE simulations basically involve characterizing the NMOS and PMOS in detail, thus optimizing the delay model <br/>

### Lecture 2: Introduction to basic elements in Circuit Design - NMOS
#### N-channel Metal Oxide Semiconductor 
- NMOS is a 4-terminal device consisting of Gate (G), Drain (D), Source (S), and Body (B). The device operates by forming an inversion channel between source and drain when Vgs exceeds the threshold voltage <br/>

| Component | Description | Key Notes |
|------------|-------------|-----------|
| P-type Substrate | Base semiconductor material on which the NMOS is built | • Forms the body of the device <br> • Provides majority holes as carriers |
| Isolation Regions | Regions separating adjacent devices | • Electrically isolate neighboring transistors <br> • Prevent leakage and latch-up |
| N+ Diffusion (Source & Drain) | Heavily doped n-type regions in the substrate | • Act as source and drain terminals <br> • Provide electron injection and collection |
| Gate Oxide | Thin insulating oxide layer above substrate | • Typically SiO₂ <br> • Controls channel formation <br> • Critical for threshold voltage |
| Polysilicon / Metal Gate | Conductive layer above gate oxide | • Forms the Gate (G) terminal <br> • Controls channel via electric field <br> • Drives device switching |
| Body Terminal | Substrate connection terminal | • Usually connected to ground in NMOS <br> • Affects threshold voltage (body effect) <br> • Important for device modeling |

<br/>
<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/1b31d1fd-671c-41de-93c7-3695d559501c" /> <br/>

#### Threshold voltage (Vt)
- Threshold voltage is the minimum gate-to-source voltage required to form an inversion layer (conducting channel) between source and drain, allowing the MOSFET to turn ON <br/>

**Threshold Voltage Modelling** <br/>

- Let Vgs=0
- Connect Drain, Source, and Body to GND
- Now, Body-Source and Body-Drain form a pn junction diode 
- As both junctions are OFF, high resistance is observed, thus no conductivity between Source and Drain <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/c067006d-8848-42e2-b6ed-c1aeeb2d0b77" /> <br/>

- When a small positive voltage is applied to the gate, an electric field is established across the gate oxide.
- The gate oxide acts as a capacitor, causing positive charges (holes) in the p-type substrate to be repelled deeper into the substrate, leaving behind immobile negative ions near the surface.
- As these negative charges accumulate, a depletion region forms beneath the gate. <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/777eb3ae-af5b-4f28-80c0-4bf5a2f5590c" />  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/f15ecc07-48e5-4894-acc3-e2461cd3baec" /> <br/>

### Lecture 3: Strong Inversion
- Increasing the gate voltage Vgs, the electric field across the oxide strengthens.
- More holes are pushed away from the surface, expanding the depletion region.
- When Vgs increases further, electrons accumulate at the surface and form an n-type inversion layer. This is called **strong inversion** or **surface inversion**
- The voltage at which strong inversion occurs is known as the threshold voltage  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/20255246-23fa-4ea4-b7c7-32ae55eaa35f" />  <br/>

- With further increase in VGS beyond strong inversion, additional gate voltage attracts more electrons to the surface, increasing the inversion charge density.
- The channel becomes stronger (effectively wider), forming a conductive path between source and drain.
- However, since VDS = 0, there is no electric field to drive electrons from source to drain, so no current flows. Hence, the device remains in the **cutoff region**

#### Role of the Body terminal

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/2bb59ef7-693e-4cb3-9fa4-ddde41906f98" /> <br/>

- Applying a positive voltage to the substrate, an additional reverse bias is observed, as the source is now more negatively charged and the substrate is positively charged.
- This increases the depletion layer width more near the source <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/88327cd7-25cb-4ab5-baca-e9ba650f9cf2" /> <br/>

### Lecture 4: Threshold voltage with positive substrate potential
- As VGS increases, the electric field across the oxide increases, and the depletion region beneath the gate expands in both cases (VSB = 0 and VSB > 0).
- When VSB is positive, the source–body junction becomes more reverse-biased. This increases the electric field between the source and the p-substrate, pulling more holes (positive charges) away from the surface and deeper into the substrate.
- Because more holes are removed from the surface, the depletion region becomes wider compared to the VSB = 0 case. This means a larger amount of negative fixed charge (ionized acceptor ions) is left behind near the surface.
- To achieve inversion, the gate must now supply enough electric field to first balance this larger depletion charge before attracting electrons to form the inversion layer.
- As a result, surface inversion occurs at a higher gate voltage. Therefore, a higher VGS is required to turn the device ON when VSB > 0. This increase in threshold voltage due to body bias is called the **body effect** <br/>

<img width="2128" height="841" alt="image" src="https://github.com/user-attachments/assets/872e75b9-8305-4098-8a05-e183cc739a0f" /> <br/>

- Let VGS = VTO be the gate voltage at which the semiconductor surface reaches inversion when VSB = 0.
- In the second case, when VSB > 0, an additional voltage (say V1) is required to overcome the increased depletion charge.
- Therefore, the new gate voltage required for inversion becomes: **VGS = VTO + V1** 

<img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/5b1a280e-ea97-418f-a3b6-45f77d7d3289" /> <br/>

- Vto is the threshold voltage at Vsb=0
- γ is the body effect coefficient, which indicates how strongly the threshold voltage changes with body bias. It depends on substrate doping and oxide capacitance. <br/>

<img width="350" height="200" alt="image" src="https://github.com/user-attachments/assets/4db43a61-73dd-4b57-8220-14ae993c015c" /> <br/>

- φF is the Fermi potential of the substrate, representing the energy difference between the intrinsic level and the Fermi level in the semiconductor <br/>

<img width="350" height="200" alt="image" src="https://github.com/user-attachments/assets/2bf00eeb-9614-4f89-b392-854953ff3d0c" /> <br/>

- These values are obtained from the foundry and fed into the SPICE model for device modelling and simulation

## NMOS resistive region and saturation region of operation
### Lecture 1: Resistive region of operation with small drain-source voltage
- On increasing VGS > Vt, the channel charge density increases
- In the channel, the induced charge Qi is directly proportional to (Vgs - Vt). This excess voltage, known as the overdrive voltage, creates additional mobile electrons in the channel, increasing the drain current.  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/76f212fd-8e55-481c-a80f-9126a104c716" />  <br/>

- Let Vt (NMOS) = 0.45 V, VGS = 1 V and VDS = 0.05 V.
- Since VGS > Vt, the transistor is ON and a conducting inversion channel is formed between source and drain.
- Because the source is grounded and the drain is at a positive voltage, a voltage gradient develops along the channel from source to drain.
- If we plot a graph with the x-axis as the channel length (from 0 to L, considering L ≈ Leff) and the y-axis representing channel charge/strength:
    - In the absence of VDS, every point along the channel sees the same gate overdrive voltage (VGS − Vt).
    - When VDS is applied, the local channel potential becomes V(x), which varies from 0 at the source to VDS at the drain.
    - Therefore, the effective overdrive at any point x becomes (VGS − V(x) − Vt), meaning the channel charge gradually decreases from source to drain. <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/6298ab08-fca4-4868-a012-9b56a973c8f4" />  <br/>

| Parameter | Defination |
|------------|------------|
| Channel Length (L) | The physical distance between the source and drain defined during fabrication (layout dimension). |
| Effective Channel Length (Leff) | The actual conductive channel length after accounting for lateral diffusion and short-channel effects |

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/7728045d-565e-4360-a89f-7d23a46edf07" />

### Lecture 2: Drift current theory
- In the channel (yellow region below), the induced inversion charge at any point x depends on the local gate overdrive voltage.
- Since the channel potential varies along its length, the effective gate voltage at position x is VGS − V(x).
- Therefore, the inversion charge per unit area at point x is proportional to the local overdrive voltage  <br/>

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/3e7df49a-3515-41b9-93ef-596a45fcfb20" />  <br/>

- Where Cox is the gate oxide capacitance per unit area. It represents the capacitance formed between the gate and the channel through the thin oxide layer <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/0d5a8931-ccce-441f-9a23-f5b1a64e3bc1" /> <br/>

- There are two types of current
1. Drift current - Current that flows due to an applied electric field (potential difference), which causes charge carriers to move in a specific direction.
2. Diffusion current - Current that flows due to a concentration gradient, where charge carriers move from a region of higher concentration to a region of lower concentration <br/>
        
```Drift current (Id) = Velocity of charge carriers x Available charge (over the channel width)```

<img width="700" height="800" alt="image" src="https://github.com/user-attachments/assets/8ca8f8bd-3c14-4416-b3bb-4a74467fa8a2" />

### Lecture 3: Drain current model for linear region of operation

<img width="700" height="800" alt="image" src="https://github.com/user-attachments/assets/f9f14a0b-88c8-42a1-9881-275c03df6fcb" /> <br/>

- Considering kn= unCox, where kn is the process transconductance, which determines how effectively the device converts gate voltage into drain current.

<img width="700" height="300" alt="image" src="https://github.com/user-attachments/assets/c4234c25-b9d5-43a8-a704-294359f89974" />  <br/>

- As the current equation is still quadratic, on further simplification, we obtain

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/0a8a4cc8-0986-4d8f-b109-9e3edfdf46e1" /> <br/>

- Therefore, for all values of VDS ≤ (VGS − Vt), the MOSFET operates in the resistive (linear) region.
- In this region, the channel is continuous from source to drain, and the device behaves like a voltage-controlled resistor.

### Lecture 4: SPICE conclusion to resistive operation
- To analyze the impact of VGS and VDS on the drain current (ID), we consider different values of both voltages.
- For a given VGS, the device remains in the linear (triode) region as long as: VDS < (VGS − Vt).
- To calculate ID for different values of VGS, we fix a particular VGS and then sweep VDS from 0 up to (VGS − Vt).
- In this region, ID follows the linear-region equation, and SPICE simulations can be used to obtain and verify the ID–VDS characteristics for each VGS.
  
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/c7f604bc-7e9f-48fb-a48b-a6753add9850" />

### Lecture 5: Pinch-off region condition
- When (VGS − VDS) > Vt, the effective gate voltage at the drain end is still greater than the threshold voltage. This means inversion is maintained even at the drain side
- Since inversion exists along the entire channel from source (x = 0) to drain (x = L), a continuous conducting path connects source and drain.
- In this condition, the device operates in the linear (triode) region, and the drain current increases approximately linearly with VDS for small values of VDS.

<img width="1000" height="900" alt="image" src="https://github.com/user-attachments/assets/642a659d-11ae-4277-af57-a5127d9f2616" /> <br/>

- When (VGS − VDS) = Vt, the effective gate-to-channel voltage at the drain end becomes exactly equal to the threshold voltage required for surface inversion.
- This means that at the drain end, the surface is just at the onset of inversion — the inversion charge density becomes zero at that point.
- Since the inversion layer disappears at the drain side, *the channel no longer extends fully to the drain*. This is called **pinch-off**.
- At pinch-off, the channel disappears only at the drain end, but the current does not stop flowing. Electrons reaching the pinch-off point are swept across the depletion region to the drain due to the strong electric field. As a result, the drain current no longer increases linearly with VDS

<img width="1000" height="900" alt="image" src="https://github.com/user-attachments/assets/9d34e16f-3108-4459-8380-50276c28848c" />  <br/>

- When VDS exceeds (VGS − Vt), the MOSFET enters the saturation region. At this point, the drain end no longer satisfies the inversion condition, and pinch-off occurs near the drain.
- Since the local channel potential reduces the effective gate voltage, the effective overdrive at any point along the channel is given by (VGS − V(x)). As V(x) increases from source to drain, the inversion charge decreases toward the drain end.
- As VDS increases further beyond (VGS − Vt), the pinch-off point moves slightly toward the source.

<img width="1000" height="900" alt="image" src="https://github.com/user-attachments/assets/e8735840-bd6f-49a4-8b28-d5d8795cdb3d" />

### Lecture 6: Drain current model for saturation region of operation
- When (VGS − VDS) ≤ Vt, the channel disappears at the drain side 
- In saturation, the channel voltage remains approximately constant at (VGS − Vt), unlike the linear region where it varies with V(x)
- The drain current ideally becomes independent of VDS and depends mainly on (VGS − Vt), assuming channel length modulation is neglected <br/>

``` Id = kn/2 (Vgs-Vt)^2``` <br/>

<img width="700" height="350" alt="image" src="https://github.com/user-attachments/assets/11105eee-d639-4614-84b0-1aa2d9e63cc7" />  <br/>

- In saturation, the MOSFET ideally behaves like a constant current source.
- However, the current is not completely independent of VDS. As VDS increases, the depletion region at the drain expands.
- This expansion reduces the effective conductive channel length. As the effective channel length decreases, the drain current increases slightly with VDS. This effect is known as **channel length modulation**

<img width="700" height="350" alt="image" src="https://github.com/user-attachments/assets/869dd17e-c959-4948-b493-f787e2c240a5" />

## Introduction to SPICE
### Lecture 1: Basic SPICE setup
- SPICE uses predefined device models to represent transistors and other circuit elements accurately.
- The user provides circuit inputs through a netlist, which describes the components and their connections.
- SPICE then simulates the circuit and generates waveforms and output data.
- These results can be used to calculate delays, characterize cells, and further support analyses such as Static Timing Analysis (STA) and other performance evaluations

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/a78befdd-b4c7-466a-a5f0-7f59ca8e45a3" />  <br/>

- Parameters such as VTO, kn′, γ, and λ (highlighted in brown in the image above) are fixed for a given technology node.
- These are called technology constants, as they depend on the fabrication process and device characteristics.
- They are provided by the foundry and are defined in the SPICE model file used by the simulation engine.

<img width="700" height="800" alt="image" src="https://github.com/user-attachments/assets/9c19ab7d-9d48-483d-b0b4-5fbfd6be154c" />

- When we provide the SPICE model parameters (technology file) and the SPICE netlist (circuit description) to the SPICE engine, the simulator computes the device characteristics.
- By performing a DC sweep, we can obtain Id vs Vds curves for different values of Vgs.
#### SPICE Netlist:
- The device must be described in a specific syntax format understood by the SPICE engine.
- We define the MOSFET with its node connections (Drain, Gate, Source, Bulk), W/L values, and bias sources.
- The circuit equivalent of the given MOSFET is modeled as shown, and the simulator internally uses the model parameters to compute the electrical behavior.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/35343460-df67-4086-bb9e-009b3c647090" />

- In the SPICE netlist, the MOSFET is defined using four nodes: **Drain, Gate, Source, Bulk (Body)**
- Voltage sources are connected to apply VGS and VDS, while the bulk is usually tied to VSS (ground) for NMOS.
- The simulator does not model the physical cross-section directly; instead, it uses the mathematical model parameters from the model file to compute the electrical behavior.
- A gate protection resistor is added to limit sudden current spikes into the gate.
- Although the MOSFET gate ideally draws no DC, it has gate capacitance, so during switching, a large transient current can flow. The resistor protects the gate oxide and the driving circuit.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/b441358f-688c-43c7-b7ad-74c95d9f6411" />

### Lecture 2: Circuit description in SPICE syntax
1. Analyse and note all parameter values

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/fbab34c1-4268-4f01-93fe-34b62e8a043e" />

2. Defining the nodes
    - Every element in the circuit must be connected between two electrical points called nodes.
    - A node is any junction where two or more components meet, and it must be uniquely named in the SPICE netlist.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/98bdbe35-2c31-4761-aeb4-aa7fba40c5cc" />

3. Naming the nodes

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/54281126-fdc5-49ac-bc03-9dc6c5ca0694" />

4. Defining the spice netlist
- MOSFET lies between four nodes so ```M1 vdd n1 0 0 nmos W=1.8u L=1.2u ```
    - M1 → Device name (MOSFET instance)
    - vdd → Drain node
    - n1 → Gate node
    - 0 → Source node
    - 0 → Body node
    - nmos → Model name (From the technology file)
    - W=1.8u L=1.2u → Device dimensions
- **Common Nomenclature** (for MOS): ```Device_name Drain_pin Gate_pin Source_pin Body_pin Model_name Device_dimensions```
#### Netlist
```
M1 vdd n1 0 0 nmos W=1.8u L=1.2u  
R1 in n1 55  
Vdd vdd 0 2.5
Vin in 0 2.5
```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/45e92aa6-5916-4f53-8b8d-074c08e2d59b" />

### Lecture 3: Define technology parameters
- Defining and evaluating the model: The MOSFET model (nmos) is defined in the technology/model file, where all device parameters (VTO, kn′, γ, λ, etc.) are specified. The SPICE engine uses this model to compute device behavior.
- For smaller technology nodes, higher accuracy in parameter extraction is required because short-channel effects and non-idealities become more significant.
- The model name used in the MOSFET line (e.g., nmos) must exactly match the name defined in the netlist (model definition statement)
- If the netlist uses ```M1 ... nmos ...,``` then the model definition must be:  <br/>
```
.MODEL nmos NMOS (...)
```
- The model type (NMOS/PMOS) and its parameters must remain consistent; otherwise, SPICE will throw an error or simulate the wrong device behavior.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/58503833-bdcb-4efe-8089-a46aabf80615" />

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/7f14ff99-acce-409f-988c-0cba5f5d8bfd" />

- nmos → Model name (must match the name used in the netlist).
- NMOS → Device type
- TOX → Oxide thickness
- VTH0 → Zero-bias threshold voltage
- U0 → Carrier mobility
- GAMMA1 → Body effect coefficient

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/50dd1f4f-01c3-44fd-82a0-e7398c107f6e" />

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/7ce0beaa-637d-469a-b860-4073921a380a" />

- The NMOS and PMOS models are defined inside a model library file (xxxx_025um_model.mod). This file contains all technology parameters under a library name
- In the main netlist, the model file is included using: ```.LIB "xxxx_025um_model.mod" CMOS_MODELS```
- This links the circuit netlist to the technology model definitions.
- After including the model file, we can perform DC sweeps of VGS and VDS to obtain the device characteristics.

### Lecture 4: First SPICE simulation
1. Open VirtualBox
2. Git clone ```git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git```

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/d5774d32-8808-4924-b12a-309b320417d3" />

3. A folder named sky130CircuitDesignWorkshop will be created after setup.
4. In the terminal, navigate to the design directory: ```cd sky130CircuitDesignWorkshop/design/```
5. Use the ```ls``` command to list the files inside the design folder

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/a2e0fde2-c67f-49c0-a84e-6d95ec848127" />

6. To view the available cells and models, navigate to the sky130_fd_pr folder: ```cd sky130_fd_pr/```, then list the contents using ```ls```
7. Move into the cells directory ```cd cells/```. This folder contains device folders ```nfet_01v8``` and ```pfet_01v8``` 

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/32197317-810a-4550-a5ac-4a3aecb49705" />

8. Inside the ```nfet_01v8``` folder, to view the different library files corresponding to various process corners (e.g., TT, FF, SS, etc.), use ```ls```. These files define the NMOS model parameters for different operating conditions and process variations.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/0bbac31d-1912-4549-88bc-bcab682d8f1a" />

9. For the Typical (TT) corner, open the model file using ``` less sky130_fd_pr__nfet_01v8___tt.pm3.spice```. This file contains all the NMOS model parameters defined for the TT process corner.
10. To exit the file type ```q```

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/a883e8cc-0c22-41a7-b26d-1aae4cee6efd" />

11. The available W and L values are predefined inside ```sky130_fd_pr__nfet_01v8___tt.corner.spice``` file. For simulation, the chosen W and L must match one of the values specified in the library.
If unsupported dimensions are used, the simulator may throw an error.

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/6641980f-ff02-44b6-944e-83635164ed05" /> <br/>

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/6cf7dc42-c877-417f-bb10-17fa9731b549" />

12. Going back to the models file by ```cd ../../models```. We can find ```sky130.lib.spice```. This file contains all the library files for nfet and pfet for different corners

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/fa5d0afa-a6d6-43b5-8baa-d89fd58a60d4" />  <br/>

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/893b555a-2e09-435d-9dfb-3ab6192dc346" />

13. For further simulations, go back to the ```design``` folder and open ```day1_nfet_idvds_L2_W5.spice``` using ```vim day1_nfet_idvds_L2_W5.spice```

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/4e8c93c6-19a1-4784-a4f3-92d7a85cd925" />  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/2abdcbc4-5dff-4879-b727-8dbf835cf726" /> <br/>

- The green box indicates the attached Sky130 library file
- The yellow box specifies the process corner being used.
    - tt → Typical-Typical
    - sf → Slow-Fast
    - ff → Fast-Fast
    - ss → Slow-Slow
- The selected corner determines which set of model parameters is used during simulation.
- **Netlist description** <br/>
```
XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=5 l=2
R1 n1 in 55
Vdd Vdd 0 1.8
Vin in 0 1.8
```
- The NMOS model used is sky130_fd_pr__nfet_01v8.
- The W and L values are chosen from the corresponding corner.spice file to ensure valid dimensions for simulation.
- The supply voltage used for this device is 1.8V, as it is a 1.8V NMOS variant.
- **Simulation commands**  <br/>
```
.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2
```
- Vds is swept from 0 to 1.8 with a step of 0.1V and Vgs with a step of 0.2V

14. To run this file and obtain I vs V curve use the command ```ngspice day1_nfet_idvds_L2_W5.spice```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/b82a8d08-3feb-4253-ae03-62139dc20565" />

15. To plot the Id curve run the command ```plot -vdd#branch```. We obtain the Id vs Vds graph for different values of Vgs

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/44044d36-9120-4960-84d1-c28813cab087" /> <br/>

<img width="700" height="800" alt="image" src="https://github.com/user-attachments/assets/7954e1e0-4002-4ce9-b179-1a3a8cada1f5" />  <br/>

- Initially, as VGS increases (just above Vt), the drain current increases quadratically with respect to Vgs-Vt
- At higher VGS values, the behavior gradually becomes more linear, mainly due to mobility degradation and other non-ideal short-channel effects
- To view the current at a specific point on the graph, left-click on the required point. The corresponding coordinate values are displayed in the terminal. The Y-coordinate represents the drain current (Id) at that operating point.

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/09938891-901c-44c7-9c65-097ac5d1a844" />

### Lecture 5: SPICE Lab with sky130 models
- Open ```sky130.lib.space``` file in ```models``` <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/df4bc6b1-3aca-4e97-bab3-13a50ea3aa2a" />  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/1e7970c8-afcc-4997-9d6c-4506d7f8108d" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/d3e42812-3322-4704-be90-03b0dd776f69" /> <br/>

- The scale in which the parameter dimensions are defined can be obtained in the ```all.spice``` file <br/>

- Cut off region analysis <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/9d8e8aa3-c0d8-48fb-a80a-458f474f1655" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/2dbf88d9-05a6-40a6-b4d0-d031f38b3cc6" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/878710f0-e6b3-4631-bea5-a3521ae04228" /> <br/>

- A very small current can be observed for lower Vgs (Vgs=0.4V)
- For the device to be ON, Vgs>= Vt, the current is very minimal, as the transistor is in the cut-off region

# Day 2: Velocity saturation and basics of CMOS inverter VTC

## SPICE simulation for lower nodes and velocity saturation effect

### Lecture 1: WSPICE simulation for lower nodes

- w=5um and L = 2nm : w/L = 2.5  <br/>

<img width="800" height="800" alt="Screenshot 2026-02-17 182134" src="https://github.com/user-attachments/assets/2738a4c4-a233-4926-87a4-f5ef16929429" />  <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/ab3d9d48-fd63-44c2-bc9f-ee408eb4ec8b" /> <br/>

- To the left of the blue line, the drain current increases approximately linearly with drain voltage. In this region, the MOSFET operates in the linear (resistive) region
- To the right of the blue line, the drain current is almost constant; however, a slight increase can be observed due to channel length modulation, indicating operation in the saturation region

- w=0.375u and L=0.25u

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/69a58c20-12da-4cc1-8419-9265338e5ed2" />  <br/>

- w=1.8u and L=1.2u

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/76c5c87c-60ae-431d-90bb-302955636d8c" /> <br/>

- Now, we choose different values of W and L, keeping the ratio W/L the same as before. Ideally, since Id ∝ (W/L), the drain current should remain unchanged.
- However, in practice, the drain current does change due to second-order effects such as mobility degradation, channel length modulation, series resistance, and short-channel effects.
- Below is the SPICE deck where only W and L values are modified, while all other parameters remain unchanged.

### Lecture 2: Drain current vs gate voltage for long and short channel devices

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/6f0a039a-69ae-489d-bd00-7727217120ab" /> <br/>

- For a long-channel device, observing Id at VDS = 2.5 V for different VGS values shows a quadratic dependence of Id on VGS (Id ∝ (VGS − Vt)²).
- For a short-channel device at VDS = 2.5 V, the drain current increases approximately linearly with VGS due to velocity saturation, which limits carrier velocity and alters the ideal square-law behavior.

#### Velocity Saturation effect
- In short-channel MOSFETs, when the electric field becomes very high (due to large Vds), the carrier velocity does not keep increasing linearly with the field.
- Normally, carrier velocity increases proportionally with electric field, but at high fields it reaches a maximum value called the saturation velocity (v_sat).
- Because of this, the drain current no longer follows the ideal square-law relation Id ∝ (Vgs − Vt)².
- Instead, in short-channel devices, the current becomes approximately linear with (Vgs − Vt) in saturation.

#### Id vs Vgs graph
- Keeping Vds constant at 2.5 V, Vgs is varied.
- The corresponding drain current (Id) is plotted for both cases (long-channel and short-channel devices).


- w=1.8u and L=1.2u (Long channel)

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/92bb5264-3f13-42b7-a281-f8c8a4be634d" /> <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/5bb23b1f-3f43-4744-9e0c-05cc50047a64" /> <br/>

- w= 0.375u and L=0.25u (Short channel)

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/f68cc496-2835-47a1-ad6e-9f3472b18819" /> <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/2c9222b2-c391-4dfa-8f84-09f1410833d2" />  <br/>

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/e699a5a4-04e8-43b3-9443-c68c9e0b9b09" /> <br/>

1. W = 1.8u, L = 1.2u → Long-channel device
    - Shows a more quadratic (square-law) behavior.
    - Id increases slowly near threshold and then rises rapidly as Vgs increases.
    - Follows approximately Id ∝ (Vgs − Vt)².

2. W = 0.375u, L = 0.25u → Short-channel device
    - Shows a more linear behavior at higher Vgs.
    - Deviation from square-law due to velocity saturation.
    - Id increases almost linearly with Vgs in saturation.

### Lecture 3: Velocity saturation at lower and higher electric fields

- For a short-channel device, the Id vs Vgs curve shows more linear behavior as Vgs increases.
- This happens due to the velocity saturation effect, where carrier velocity reaches its maximum limit at high electric fields, preventing the current from following the ideal quadratic relationship.

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/175324b9-81d2-4442-997c-d5b35b50a4a1" /> <br/>

- For lower values of electric field, carrier velocity increases linearly with the electric field.
- After a certain field (critical field), the velocity reaches a maximum value and saturates.
- This happens due to increased scattering effects at high electric fields, which limit further acceleration of carriers.

<img width="1708" height="558" alt="image" src="https://github.com/user-attachments/assets/b23c4fa2-25a2-45b3-9e66-da108fe68941" />

#### Scattering effects
- As electrons move in the channel, they continuously collide with lattice atoms. These collisions are called scattering events.
- At low electric fields, electrons gain small energy between collisions, so velocity increases almost linearly with the field.
- At high electric fields, electrons gain large energy, which increases lattice vibrations (phonons). Increased lattice vibrations cause more frequent collisions (phonon scattering).
- Because of these frequent scattering events, electrons cannot accelerate further, and their velocity reaches a maximum value
#### Modelling the velocity
- Boundary conditions:
    1. For electric field ```E ≤ Ec``` (critical field): Electron velocity vn increases linearly with electric field
    2. For electric field ```E ≥ Ec```: Electron velocity reaches saturation velocity (vsat) and becomes approximately constant <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/37cc8772-867e-442b-96f6-150ae09ab5ca" /> <br/>

- For continuity substituting E=Ec we obtain  <br/>

<img width="250" height="100" alt="image" src="https://github.com/user-attachments/assets/b7b377da-11af-419f-9126-5480e39066be" />  <br/>

- Rederiving the drain current equations  <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/8a107a30-315e-43ee-af9d-4077977ff87c" />  <br/>

| Region                  | Long Channel                     | Short Channel                         |
|--------------------------|--------------------------------------------------|---------------------------------------------------|
| Cutoff                   | No channel formation (Vgs < Vt)                 | No channel formation (Vgs < Vt)                  |
| Resistive (Linear)       | Id increases linearly with Vds                  | Id increases linearly with Vds                   |
| Velocity Saturation      | Not significant                                 | Carrier velocity saturates at high electric field |
| Saturation               | Id ∝ (Vgs − Vt)² (square-law behavior)         | Id ≈ linear with (Vgs − Vt)                      |

<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/d49f67d8-f2b6-42bc-982d-684286567eb4" />

### Lecture 4: Velocity saturation drain current model

- Define Vgt = Vgs − Vt (gate overdrive voltage), since analysis is performed at higher Vgs values.
- The drain current equation is expressed in terms of Vgt.
- For lower values of Vds, the channel length modulation term (λVds) is neglected.
- Vdsat is a technology parameter
    - It represents the drain-to-source voltage at which the device enters the velocity saturation region.
    - Beyond Vdsat, carrier velocity saturates and the drain current deviates from ideal quadratic behavior.

<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/59c16b70-770a-4388-939f-c534726b0de1" />

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/1be510ce-cafe-424e-a1da-5b1091844b1a" />

- The saturation current for lower technology nodes is comparatively smaller instead of larger.
- This occurs due to the velocity saturation effect, which becomes more dominant in short-channel devices.
- In lower nodes, the electric field along the channel becomes very high even at small Vds. As a result, carrier velocity reaches its saturation value earlier.
- Since carrier velocity cannot increase beyond the saturation velocity, the drain current stops increasing proportionally.
- Therefore, the peak (saturation) current observed in lower nodes is significantly less compared to higher (long-channel) nodes.

<img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/f80dfba4-8413-4ff9-9fb0-b6e749416536" />

### Lecture 5: Labs Sky130 Id-Vgs
#### Id vs Vds
- Open ```day2_nfet_idvds_L015_W039.spice``` <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/4b5f41a2-9aff-424f-986f-c0c2c174d738" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/5f87e6c5-19d8-4cdd-9fa7-9a3842e856dd" /> <br/>

- w=0.39u and L=0.15u
- Perform DC simulation using ```ngspice```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/d9a4bf5c-5bda-4793-a43d-3a478b9c83d1" />  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/3fbda566-0c16-48cf-8178-04412b18b9b9" /> <br/>

- For lower values of Vgs (just above Vt), the drain current shows a quadratic behavior with respect to (Vgs − Vt).
- For higher values of Vgs, the behavior becomes more linear, mainly due to velocity saturation effects in short-channel devices.
- Peak current is about 197uA

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/f4a9996f-b69b-4a44-9715-009eb300457b" /> <br/>

#### Id vs Vgs
- Open ```day2_nfet_idvgs_L015_W039.spice```
- Perform DC simulation using ```ngspice```  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/f6ec26a3-892a-46a3-8960-dcb3ed33da04" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/61fc6887-cfc1-4738-8903-3012be506a3b" /> <br/>

### Lecture 6: Labs Sky130 Vt
- Open ```day2_nfet_idvgs_L015_W039.spice```
- Run ```ngspice```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/9e8a6845-3c6e-4dad-b344-99154f0a187c" /> <br/>

- Plot Id current (vdd-branch)

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/1a0da406-0d8b-4a6b-9b02-62016fd36164" />  <br/>

- Threshold voltage (Vt) is obtained by drawing a tangent at the maximum slope of the Id–Vgs curve and extending it to intersect the Vgs axis
- Threshold voltage, ```Vt=0.737V```

## CMOS voltage transfer characteristics (VTC)
### Lecture 1: MOSFET as a switch
- When |Vgs| < |Vt| → No inversion channel is formed → Device is OFF (open switch).
- When |Vgs| > |Vt| → Inversion channel forms between source and drain.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/33feb817-4f2c-4a8d-8e02-32ccaa1495f5" />  <br/>

- Infinite OFF resistance when |Vgs| < |Vt| → Device behaves as an open circuit.
- Finite ON resistance when |Vgs| > |Vt| → Device behaves as a closed switch

#### Complementary MOS Transistors
##### Case 1: Vin = Vdd (Input High)

- When the input Vin is equal to Vdd, the PMOS transistor turns OFF because its gate-to-source voltage becomes zero. At the same time, the NMOS transistor turns ON since its gate-to-source voltage equals Vdd and exceeds the threshold voltage.
- In this condition, the PMOS behaves like an open switch and the NMOS behaves like a closed switch. As a result, the output node is connected to Vss through the NMOS, and the load capacitor discharges.
- Therefore, the output voltage Vout becomes logic LOW.

##### Case 2: Vin = 0 (Input Low)

- When the input Vin is equal to 0 V, the NMOS transistor turns OFF because its gate-to-source voltage is zero. Meanwhile, the PMOS transistor turns ON since its gate-to-source voltage equals Vdd in magnitude and exceeds the threshold voltage. 
- In this case, the NMOS behaves like an open switch and the PMOS behaves like a closed switch. Consequently, the output node is connected to Vdd through the PMOS, and the load capacitor charges.
- Therefore, the output voltage Vout becomes logic HIGH.


<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/8bfbcb84-1d6a-4cbd-b2b6-41e20faa4cb2" />

### Lecture 2: Introduction to standard MOS voltage current parameters
- To derive the equivalent circuit of the CMOS inverter, the input is evaluated at logic HIGH and logic LOW conditions. This allows the extraction of the Voltage Transfer Characteristics (VTC) and the subsequent estimation of cell delay.
    - When Vin = Vdd (logic HIGH), the PMOS transistor is in cutoff (OFF state), and the NMOS transistor operates in the ON state. The output node is connected to ground through the NMOS, forming the pull-down equivalent circuit.
    - When Vin = 0 (logic LOW), the NMOS transistor is in cutoff (OFF state), and the PMOS transistor operates in the ON state. The output node is connected to Vdd through the PMOS, forming the pull-up equivalent circuit.
  
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/a2132ee6-dbb4-4d7c-a891-5654563e57ed" /> <br/>

- During steady-state operation (static HIGH or LOW), only one device conducts at a time.
- In dynamic switching conditions, the instantaneous currents satisfy: ```Idsp = −Idsn``` indicating that the currents are equal in magnitude and opposite in direction at the output node (by Kirchhoff’s Current Law).

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/db0be880-1ec4-426c-bc18-6dd2ee212f41" /> <br/>

#### CMOS Naming convention
- G = Gate  
- S = Source  
- D = Drain  

- Vgs = Gate-to-Source voltage  
- Vds = Drain-to-Source voltage  

- Vgsn = Gate-to-Source voltage of NMOS  
- Vgsp = Gate-to-Source voltage of PMOS  
- Vdsn = Drain-to-Source voltage of NMOS  
- Vdsp = Drain-to-Source voltage of PMOS

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6fa00e5a-fc21-472f-b9ef-a2c7f906319f" />

### Lecture 3: PMOS/NMOS drain current v/s drain voltage

<img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/a4238ab3-3376-4d4c-b5a6-e9b0d70d2484" />

#### Deriving equations for Vgsn, Vgsp, Vdsn, and Vdsp

<img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/dea48547-7675-4b39-8977-a931bf8944a2" /> <br/>

| NMOS (Idsn vs Vgsn) | PMOS (Idsp vs Vgsp) |
|-----|-----|
| <img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/57e85516-1a9e-4d11-8d8e-58dae8fda3fe" /> | <img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/ddb7c1b2-5bb4-4c46-99d0-1a2daad86209" /> |
| As Vgsn increases, the drain current Idsn increases | As the magnitude of Vgsp increases (more negative), Idsp increases in magnitude |
| At low Vdsn, the device operates in the linear region | At small \|Vdsp\|, it operates in the linear region |
| At higher Vdsn, it enters saturation where the current becomes nearly constant | At larger \|Vdsp\|, it enters saturation where the current becomes nearly constant |

### Lecture 4: Step1 – Convert PMOS gate-source-voltage to Vin

- As a digital logic circuit, the CMOS inverter is characterized only by two measurable node voltages: Vin and Vout, since internal device node voltages cannot be directly observed.
- Therefore, the voltage transfer characteristics (VTC) and delay modeling must be expressed purely as functions of Vin and Vout

#### Deriving Voltage Transfer characteristics for static CMOS inverter
- Let us assume that it is a long channel device and ```Vdd= 2V``` <br/>

| Vgsp | V | Vin (Vgsp+Vdd) |
|----| ----|----|
| Vgsp1| 0 | 2 |
| Vgsp2| -0.5 | 1.5 |
| Vgsp3| -1 | 1 |
| Vgsp4| -1.5| 0.5 |
| Vgsp5| -2 | 0 |

- By modifying the PMOS transfer characteristics using ```Vgsp = Vin-Vdd``` and ```Idsp = -Idsn```, the PMOS curve can be expressed in terms of the same variables used for the NMOS, enabling direct comparison and combination.

<img width="900" height="700" alt="image" src="https://github.com/user-attachments/assets/ce4a0eea-aa0d-44c1-8bd0-f1472dc89517" /> <br/>

- The Vgsp term is therefore eliminated by rewriting it in terms of Vin
- The magnitude of Idsp remains equal to Idsn, but with opposite sign, ensuring current continuity at the output node

### Lecture 5: Step2 & Step3 – Convert PMOS and NMOS drain-source-voltage to vout
- Since the transfer characteristics are still expressed as a function of Vdsp, which corresponds to an internal device voltage, it must be substituted in terms of external node variables.

| Vdsp | V | Vout (Vdsp+Vdd) |
|----| ----|----|
| Vdsp1| -2 | 0 |
| Vdsp2| -1.5 | 0.5 |
| Vdsp3| -1 | 1 |
| Vdsp4| -0.5| 1.5 |
| Vdsp5| 0 | 2 |

- Rewriting Vdsp using the circuit-level relationship ```Vout = Vdd + Vdsp```, we obtain

<img width="1000" height="700" alt="image" src="https://github.com/user-attachments/assets/fce9c30d-261f-4b5a-8f4b-97dd7ebc5c2d" /> <br/>

- When Vout = 2 V (with Vdd = 2 V), the drain-to-source voltage of the PMOS becomes Vdsp = 0 V. Under this condition, the PMOS current becomes zero because there is no voltage drop across it. The output capacitor CL is fully charged, and no further current flows. This represents the steady-state HIGH output condition of the CMOS inverter.
- When Vout = 0 V (with Vdd = 2 V), the magnitude of Vdsp becomes 2 V. In this condition, a finite current can flow depending on the applied Vin. Since the output node is at ground potential, the load capacitor CL is fully discharged. To transition the output back to HIGH, a charging current must flow from Vdd through the PMOS to charge CL
- Similarly, the NMOS load curve can be derived using the relationships ```Vgsn = Vin``` and ```Vdsn = Vout```, the NMOS current equations can be rewritten entirely as functions of Vin and Vout


| Vgsp | V | Vin (Vgsn) |
|----| ----|----|
| Vgsp1| 0 | 0 |
| Vgsp2| 0.5 | 0.5 |
| Vgsp3| 1 | 1 |
| Vgsp4| 1.5| 1.5 |
| Vgsp5| 2 | 2 |

<img width="1000" height="700" alt="image" src="https://github.com/user-attachments/assets/c3d08d9e-dae4-4426-aa83-ef8bf647bd90" /> <br/>

### Lecture 6: Step4 – Merge PMOS – NMOS load curves and plot VTC
- By appropriately superimposing the PMOS and NMOS load curves under the condition that their drain currents are equal in magnitude and opposite in direction, the CMOS Voltage Transfer Characteristics (VTC) are obtained

<img width="800" height="700" alt="image" src="https://github.com/user-attachments/assets/6f2c97d1-e17c-4e40-9297-67caf5ded14c" /> <br/>

- To obtain the CMOS Voltage Transfer Characteristics (VTC), the NMOS and PMOS load curves are superimposed. The operating point for each value of Vin is determined by the condition where the magnitude of NMOS and PMOS drain currents are equal

<img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/6fe2f3c6-8352-433a-9604-7ad2e1bb86ee" /> <br/>

- Since Vdd = 2 V, both Vin and Vout vary within the range 0 V to 2 V
    - When Vin = 0 V, Vout = 2 V. The NMOS is in cutoff, and the PMOS operates in the linear region.
    - When Vin = 0.5 V, Vout lies between 1.5 V and 2 V. The NMOS operates in saturation, while the PMOS remains in the linear region.
    - When Vin = 1 V, Vout lies approximately between 0.5 V and 1.5 V. Both NMOS and PMOS operate in saturation.
    - When Vin = 1.5 V, Vout lies between 0 V and 0.5 V. The NMOS operates in the linear region, while the PMOS operates in saturation.
    - When Vin = 2 V, Vout = 0 V. The NMOS operates in the linear region, and the PMOS is in cutoff.

| Vin (V) | Vout (V) Range | NMOS Region | PMOS Region |
| ------- | -------------- | ----------- | ----------- |
| 0       | 2              | Cutoff      | Linear      |
| 0.5     | 1.5 – 2        | Saturation  | Linear      |
| 1       | 0.5 – 1.5      | Saturation  | Saturation  |
| 1.5     | 0 – 0.5        | Linear      | Saturation  |
| 2       | 0              | Linear      | Cutoff      |

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/becc7f26-481b-4e25-b3a0-dd739c1bcc18" />

# Day 3 - CMOS Switching threshold and dynamic simulations
## Voltage transfer characteristics – SPICE simulations
### Lecture 1: SPICE deck creation for CMOS inverter
- Creating the SPICE deck involves defining the circuit connectivity (netlist), specifying input stimulus conditions, declaring technology/model parameters, and identifying the required output nodes for probing and measurement.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/b631ffee-fe1c-43c5-a4ed-2251ae220ae9" /> <br/>

- M1 represents the PMOS transistor and M2 represents the NMOS transistor.  
- Proper substrate (bulk) connectivity must be defined for both devices to accurately model body bias effects and threshold voltage behavior.  

| Component | Value |
|------------|--------|
| NMOS Width | 0.375u |
| PMOS Width | 0.375u |
| NMOS Length | 0.25u |
| PMOS Length | 0.25u |
| Cload | 10fF |
| Vin | 2.5 V|
| Vdd | 2.5 V |


- In this setup, both transistors are configured with identical W/L ratios for baseline comparison. However, in practical CMOS design, the PMOS width is typically sized 2x–3x larger than the NMOS to compensate for lower hole mobility and to balance rise and fall delays
- For a 250 nm channel length MOSFET, a nominal supply voltage in the range of approximately 2.5 V is commonly used in conventional long-channel technologies.
- Therefore, the input voltage Vin is typically swept between 0 V and 2.5 V, with 2.5 V representing the logic HIGH level corresponding to Vdd <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/91438719-fb21-40a1-90f3-9bee502f62a8" /> <br/>

- **Identifying the nodes** <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/9571ca53-453a-42d6-a4a6-b9b133585543" /> <br/>

- **Naming the nodes** <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/e970db29-5389-408b-8c07-b3d163fe1ce9" /> <br/>

- **Spice deck** <br/>

```
M1 out in VDD VSS pmos w=0.375 L=0.25
M2 out in 0 0 nmos w=0.375 L=0.25
```

### Lecture 2: SPICE simulation for CMOS inverter

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/2711dc95-bf13-451d-ba8d-93de2779d56f" /> <br/>

- **Spice deck** <br/>

```
M1 out in VDD VSS pmos w=0.375 L=0.25
M2 out in 0 0 nmos w=0.375 L=0.25

cload out 0 10f

Vdd vdd 0 2.5
Vin in 0 2.5

.op
.dc Vin 0 2.5 0.5

.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```

- Since 0.375u does not fall within the allowed PMOS width design rules of the SkyWater SKY130 PDK, both transistor widths are updated to 0.7u while maintaining the channel length at 0.25u.  

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/da63760a-5915-4ccd-bb3d-5c0e0b97b66a" /> <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/064d4068-51ea-40d1-87f6-f3df4c108e9a" /> <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/0b676fc1-1033-4bcf-94ea-fb8f6fe41978" /> <br/>

- For Wn/Ln = 2.8 and Wp/Lp=3.8, Wn = 0.375u, Wp = 0.95u, Ln,p=0.25  <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/e119df84-ceeb-442f-9ab9-c28b6481fda4" /> <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/5eae3290-c738-4489-b0ef-91dfb26de18f" /> <br/>


- The previous VTC curve is slightly left-shifted because the NMOS strength is higher than the PMOS strength in that configuration.
- Since the NMOS has higher drive capability, the switching threshold shifts toward a lower input voltage, resulting in the leftward displacement of the transfer curve.

### Lecture 3: Labs Sky130 SPICE simulation for CMOS

- **Transfer characterstics plot**
- Open ```day3_inv_vtc_Wp084_Wn036.spice```, Wn = 0.36u and Wp = 0.84u, Wp/Wn = 2.33

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/23401738-7317-4c65-a501-455767792a95" /> <br/>

- Run ```ngspice``` to obtain the Vtc curve

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/a4e88cd9-64e9-43a7-846f-1b638a2e0f03" /> <br/>
 
- ```plot out vs in ``` in ngspice

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/777eec1c-1bee-4a4a-8721-faca78a46ed6" /> <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/2f46aa8a-7d8b-4bdd-b1a2-73bca381c4bb" />

- Now we need to determine the switching threshold voltage (Vm) from the VTC curve. The switching threshold is the point where: Vin = Vout
- This is the exact point where the inverter transitions and both NMOS and PMOS conduct equally (Ids_n = Ids_p).
- To zoom into this point in the waveform viewer: Right mouse button + hold → drag over the region of interest → release to zoom in.
- Then locate the intersection point where the Vin and Vout curves are equal.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/493682ef-3b85-4a92-aca3-664018faa041" /> <br/>

- We get switching threshold around 0.867 V
- **Transient analysis**
- Open ```day3_inv_tran_Wp084_Wn036.spice```

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/019eb01d-2ccc-423c-b79f-0d3b823e6ad2" />  <br/>

- Run ```ngspice```
- ```plot out vs time in``` in ngspice

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/d16bbe58-8fa2-40f7-8e8f-6302fb208cc6" /> <br/>

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/12fdc67e-7954-4098-be4b-d37e426248b4" /> <br/>

- For rise delay and fall delay, consider 50% of the output voltage, i.e., at 0.9V (since Vdd = 1.8V).
- Measure delay as: Propagation delay = t(out at 0.9V) − t(in at 0.9V)

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/83d2e586-85e9-4f56-9a34-19f7226f1938" /> <br/>

- ```Rise Delay (tpLH) = 2.4637n − 2.1507n = 0.313 nsec```
- For fall delay, consider the falling transition at 0.9V

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/c6abcb24-d6b6-47d8-9ce8-71a246b58594" /> <br/>

- ```Fall Delay (tpHL) = 4.33254n − 4.0492 = 0.2833 nsec```

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/2b2505c1-f9fa-42aa-aa8a-641098731418" /> <br/>

## Static behavior evaluation – CMOS inverter robustness – Switching Threshold

### Lecture 1: Switching Threshold, Vm
- Comparison of two CMOS inverters with different PMOS and NMOS W/L ratios shows that the overall VTC shape remains the same in both cases, while only the switching threshold shifts.
- This indicates that the CMOS inverter maintains its characteristic transfer behavior despite sizing variations. The gain region, rail-to-rail swing, and general curve profile are preserved, demonstrating the robustness of CMOS inverter operation

| Wn/Ln= Wp/Lp = 1.5 | Wn/Ln = 1.5, Wp/Lp = 3.75|
|------|-----|
|Wn = Wp = 0.375 | Wn = 0.375, Wp = 0.9375 |
| Ln = Lp = 0.25u |  Ln = Lp = 0.25u |
| <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/ad0f5415-9806-4ef7-a6ed-9fe1826e1640" /> | <img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/efc6638b-55cd-42d6-83ca-482a940d365d" /> |

- ** Switching Threshold (Vm) ** – The operating point at which Vin equals Vout. This defines the inverter trip point and is a critical parameter for noise margin and timing analysis.
- Vm is obtained by plotting a 45-degree reference line (Vin = Vout) on the VTC curve and identifying the intersection with the inverter transfer characteristic.
- At this operating point, both the NMOS and PMOS devices are simultaneously in saturation region, each conducting significant current.
- A direct current path exists between VDD and GND, resulting in short-circuit current flow. This condition contributes to dynamic power dissipation during switching.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/6b837ca2-490b-49ef-9f96-1f66a42f468d" /> <br/>

- In first graph when Wn/Ln = Wp/Lp , ```Vm ~ 0.9V``` and in second graph with a widder PMOS ```Vm ~ 1.2V```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/e7b72e32-36ae-4452-98cb-279b88084b95" />

### Lecture 2: Analytical expression of Vm as a function of (W/L)n and (W/L)p

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/a84b613e-e9ff-4f6a-8519-55fe3a013b3a" /> <br/>

- Vm is directly dependent on the ratio (Wp/Lp)/(Wn/Ln)
- Increasing PMOS width shifts Vm toward VDD.
- Increasing NMOS width shifts Vm toward GND.
- For symmetric switching (Vm ≈ VDD/2)

### Lecture 3: Analytical expression of (W/L)n and (W/L)p as a function of Vm
- In the derived current equality expression at Vm, all parameters on the RHS are technology-dependent constants obtained from the model file (k’n, k’p, Vtn, |Vtp|, VDD), except Vm.
- Once Vm is known (from the VTC curve), the required (W/L)p / (W/L)n ratio can be calculated directly from the equation.
- This establishes a direct analytical relationship between the switching threshold and the device strength ratio 
- If Vm shifts toward VDD/2, it indicates balanced device strengths 
- If Vm shifts toward ground, NMOS is stronger
- If Vm shifts toward VDD, PMOS is stronger 

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/3010aa11-affa-4658-b540-8eb2fe213641" />

### Lecture 4: Static and dynamic simulation of CMOS inverter
- Behaviour of CMOS for for various ratios of PMOS and NMOS

| Wp/Lp | x · Wn/Ln |
|-------|-----------|
| Wp/Lp | Wn/Ln     |
| Wp/Lp | 2Wn/Ln    |
| Wp/Lp | 3Wn/Ln    |
| Wp/Lp | 4Wn/Ln    |
| Wp/Lp | 5Wn/Ln    |

- **Case 1**: Wp/Lp = Wn/Ln = 0.7u/1.5u
- *DC Analysis* <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/f3a47bf0-c50f-42bd-aba7-c5d486ec2ecf" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/1fab3263-51e2-41d8-a4bd-145f2f8480f0" /> <br/>

<img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/e2fc6bfc-923a-4662-a571-13468b8fafbe" /> <br/>

- Switching threshold ~ 0.83V
- *Transient analysis* <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/f8ff5393-2bc2-4ae0-af7c-b9dcbebdd3a7" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/a52b7566-c799-4478-a212-fa7fe98fc84c" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/06567a0b-c37d-425c-871e-3a44deca2468" /> <br/>

- Rise delay = 2.533n - 2.152n = 0.381nsec
- Fall delay = 4.2104n - 4.0507n = 0.1597nsec

### Lecture 5: Static and Dynamic simulation of CMOS inverter with increased PMOS width
- **Case 2**: Wp/Lp = 2(Wn/Ln)

| Parameter | Value |
|---|----|
| Wn/Ln | 0.7u/0.15u |
| Wp/Lp | 1.4u/0.15u |

- *DC Analysis* <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/0af6670c-b219-4305-8bb5-b14c5fc63a64" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/de5740d5-077b-490a-9e0c-0f309d92495f" /> <br/>

- Switching threshold ~ 0.87V
- *Transient analysis* <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/0935b12e-b536-4b5f-9b6a-72de1b58736e" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/50e134c9-f92c-41d2-be67-9ff83a3fc11f" /> <br/>

- Rise delay = 2.35n - 2.15n = 0.2nsec
- Fall delay = 4.2127n - 4.0525n = 0.1602nsec

- **Case 3**: Wp/Lp = 3(Wn/Ln)

| Parameter | Value |
|---|----|
| Wn/Ln | 0.7u/0.15u |
| Wp/Lp | 1.4u/0.15u |

- *DC Analysis* <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/467f0f31-60e8-46ab-8223-42c4e6c5e0f1" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/242f915e-4145-47c8-9869-8f01461237d9" /> <br/>

- Switching threshold ~ 0.89V
- *Transient analysis* <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/358f100f-3826-43f3-abb4-55c0e9812531" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/77d7304b-72e3-4ed1-92b1-1d45101f00e7" /> <br/>

- Rise delay = 2.3n - 2.14n = 0.16nsec
- Fall delay = 4.22n - 4.051n = 0.169nsec

| Wp/Lp | x · Wn/Ln | Vm | Rise delay | Fall delay |
|-------|-----------|-----------|-----------|-----------|
| Wp/Lp | Wn/Ln     | 0.83V | 0.381nsec | 0.1597nsec
| Wp/Lp | 2Wn/Ln    | 0.87V | 0.2nsec | 0.1602nsec | 
| Wp/Lp | 3Wn/Ln    | 0.89V | 0.16nsec | 0.169nsec |

- The switching threshold Vm shifts upward as PMOS width increases. This occurs because the pull-up network becomes stronger relative to the NMOS
- A stronger PMOS requires a higher input voltage to balance the NMOS pull-down current, thereby moving Vm closer to VDD
- Rise delay decreases with increase in PMOS width (Wp). A larger PMOS provides higher drive current during the charging phase, reducing the time required to charge the output load capacitor (Cload)

### Lecture 6: Applications of CMOS inverter in clock network and STA

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/fcfa904b-6b7d-472b-aa13-5d3904ed1b4e" /> <br/>

- During fabrication, process variations can introduce slight deviations in the physical dimensions of PMOS and NMOS devices from their intended W/L ratios. However, the CMOS inverter demonstrates strong robustness, as moderate sizing variations do not cause significant shifts in the switching threshold (Vm)
- The transfer characteristic remains stable, and Vm typically does not deviate drastically unless there is a substantial imbalance in device strengths
- When Wp = 2Wn, the rise and fall delays become approximately equal. This compensates for the lower hole mobility in PMOS compared to the electron mobility in NMOS
- Achieving equal rise and fall delays improves timing predictability, reduces duty-cycle distortion, and ensures balanced switching behavior
- This balanced operation reflects the inherent symmetry of the CMOS inverter, making it a highly reliable and scalable digital building block

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/5b3fd4cd-77c3-40b8-b0f0-6325ebe38cfa" /> <br/>

- It is the typical characteristics of clock inverters and buffers, where propagation delay symmetry (tphl = tplh) is a key design

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/bb4ebd23-6953-4184-aa15-f931f323fec3" /> <br/>

- If delays are not equal, the output waveform becomes asymmetric, causing duty cycle distortion in clock distribution networks. This leads to unequal high and low pulse widths at sequential elements, potentially impacting setup/hold margins
- Unequal rise and fall delays introduce transition-dependent delay variation across buffers, increasing clock skew and degrading timing predictability in large clock trees. Over multiple stages, this asymmetry accumulates and can significantly affect overall timing closure <br/>

- If the primary timing constraint is dominated by rise delay (tpLH), sizing can be optimized specifically to meet the required rising-edge slack condition.
- In such cases, PMOS width can be increased selectively to reduce the low-to-high transition delay, ensuring that the data arrival time satisfies the setup timing requirement at the capture flop.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/f8618c21-fd48-409d-b604-6799f95d3b14" />

# Day4- CMOS Noise Margin robustness evaluation
## Static behaviour evaluation-CMOS inverter robustness-Noise Margin
### Lecture 1: Introduction to Noise Margin

- Glitches and crosstalk noise become increasingly critical in advanced technology nodes due to reduced supply voltages, tighter spacing, and higher interconnect coupling. These effects can be anticipated and quantified through noise margin analysis.
- **Noise Margin**: The maximum unwanted noise voltage that can be superimposed on a valid logic level without causing a logic error at the output.
- In an ideal inverter, input levels of 0 and 1 produce perfect 1 and 0 outputs, with an infinite transition slope at the switching point.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/214e40ad-efe4-407c-b804-4cd65390b5f3" /> <br/>

- In practical CMOS circuits, parasitic resistances and capacitances introduce finite transition time, resulting in a finite slope in the VTC around the switching region.
- Due to this finite gain in the transition region, the inverter becomes more sensitive to input noise near the switching threshold (Vm), where small voltage variations can cause significant output changes.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/3d46cb71-71ca-49eb-8cac-3c2f6e57713a" /> <br/>

| Voltage margin | Definations |
|-----|-----|
| VIL | - Input low voltage <br/> - Any input voltage between 0 and VIL will be treated as 0 |
| VOH | - Output high voltage <br/> - Any output voltage between VOH and VDD is treated as logic 1 |
| VIH | - Input high voltage <br/>  - Any input voltage between VIH and VDD will be treated as 1 |
| VOL | - Output low voltage <br/> - Any output voltage between 0 and VOL is treated as logic 0 |

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/9b878d0f-5c9c-4e61-90ea-dc75c6443639" />

### Lecture 2: Noise Margin voltage parameters

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/cd13339b-c60f-4ec6-b802-22ac5b1326da" /> <br/>

- Considering practical non-idealities of a CMOS inverter, the VTC is not perfectly vertical in the transition region, and valid logic levels occupy finite voltage ranges.
- When 0 < Vin < VIL → the inverter output is VOH ≤ Vout ≤ VDD (valid logic HIGH output)
- When VIH < Vin < VDD → the inverter output is 0 ≤ Vout ≤ VOL (valid logic LOW output)
- The regions between VIL and VIH correspond to the transition region, where both devices conduct, and the output is not considered a valid logic level.
- Voltage relationships must satisfy: ```VOL < VIL < VIH < VOH < VDD```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/582aa87b-d38e-4334-b5b2-134c49b40b80" /> <br/>

- The points where the slope of the VTC equals −1 (dVout/dVin = −1) define VIL and VIH. These boundaries mark the limits of the valid noise margin region.
- In the transition region, the magnitude of the slope (gain) is greater than 1, providing signal amplification and noise rejection. Outside this region, the slope magnitude is less than 1, ensuring stable logic levels.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/a74d71cb-605c-4093-b16f-e90cd484d993" /> <br/> 

### Lecture 3: Noise margin equation and summary
- NML (Noise Margin Low): Any voltage in this range is interpreted as logic low
- NMH (Noise Margin High): Any voltage in this range is interpreted as logic high
- Any input voltage falling outside the guaranteed LOW region (≤ VIL) or HIGH region (≥ VIH) lies in the transition region and is considered undefined.
- Only voltages within the NML or NMH limits are considered tolerable

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/a853ce40-62c3-4f7a-85fe-39366f8719ab" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/d362e0c0-ee28-4f7d-9bab-980d37e49dab" /> <br/>

- The small voltage bumps represent glitches, which may arise due to crosstalk, coupling capacitance, or switching activity in neighboring nets
 - Case 1: A small glitch occurs while the signal is logic 0, but the disturbed voltage remains within the NML range. The logic level is still correctly interpreted as LOW, and no functional error occurs
 - Case 2: The glitch pushes the voltage into the undefined region (between VIL and VIH). The inverter may respond unpredictably, potentially producing an erroneous output
 - Case 3: A large glitch shifts the voltage into the NMH region. Although the voltage now represents a valid HIGH level, it results in unintended logic switching and incorrect circuit behavior

### Lecture 4: Noise margin variation with respect to PMOS width
- Noise margin is evaluated by varying the PMOS width as an integral multiple of the NMOS width, and observing the impact on VTC characteristics. This analysis demonstrates the robustness of the CMOS inverter against noise under different strength ratios
- The critical points are obtained by identifying where the slope of the VTC equals −1 (dVout/dVin = −1). These points correspond to VIL and VIH
- From these slope = −1 points, projections are extended to the x-axis and y-axis to determine VIL, VIH, VOL, and VOH, enabling calculation of: ```NMH = VOH - VIH``` and ```NML = VIL - VOL```
- **Case 1:** Wp/Lp = Wn/Ln

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/6256973a-89d8-4643-9640-f0285712620f" /> <br/>

- A larger noise margin indicates a stronger and more noise-immune CMOS inverter, ensuring reliable logic interpretation even in the presence of glitches and coupling noise
- **Case 2:** Wp/Lp = 2(Wn/Ln)

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/ffa94347-71dc-42e9-a410-a578b72c5548" /> <br/>

- The PMOS transistor is responsible for charging and maintaining the output node at logic HIGH. Increasing the PMOS width reduces its effective ON resistance (R_ON), creating a stronger pull-up path from VDD to the load capacitance.
- A lower resistance path improves the ability of the output node to restore and sustain a solid HIGH level against leakage and noise disturbances.
- As a result, VOH remains closer to VDD, leading to an increase in NMH (Noise Margin High) and improved immunity to HIGH-level noise.
- **Case 3:** Wp/Lp = 3(Wn/Ln)

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/19c3ca25-35ac-4a45-80a6-ecb17433329e" /> <br/>

- The PMOS  is responsible for maintaining logic HIGH (1) at the output, while the NMOS device maintains logic 0. When only the PMOS width is increased, the pull-up network becomes stronger, improving the output HIGH level (VOH) and increasing NMH.
- Since the NMOS sizing remains unchanged, the pull-down strength and VOL remain nearly the same, therefore, NML does not significantly change. Hence, selectively increasing the PMOS width primarily enhances high-level noise immunity (NMH) without significantly affecting the low-level noise margin (NML).
- **Case 4:** Wp/Lp = 4(Wn/Ln)

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/a833dbfd-1c0b-4e59-9093-fcd58dbee15c" /> <br/>

- There are practical limitations to increasing the PMOS width; device sizing cannot be scaled arbitrarily due to area, capacitance, and power constraints.
- NMH does not increase indefinitely with continuous PMOS width scaling. Beyond a certain point, improvements saturate because VOH is already close to VDD, and further strength increase provides diminishing returns
- **Case 5:** Wp/Lp = 5(Wn/Ln)

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/c55af2b2-235c-4f0a-9a61-7457f897aa24" /> <br/>

- For Wp/Lp=4(Wn/Ln) and Wp/Lp=5(Wn/Ln), the extracted noise margins are nearly identical
- This indicates that beyond a certain PMOS sizing ratio, the noise margin saturates and becomes relatively insensitive to further width increase
- Therefore, increasing PMOS width beyond this point does not provide meaningful improvement in noise immunity and only adds area and parasitic capacitance overhead

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/cd596b4f-8358-4d6d-b7c4-e46a95e56378" /> <br/>

- Due to fabrication imperfections, actual transistor widths may slightly deviate from their intended design values. However, NMH, NML, and the switching threshold (Vm) do not exhibit drastic variation for moderate sizing deviations.
- This indicates that inverter functionality, noise immunity, and switching behavior remain stable despite process-induced dimensional variations.
- Therefore, CMOS inverters demonstrate strong robustness to practical fabrication tolerances

- **Digital Design:**
- Operates in the saturation regions (logic 0 or logic 1): The circuit is designed so the input stays in regions where the output is clearly HIGH (~VDD) or LOW (~0V).
- Avoids the unstable middle region
- Uses noise margins for reliability

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/640c9f3c-7381-44cd-b91a-da340985d2f0" /> <br/>

- **Analog Design:**
- Operates in the transition region (linear region): The design intentionally biases the inverter in the steep middle portion of the curve, where the slope is high.
- Small input voltage changes produce amplified output changes (voltage gain)
- Output is continuous, not just 0 or VDD
- The output can take any voltage along the curve

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/70659abe-a663-4e57-88ff-f4cdcd18b3ec" /> <br/>

### Lecture 5: Sky130 Noise margin labs
- Open the ```day4_inv_noisemargin__wp1__wn036.spice```

<img width="400" height="200" alt="image" src="https://github.com/user-attachments/assets/801a5eaf-88ee-4c77-8da3-9129693ffabe" /> <br/>

- ```(Wp/Lp)/(wn/Ln) = 2.78``` <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/6b9c16c7-8cb5-43f2-ae3c-efd9fb1de1c5" /> <br/>

- Run ngspice and ``` plot out vs in```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/12056ab4-a8dd-41a0-b310-c7f460cb636c" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/781bc842-6b10-4bde-b5d4-a24fb22f947f" /> <br/>

- We obtain VOH and VIL values from this part of the graph

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/3c04338b-e2b8-4d49-87d8-1cf5971d63dc" /> <br/>

<img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/741634e8-74aa-4496-87dd-8e87b710a4f2" /> <br/>

- VOH = 1.72464V
- VIL = 0.761818V

- We obtain VOl and VIH values from this part of the graph

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/99a44a5e-e2f1-44be-9133-550e5407eb29" /> <br/>

<img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/c428f95f-4cc8-4c1f-84bc-3239b332cdcb" /> <br/>

- VOL = 0.05217V
- VIH = 1.0363V

```
- NMH = VOH − VIH = 1.72464 - 1.0363 = 0.688V
- NML = VIL - VOL = 0.761818 - 0.05217 = 0.709V
```

# Day 5 - CMOS power supply and device variation robustness evaluation
## Static behavior evaluation – CMOS inverter robustness – Power supply variation
### Lecture 1: Smart SPICE simulation for power supply variations
- At advanced technology nodes, power supply scaling becomes a critical parameter in robustness evaluation, since VDD is reduced to control dynamic power and electric field stress.
- As VDD decreases, noise margins shrink, and the transition region becomes more sensitive to variations, making inverter stability more challenging.
- It is essential that the fundamental CMOS behavior — valid logic levels, switching threshold positioning, and gain characteristics — remains consistent even at lower supply voltages

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/81b7d163-6332-4d1b-a42f-6215274ed043" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/85dba913-126d-40a4-a366-24e5d8dfdf5c" /> <br/>

- This script performs a DC sweep of the CMOS inverter while progressively reducing the supply voltage (VDD).
- The initial supply voltage is set to 2.5 V, and inside the loop, VDD is reduced in steps of 0.5 V for five iterations.
- For each supply voltage value, a DC sweep of Vin from 0 to 2.5 V with a step size of 0.01 V is executed to extract the VTC.
- The ```alter Vdd``` command updates the supply value without redefining the entire circuit.
- Finally, multiple DC characteristics (dc1 to dc5) are plotted together to compare inverter behavior as a function of supply voltage, illustrating the impact of supply scaling on switching threshold and output swing.

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/0949b903-7a5e-4c2c-94e3-0098d94f535c" /> <br/>

### Lecture 2: Advantages and disadvantages of using low supply voltage
- The CMOS inverter is capable of operating even at lower supply voltages (e.g., 0.5 V), still producing a valid VTC, though with reduced voltage swing and transition sharpness.
- The first robustness metric to evaluate under supply scaling is the gain of the inverter
- As VDD decreases, the peak gain typically reduces, indicating weaker amplification and potentially reduced noise margins
- When ```Supply voltage = 2.5V```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/1981e960-e7c3-42ba-9531-f86bc0abae38" /> <br/>

<img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/a05c5ba7-e894-418b-b085-36969020d615" /> <br/>

- Gain = dVout/dVin = (2.35-0.1667)/(1.242-0.944) = 7.327

- Similarly, calculating the gain factor for all the values of supply voltage

| Supply voltage | Gain factor |
|-----|----|
| 2.5V | 7.327 |
| 2V | 9.27 |
| 1.5V | 15.96 |
| 1V | 14.89 |
| 0.5V | 12.63 |

- The Gain magnitude increases by 53% when the supply is reduced from 2.5 V to 0.5 V
- Energy, ```E= (1/2) CV^2```
 - For 0.5V, E = 0.125C J
 - For 2.5V, E = 3.125C J
- **Advantages of using lower supply voltage**
 1. Increase in gain (about 50%)
 2. Significant reduction in energy (about 90%)

<br/>

- **Disadvantages of using lower supply voltage**
 - When the supply voltage is reduced, the drive current of both NMOS and PMOS decreases.
 - Due to lower current, the charging and discharging of the load capacitor become slower. As a result, both rise delay (tₚLH) and fall delay (tₚHL) increase.
 - Increased propagation delay leads to reduced switching speed. This ultimately causes a performance degradation in the CMOS inverter.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/0831ef93-130e-4424-84cf-4fac2acd9856" />


### Lecture 3: Sky130 Supply Variation Labs
- Open ```day5_inv_supplyvariation.spice``` file

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/dd58c259-66b8-4dce-8b66-ac36cfca4a34" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/d8880204-ccd8-4ce4-b651-6ae7db0dee07" /> <br/>

- The initial supply voltage is set to 1.8 V
- Inside the loop, the supply voltage is reduced in steps of 0.2 V after each DC sweep
- The loop runs while voltagesupplyvariation < 6, resulting in 6 iterations
- Therefore, the inverter characteristics are evaluated at the following supply voltages: 1.8 V, 1.6 V, 1.4 V, 1.2 V, 1.0 V, and 0.8 V
- Each iteration performs a DC sweep of Vin, allowing comparison of the VTC curves as a function of decreasing supply voltage
- Run ```ngspice```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/559a2c6e-0dfa-489c-a739-8c8a6b206a79" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/c3b92765-8469-4ab5-a325-67d6fe0916d2" /> <br/>

- Evaluating gain

| Supply voltage | | Gain |
| ------| -----| -----|
| 1.8V | <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/40dbffef-ce11-4675-8fc3-01b3c468da81" /> | 5.95 |
| 1.6V | <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/e53e3087-d053-4c2a-899f-b9e32ad7ab65" /> | 7.74 |
| 1.4V | <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/515e3d1e-da31-43c2-9d50-fde6d53b5b4b" /> | 8.38 |
| 1.2V | <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/ec36864f-28e6-4da8-a620-0797745bb2de" /> | 9.06 |
| 1V | <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/36272d4b-42b5-42f8-9118-dd8aa3497528" /> | 9.15 |
| 0.8V | <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/0d5988fe-c982-40fd-acbb-a6f78d899ce2" /> | 9.43 |





