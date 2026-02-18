# CMOS Circuit Design and SPICE Simulations

## VirtualBox Setup
This guide explains how to open the provided CMOS VDI file using Oracle VirtualBox.

#### 1. Install VirtualBox
- Download and install Oracle VirtualBox: ```https://www.virtualbox.org/wiki/Downloads```
#### 2. Create Virtual Machine
1. Open **VirtualBox**
2. Click **New**
3. Set:

| Setting | Value |
|----------|--------|
| Type | Linux |
| Version | Ubuntu 18.04 Bionic Beaver (64-bit) |

- Click **Next**

#### 3. Allocate Memory
- Assign RAM as required (Recommended: 4096 MB)
- Click **Next**

#### 4. Attach CMOS VDI File
1. Select **Use an existing virtual hard disk file**
2. Click the folder icon
3. Browse to the unzipped CMOS VDI file
4. Click **Open**
5. Click **Next**
6. Click **Finish**

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/810667cd-80c8-464e-b38d-54e2b0d478f9" />

#### 5. Start the Virtual Machine

1. Select the created VM
2. Click **Start**

## Day 1: NgSpiceSky130 - Basics of NMOS Drain Current (Id) vs Drain to Source Voltage (Vds)

## Introduction to Circuit Design and SPICE Simulations

## Lecture 1: Why is SPICE Simulation needed?
- to verify circuit behavior
- optimize performance
- identify flaws before physical prototyping <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/73c5ea9b-62ea-4038-aa77-176a99e55680" /> <br/>

- The above is a CMOS inverter. It is the most basic logic gate in digital electronics. It performs the NOT operation <br/>
- Similarly, modifying the PDN and PUN networks involves various logic circuits that can be made <br/>
- On feeding various input values to the logic circuit, we obtain its IV characteristics graph as shown below <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/f0c3abb4-1ba3-4fac-8768-3c4e76df4ebb" /> <br/>

- By simulating and merging the PMOS and NMOS responses, the corresponding SPICE waveform is obtained <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/0d2227d6-7832-4d98-a2f9-ec890b895fca" /> <br/>
- The propagation delay extracted from this waveform can be used to optimize the Wn/Wp ratio, enabling further tuning of the delay model <br/>
- Suppose we perform Clock Tree Synthesis (CTS) on the circuit shown below, inserting buffers to drive different capacitive loads at the output <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/b289b3a4-f12c-45ea-a5e6-e85a157d9704" /> <br/>

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

## Lecture 3: Strong Inversion
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

<img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/5b1a280e-ea97-418f-a3b6-45f77d7d3289" /> <br/>

- Vto is the threshold voltage at Vsb=0
- γ is the body effect coefficient, which indicates how strongly the threshold voltage changes with body bias. It depends on substrate doping and oxide capacitance. <br/>

<img width="350" height="200" alt="image" src="https://github.com/user-attachments/assets/4db43a61-73dd-4b57-8220-14ae993c015c" /> <br/>

- φF is the Fermi potential of the substrate, representing the energy difference between the intrinsic level and the Fermi level in the semiconductor <br/>

<img width="350" height="200" alt="image" src="https://github.com/user-attachments/assets/2bf00eeb-9614-4f89-b392-854953ff3d0c" /> <br/>

- These values are obtained from the foundry and fed into the SPICE model for device modelling and simulation

## NMOS resistive region and saturation region of operation
## Lecture 1: Resistive region of operation with small drain-source voltage
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

## Lecture 2: Drift current theory
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

## Lecture 3: Drain current model for linear region of operation

<img width="700" height="800" alt="image" src="https://github.com/user-attachments/assets/f9f14a0b-88c8-42a1-9881-275c03df6fcb" /> <br/>

- Considering kn= unCox, where kn is the process transconductance, which determines how effectively the device converts gate voltage into drain current.

<img width="700" height="300" alt="image" src="https://github.com/user-attachments/assets/c4234c25-b9d5-43a8-a704-294359f89974" />  <br/>

- As the current equation is still quadratic, on further simplification, we obtain

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/0a8a4cc8-0986-4d8f-b109-9e3edfdf46e1" /> <br/>

