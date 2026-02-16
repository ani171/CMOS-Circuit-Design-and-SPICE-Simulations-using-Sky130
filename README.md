# CMOS Circuit Design and SPICE Simulations

## VirtualBox Setup
This guide explains how to open the provided CMOS VDI file using Oracle VirtualBox.

#### 1. Install VirtualBox

Download and install Oracle VirtualBox:

```https://www.virtualbox.org/wiki/Downloads```

#### 2. Create Virtual Machine

1. Open **VirtualBox**
2. Click **New**
3. Set:

| Setting | Value |
|----------|--------|
| Type | Linux |
| Version | Ubuntu 18.04 Bionic Beaver (64-bit) |

Click **Next**

#### 3. Allocate Memory

Assign RAM as required (Recommended: 4096 MB)

Click **Next**

#### 4. Attach CMOS VDI File

1. Select **Use an existing virtual hard disk file**
2. Click the folder icon
3. Browse to the unzipped CMOS VDI file
4. Click **Open**
5. Click **Next**
6. Click **Finish**

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/810667cd-80c8-464e-b38d-54e2b0d478f9" />

#### 5. Start the Virtual Machine

1. Select the created VM
2. Click **Start**

## Day 1: NgSpiceSky130 - Basics of NMOS Drain Current (Id) vs Drain to Source Voltage (Vds)

## Introduction to Circuit Design and SPICE Simulations

## Lecture 1: Why is SPICE Simulation needed?
- to verify circuit behavior
- optimize performance
- identify flaws before physical prototyping <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/73c5ea9b-62ea-4038-aa77-176a99e55680" /> <br/>

- The above is a CMOS inverter. It is the most basic logic gate in digital electronics. It performs the NOT operation <br/>
- Similarly, modifying the PDN and PUN networks involves various logic circuits that can be made <br/>
- On feeding various input values to the logic circuit, we obtain its IV characteristics graph as shown below <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/f0c3abb4-1ba3-4fac-8768-3c4e76df4ebb" /> <br/>

- By simulating and merging the PMOS and NMOS responses, the corresponding SPICE waveform is obtained <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/0d2227d6-7832-4d98-a2f9-ec890b895fca" /> <br/>
- The propagation delay extracted from this waveform can be used to optimize the Wn/Wp ratio, enabling further tuning of the delay model <br/>
- Suppose we perform Clock Tree Synthesis (CTS) on the circuit shown below, inserting buffers to drive different capacitive loads at the output <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/b289b3a4-f12c-45ea-a5e6-e85a157d9704" /> <br/>

- From these spice simulations, we obtain a delay table that includes the input slew and output load <br/>
<img width="2141" height="518" alt="image" src="https://github.com/user-attachments/assets/fdcd03b7-3d62-43ea-94e5-b42515b9f25e" /> <br/>

- Select the row corresponding to the input slew and the column corresponding to the output load; their intersection gives the cell delay value <br/>
- If the exact slew or load is not listed, use interpolation between adjacent values to estimate the delay <br/>
- Each delay table corresponds to a different Wn/Wp ratio, so variations between tables reflect the impact of transistor sizing on propagation delay <br/>
- SPICE simulations basically involve characterizing the NMOS and PMOS in detail, thus optimizing the delay model <br/>

## Lecture 2: Introduction to basic elements in Circuit Design - NMOS
### N-channel Metal Oxide Semiconductor 
- 4-terminal device <br/>

| Component | Description | Key Notes |
|------------|-------------|-----------|
| P-type Substrate | Base semiconductor material on which the NMOS is built | • Forms the body of the device <br> • Provides majority holes as carriers |
| Isolation Regions | Regions separating adjacent devices | • Electrically isolate neighboring transistors <br> • Prevent leakage and latch-up |
| N+ Diffusion (Source & Drain) | Heavily doped n-type regions in the substrate | • Act as source and drain terminals <br> • Provide electron injection and collection |
| Gate Oxide | Thin insulating oxide layer above substrate | • Typically SiO₂ <br> • Controls channel formation <br> • Critical for threshold voltage |
| Polysilicon / Metal Gate | Conductive layer above gate oxide | • Forms the Gate (G) terminal <br> • Controls channel via electric field <br> • Drives device switching |
| Body Terminal | Substrate connection terminal | • Usually connected to ground in NMOS <br> • Affects threshold voltage (body effect) <br> • Important for device modeling |

