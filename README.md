# CMOS Circuit Design and SPICE Simulations

## VirtualBox Setup
This guide explains how to open the provided CMOS VDI file using Oracle VirtualBox.

### 1. Install VirtualBox

Download and install Oracle VirtualBox:

```https://www.virtualbox.org/wiki/Downloads```

### 2. Create Virtual Machine

1. Open **VirtualBox**
2. Click **New**
3. Set:

| Setting | Value |
|----------|--------|
| Type | Linux |
| Version | Ubuntu 18.04 Bionic Beaver (64-bit) |

Click **Next**

### 3. Allocate Memory

Assign RAM as required (Recommended: 4096 MB)

Click **Next**

### 4. Attach CMOS VDI File

1. Select **Use an existing virtual hard disk file**
2. Click the folder icon
3. Browse to the unzipped CMOS VDI file
4. Click **Open**
5. Click **Next**
6. Click **Finish**

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/810667cd-80c8-464e-b38d-54e2b0d478f9" />

### 5. Start the Virtual Machine

1. Select the created VM
2. Click **Start**

## Day 1: NgSpiceSky130 - Basics of NMOS Drain Current (Id) vs Drain to Source Voltage (Vds)

## Lecture 1: Introduction to Circuit Design and SPICE Simulations

### Why is SPICE Simulation needed?
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
