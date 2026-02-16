# CMOS-Circuit-Design-and-SPICE-Simulations

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
| Version | Ubuntu 18.04 (64-bit) |

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

### Why is SPICE Simulation needed?
- to verify circuit behavior
- optimize performance
- identify flaws before physical prototyping
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/73c5ea9b-62ea-4038-aa77-176a99e55680" /> <br/>

- The above is a CMOS inverter. It is the most basic logic gate in digital electronics. It performs the NOT operation <br/>
- Similarly, modifying the PDN and PUN networks involves various logic circuits that can be made <br/>
- On feeding various input values to the logic circuit, we obtain its IV characteristics graph as shown below <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/f0c3abb4-1ba3-4fac-8768-3c4e76df4ebb" /> <br/>

- By simulating and merging the PMOS and NMOS responses, the corresponding SPICE waveform is obtained <br/>

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/0d2227d6-7832-4d98-a2f9-ec890b895fca" />
- The propagation delay extracted from this waveform can be used to optimize the Wn/Wp ratio, enabling further tuning of the delay model.
- Suppose we perform Clock Tree Synthesis (CTS) on the circuit shown below, inserting buffers to drive different capacitive loads at the output.
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/b289b3a4-f12c-45ea-a5e6-e85a157d9704" />
- From these spice simulations, we obtain a delay table that includes the input slew and output load.
<img width="2141" height="518" alt="image" src="https://github.com/user-attachments/assets/fdcd03b7-3d62-43ea-94e5-b42515b9f25e" />
- Select the row corresponding to the input slew and the column corresponding to the output load; their intersection gives the cell delay value.
- If the exact slew or load is not listed, use interpolation between adjacent values to estimate the delay.
- Each delay table corresponds to a different Wn/Wp ratio, so variations between tables reflect the impact of transistor sizing on propagation delay.