<br/>
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/1b31d1fd-671c-41de-93c7-3695d559501c" /> <br/>

#### Threshold voltage (Vt)
- Threshold voltage is the minimum gate-to-source voltage required to form an inversion layer (conducting channel) between source and drain, allowing the MOSFET to turn ON <br/>

**Threshold Voltage Modelling** <br/>

- Let Vgs=0
- Connect Drain, Source, and Body to GND
- Now, Body-Source and Body-Drain form a pn junction diode 
- As both junctions are OFF, high resistance is observed, thus no conductivity between Source and Drain <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/c067006d-8848-42e2-b6ed-c1aeeb2d0b77" /> <br/>

- When a small positive voltage is applied to the gate, an electric field is established across the gate oxide.
- The gate oxide acts as a capacitor, causing positive charges (holes) in the p-type substrate to be repelled deeper into the substrate, leaving behind immobile negative ions near the surface.
- As these negative charges accumulate, a depletion region forms beneath the gate. <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/777eb3ae-af5b-4f28-80c0-4bf5a2f5590c" />  <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/f15ecc07-48e5-4894-acc3-e2461cd3baec" /> <br/>

## Lecture 3: Strong Inversion
- Increasing the gate voltage Vgs, the electric field across the oxide strengthens.
- More holes are pushed away from the surface, expanding the depletion region.
- When Vgs increases further, electrons accumulate at the surface and form an n-type inversion layer. This is called **strong inversion** or **surface inversion**
- The voltage at which strong inversion occurs is known as the threshold voltage  <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/20255246-23fa-4ea4-b7c7-32ae55eaa35f" />  <br/>

- With further increase in VGS beyond strong inversion, additional gate voltage attracts more electrons to the surface, increasing the inversion charge density.
- The channel becomes stronger (effectively wider), forming a conductive path between source and drain.
- However, since VDS = 0, there is no electric field to drive electrons from source to drain, so no current flows. Hence, the device remains in the **cutoff region**

#### Role of the Body terminal

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/2bb59ef7-693e-4cb3-9fa4-ddde41906f98" /> <br/>

- Applying a positive voltage to the substrate, an additional reverse bias is observed, as the source is now more negatively charged and the substrate is positively charged.
- This increases the depletion layer width more near the source <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/88327cd7-25cb-4ab5-baca-e9ba650f9cf2" /> <br/>

## Lecture 4: Threshold voltage with positive substrate potential
- As VGS increases, the electric field across the oxide increases, and the depletion region beneath the gate expands in both cases (VSB = 0 and VSB > 0).
- When VSB is positive, the source–body junction becomes more reverse-biased. This increases the electric field between the source and the p-substrate, pulling more holes (positive charges) away from the surface and deeper into the substrate.
- Because more holes are removed from the surface, the depletion region becomes wider compared to the VSB = 0 case. This means a larger amount of negative fixed charge (ionized acceptor ions) is left behind near the surface.
- To achieve inversion, the gate must now supply enough electric field to first balance this larger depletion charge before attracting electrons to form the inversion layer.
- As a result, surface inversion occurs at a higher gate voltage. Therefore, a higher VGS is required to turn the device ON when VSB > 0. This increase in threshold voltage due to body bias is called the **body effect** <br/>

<img width="2128" height="841" alt="image" src="https://github.com/user-attachments/assets/872e75b9-8305-4098-8a05-e183cc739a0f" /> <br/>

- Let VGS = VTO be the gate voltage at which the semiconductor surface reaches inversion when VSB = 0.
- In the second case, when VSB > 0, an additional voltage (say V1) is required to overcome the increased depletion charge.
- Therefore, the new gate voltage required for inversion becomes: **VGS = VTO + V1** 

<img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/5b1a280e-ea97-418f-a3b6-45f77d7d3289" /> <br/>

- Vto is the threshold voltage at Vsb=0
- γ is the body effect coefficient, which indicates how strongly the threshold voltage changes with body bias. It depends on substrate doping and oxide capacitance. <br/>