- Therefore, for all values of VDS ≤ (VGS − Vt), the MOSFET operates in the resistive (linear) region.
- In this region, the channel is continuous from source to drain, and the device behaves like a voltage-controlled resistor.

## Lecture 4: SPICE conclusion to resistive operation
- To analyze the impact of VGS and VDS on the drain current (ID), we consider different values of both voltages.
- For a given VGS, the device remains in the linear (triode) region as long as: VDS < (VGS − Vt).
- To calculate ID for different values of VGS, we fix a particular VGS and then sweep VDS from 0 up to (VGS − Vt).
- In this region, ID follows the linear-region equation, and SPICE simulations can be used to obtain and verify the ID–VDS characteristics for each VGS.
<img width="700" height="200" alt="image" src="https://github.com/user-attachments/assets/c7f604bc-7e9f-48fb-a48b-a6753add9850" />

## Lecture 5: Pinch-off region condition
- When (VGS − VDS) > Vt, the effective gate voltage at the drain end is still greater than the threshold voltage. This means inversion is maintained even at the drain side
- Since inversion exists along the entire channel from source (x = 0) to drain (x = L), a continuous conducting path connects source and drain.
- In this condition, the device operates in the linear (triode) region, and the drain current increases approximately linearly with VDS for small values of VDS.

<img width="1000" height="700" alt="image" src="https://github.com/user-attachments/assets/642a659d-11ae-4277-af57-a5127d9f2616" /> <br/>

- When (VGS − VDS) = Vt, the effective gate-to-channel voltage at the drain end becomes exactly equal to the threshold voltage required for surface inversion.
- This means that at the drain end, the surface is just at the onset of inversion — the inversion charge density becomes zero at that point.
- Since the inversion layer disappears at the drain side, *the channel no longer extends fully to the drain*. This is called **pinch-off**.
- At pinch-off, the channel disappears only at the drain end, but the current does not stop flowing. Electrons reaching the pinch-off point are swept across the depletion region to the drain due to the strong electric field. As a result, the drain current no longer increases linearly with VDS

<img width="1000" height="700" alt="image" src="https://github.com/user-attachments/assets/9d34e16f-3108-4459-8380-50276c28848c" />  <br/>

- When VDS exceeds (VGS − Vt), the MOSFET enters the saturation region. At this point, the drain end no longer satisfies the inversion condition, and pinch-off occurs near the drain.
- Since the local channel potential reduces the effective gate voltage, the effective overdrive at any point along the channel is given by (VGS − V(x)). As V(x) increases from source to drain, the inversion charge decreases toward the drain end.
- As VDS increases further beyond (VGS − Vt), the pinch-off point moves slightly toward the source.

<img width="1000" height="700" alt="image" src="https://github.com/user-attachments/assets/e8735840-bd6f-49a4-8b28-d5d8795cdb3d" />

## Lecture 6: Drain current model for saturation region of operation
- When (VGS − VDS) ≤ Vt, the channel disappears at the drain side 
- In saturation, the channel voltage remains approximately constant at (VGS − Vt), unlike the linear region where it varies with V(x)
- The drain current ideally becomes independent of VDS and depends mainly on (VGS − Vt), assuming channel length modulation is neglected <br/>

``` Id = kn/2 (Vgs-Vt)^2``` <br/>

<img width="700" height="250" alt="image" src="https://github.com/user-attachments/assets/11105eee-d639-4614-84b0-1aa2d9e63cc7" />  <br/>

- In saturation, the MOSFET ideally behaves like a constant current source.
- However, the current is not completely independent of VDS. As VDS increases, the depletion region at the drain expands.
- This expansion reduces the effective conductive channel length. As the effective channel length decreases, the drain current increases slightly with VDS. This effect is known as **channel length modulation**

<img width="700" height="250" alt="image" src="https://github.com/user-attachments/assets/869dd17e-c959-4948-b493-f787e2c240a5" />

## Introduction to SPICE
## Lecture 1: Basic SPICE setup
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