<img width="250" height="100" alt="image" src="https://github.com/user-attachments/assets/4db43a61-73dd-4b57-8220-14ae993c015c" /> <br/>

- φF is the Fermi potential of the substrate, representing the energy difference between the intrinsic level and the Fermi level in the semiconductor <br/>

<img width="939" height="220" alt="image" src="https://github.com/user-attachments/assets/2bf00eeb-9614-4f89-b392-854953ff3d0c" /> <br/>

- These values are obtained from the foundry and fed into the SPICE model for device modelling and simulation

## NMOS resistive region and saturation region of operation
## Lecture 1: Resistive region of operation with small drain-source voltage
- On increasing VGS > Vt, the channel charge density increases
- In the channel, the induced charge Qi is directly proportional to (Vgs - Vt). This excess voltage, known as the overdrive voltage, creates additional mobile electrons in the channel, increasing the drain current.  <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/76f212fd-8e55-481c-a80f-9126a104c716" />  <br/>

- Let Vt (NMOS) = 0.45 V, VGS = 1 V and VDS = 0.05 V.
- Since VGS > Vt, the transistor is ON and a conducting inversion channel is formed between source and drain.
- Because the source is grounded and the drain is at a positive voltage, a voltage gradient develops along the channel from source to drain.
- If we plot a graph with the x-axis as the channel length (from 0 to L, considering L ≈ Leff) and the y-axis representing channel charge/strength:
    - In the absence of VDS, every point along the channel sees the same gate overdrive voltage (VGS − Vt).
    - When VDS is applied, the local channel potential becomes V(x), which varies from 0 at the source to VDS at the drain.
    - Therefore, the effective overdrive at any point x becomes (VGS − V(x) − Vt), meaning the channel charge gradually decreases from source to drain. <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6298ab08-fca4-4868-a012-9b56a973c8f4" />  <br/>

| Parameter | Defination |
|------------|------------|
| Channel Length (L) | The physical distance between the source and drain defined during fabrication (layout dimension). |
| Effective Channel Length (Leff) | The actual conductive channel length after accounting for lateral diffusion and short-channel effects |

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/7728045d-565e-4360-a89f-7d23a46edf07" />

## Lecture 2: Drift current theory
- In the channel (yellow region below), the induced inversion charge at any point x depends on the local gate overdrive voltage.
- Since the channel potential varies along its length, the effective gate voltage at position x is VGS − V(x).
- Therefore, the inversion charge per unit area at point x is proportional to the local overdrive voltage  <br/>

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/3e7df49a-3515-41b9-93ef-596a45fcfb20" />  <br/>

- Where Cox is the gate oxide capacitance per unit area. It represents the capacitance formed between the gate and the channel through the thin oxide layer <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/0d5a8931-ccce-441f-9a23-f5b1a64e3bc1" /> <br/>

- There are two types of current
1. Drift current - Current that flows due to an applied electric field (potential difference), which causes charge carriers to move in a specific direction.
2. Diffusion current - Current that flows due to a concentration gradient, where charge carriers move from a region of higher concentration to a region of lower concentration <br/>
        
```Drift current (Id) = Velocity of charge carriers x Available charge (over the channel width)```

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/8ca8f8bd-3c14-4416-b3bb-4a74467fa8a2" />

## Lecture 3: Drain current model for linear region of operation

<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/f9f14a0b-88c8-42a1-9881-275c03df6fcb" /> <br/>

- Considering kn= unCox, where kn is the process transconductance, which determines how effectively the device converts gate voltage into drain current.

<img width="800" height="300" alt="image" src="https://github.com/user-attachments/assets/c4234c25-b9d5-43a8-a704-294359f89974" />  <br/>

- As the current equation is still quadratic, on further simplification, we obtain

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/0a8a4cc8-0986-4d8f-b109-9e3edfdf46e1" /> <br/>

- Therefore, for all values of VDS ≤ (VGS − Vt), the MOSFET operates in the resistive (linear) region.
- In this region, the channel is continuous from source to drain, and the device behaves like a voltage-controlled resistor.