## Lecture 2: Circuit description in SPICE syntax
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
### Netlist
```
M1 vdd n1 0 0 nmos W=1.8u L=1.2u  
R1 in n1 55  
Vdd vdd 0 2.5
Vin in 0 2.5
```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/45e92aa6-5916-4f53-8b8d-074c08e2d59b" />

## Lecture 3: Define technology parameters
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

## Lecture 4: First SPICE simulation
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

## Lecture 5: SPICE Lab with sky130 models
- Open ```sky130.lib.space``` file in ```models``` <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/df4bc6b1-3aca-4e97-bab3-13a50ea3aa2a" />  <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/1e7970c8-afcc-4997-9d6c-4506d7f8108d" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/d3e42812-3322-4704-be90-03b0dd776f69" /> <br/>

- The scale in which the parameter dimensions are defined can be obtained in the ```all.spice``` file <br/>

- Cut off region analysis
<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/9d8e8aa3-c0d8-48fb-a80a-458f474f1655" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/2dbf88d9-05a6-40a6-b4d0-d031f38b3cc6" /> <br/>

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/878710f0-e6b3-4631-bea5-a3521ae04228" /> <br/>

- A very small current can be observed for lower Vgs (Vgs=0.4V)
- For the device to be ON, Vgs>= Vt, the current is very minimal, as the transistor is in the cut-off region

## Day 2: Velocity saturation and basics of CMOS inverter VTC

## SPICE simulation for lower nodes and velocity saturation effect

## Lecture 1: WSPICE simulation for lower nodes

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

## Lecture 2: Drain current vs gate voltage for long and short channel devices

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6f0a039a-69ae-489d-bd00-7727217120ab" /> <br/>

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

## Lecture 3: Velocity saturation at lower and higher electric fields

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

## Lecture 4: Velocity saturation drain current model

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

## Lecture 5: Labs Sky130 Id-Vgs
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

## Lecture 6: Labs Sky130 Vt
- Open ```day2_nfet_idvgs_L015_W039.spice```
- Run ```ngspice```

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/9e8a6845-3c6e-4dad-b344-99154f0a187c" /> <br/>

- Plot Id current (vdd-branch)

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/1a0da406-0d8b-4a6b-9b02-62016fd36164" />  <br/>

- Threshold voltage (Vt) is obtained by drawing a tangent at the maximum slope of the Id–Vgs curve and extending it to intersect the Vgs axis
- Threshold voltage, ```Vt=0.737V```

## CMOS voltage transfer characteristics (VTC)
## Lecture 1: MOSFET as a switch
- When |Vgs| < |Vt| → No inversion channel is formed → Device is OFF (open switch).
- When |Vgs| > |Vt| → Inversion channel forms between source and drain.

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/33feb817-4f2c-4a8d-8e02-32ccaa1495f5" />  <br/>

- Infinite OFF resistance when |Vgs| < |Vt| → Device behaves as an open circuit.
- Finite ON resistance when |Vgs| > |Vt| → Device behaves as a closed switch

#### Complementary MOS Transistors
### Case 1: Vin = Vdd (Input High)

- When the input Vin is equal to Vdd, the PMOS transistor turns OFF because its gate-to-source voltage becomes zero. At the same time, the NMOS transistor turns ON since its gate-to-source voltage equals Vdd and exceeds the threshold voltage.
- In this condition, the PMOS behaves like an open switch and the NMOS behaves like a closed switch. As a result, the output node is connected to Vss through the NMOS, and the load capacitor discharges.
- Therefore, the output voltage Vout becomes logic LOW.

### Case 2: Vin = 0 (Input Low)

- When the input Vin is equal to 0 V, the NMOS transistor turns OFF because its gate-to-source voltage is zero. Meanwhile, the PMOS transistor turns ON since its gate-to-source voltage equals Vdd in magnitude and exceeds the threshold voltage. 
- In this case, the NMOS behaves like an open switch and the PMOS behaves like a closed switch. Consequently, the output node is connected to Vdd through the PMOS, and the load capacitor charges.
- Therefore, the output voltage Vout becomes logic HIGH.


<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/8bfbcb84-1d6a-4cbd-b2b6-41e20faa4cb2" />

## Lecture 2: Introduction to standard MOS voltage current parameters
