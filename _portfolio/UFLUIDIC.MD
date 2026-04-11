---
title: "Additive Manufacturing Project 2: Resin Printing of Microfluidic Molds "
excerpt: "A pinch flow fractionation device."
header:
  image: /assets/img/Header.png
  teaser: /assets/img/IMG_9340.jpg
gallery:
  - image_path: /assets/img/1.jpg
  - image_path: /assets/img/2.jpg
---


## Background

A microfluidic device is a device that manipulates small volumes of liquids on the micrometer to nanometer scale through the use of networks of channels [Source: Microfluidic Devices and Their Applications](https://link.springer.com/chapter/10.1007/978-3-662-54357-3_16). In biomedical engineering applications, microfluidic devices can be used for organ-on-a-chip systems, which simulate specific physiological conditions, or lab-on-a-chip systems that miniaturize laboratory processes.  One very interesting application is the use of a silicon spiral microfluidic chip for isolating circulating tumor cells from a patient’s blood sample by separating cells based on their size. Researchers and clinicians can analyze these cells to better understand tumor progression and metastasis without needing an invasive tumor biopsy [Source: Isolation of Circulating Tumor Cells from Peripheral Blood Samples](https://pmc.ncbi.nlm.nih.gov/articles/PMC8596232/).

#### Pinched Flow Fractionation 
In addition to spiral microfluidic designs, several other separation techniques have been explored, including pinched flow fractionation (PFF). PFF describes a specific channel design in which one inlet introduces particle-free fluid and the other inlet contains particles. The particles then enter a pinched segment where the flow is confined, and the resulting force cause particles to align according to size as they enter a broadened section. The dominant mechanism responsible for separation is the laminar flow and streamline displacement due to channel geometry rather than a external force [Source: A comprehensive review of pinch flow fractionation in microfluidics](https://link.springer.com/chapter/10.1007/978-3-662-54357-3_16).

<img src="/assets/img/Schematic-of-working-mechanism-of-pinched-flow-fractionation.png.jpg" alt="print-in place hinge" style="width:400px;"/>

*Figure 1. Schematic of particle trajectory in PFF*

Pinched flow fractionation is more efficient than filters because, when functioning properly, it does not rely on the physical blocking of sized particles compared to conventional filtering techniques, such as pores and meshes that can easily clog. Additionally, in centrifugal separation, high rotational velocities can cause shear-induced damage to fragile particles [Source: What Are The Disadvantages Of Centrifugal Filtration?] (Source: https://kindle-tech.com/faqs/what-are-the-disadvantages-of-centrifugal-filtration). Pinched flow fractionation efficiency specifically relies on the width aspect ratio of the pinched section and broadened section, as well as a steep boundary angle at the transition region.

## Design Criteria and Overview 

### 
A symmetric pinch flow fractionation approach was chosen. The first design consideration was the particle size. The sizes that need to be sorted are in the range of:
- 125–150 μm
- 425–500 μm

The pinched flow section should be as small as possible (at least the size of the largest particle), while the broad section should be as large as possible. The final design specifications were chosen as follows:

| Section       | Dimension |
| ------------- | --------- |
| Pinch section | 650 μm    |
| Broad section | 55 mm     |

#### Particle Path Calculation 
Each particle path was calculated according to the formula, where *Wp* is the width of the pinched section, *Wb* is the width of the broad section, and r is the radius of the particles: 
Y0 = (wp - D/2 + r) / (wb / wp)

Each outlet was selected based on the midpoint of the particle trajectories, as seen in Figure 2A. The final calculated values are drawn on a schematic for clearer representation in Figure 2B. 

<img src="/assets/img/Fusion_Sketch_With_Calcs.png" alt="print-in place hinge" style="width:400px;"/>

*Figure 2A. Full Sketch - Fusion 360*

<img src="/assets/img/labled-particle-paths.png" alt="print-in place hinge" style="width:400px;"/>

*Figure 2B. Schematic of Particle Path Trajectories*

### Design Consideration: On-Chip Flow Resistance Design for Outlet Balancing
Flow imbalance in PFF occurs because each outlet  experiences different hydraulic resistance, causing fluid to redistribute away from the intended streamline separation. This is especially problematic for the buffer region, which carries the majority of flow, since unequal resistance or outlet sizing can force fluid into incorrect outlets.  To solve this, I increased resistance in the small and large particle outlet channels by extending their length and narrowing their geometry, while keeping the buffer outlet comparatively low-resistance so it naturally draws the highest fraction of flow.
The resistance to flow for each channel is given by R, where conductance is 1/R. Since the height and width of every channel is constant, resistance is calculated based on trapezoidal entrance geometry and channel perimeter.
- R_rectangle = L / w
- R_trapezoid = L / w_avg,   where w_avg = (w1 + w2) / 2

#### Outlet Resistace and COnductance Calculations: 

| Outlet        | Trapezoid R | Loop/Tail R | Total Resistance (R) |
| ------------- | ----------- | ----------- | -------------------- |
| Small Channel | 0.896       | 71.11       | 72.01                |
| Large Channel | 0.328       | 13.13       | 13.46                |
| Buffer Waste  | 0.515       | 5.59        | 6.11                 |

Total Conductance = (1/72.01)+(1/13.46)+(1/6.11)=0.0139+0.0743+0.1637=0.2519
###### Flow Percentages: 
- Small Flow: 5.5%
- Large Flow: 29.5%
- Buffer Flow: 65.0%

### While the conductance-based calculations of flow distribution were used for iteration of the initial model design, the actual flow rates were determined based on the relative channel widths at the outlets. With a total flow rate of 2.5 mL/min, the flow was distributed proportionally as follows:
- small = (5.878/35) × 2.5 = 0.42 mL/min 
- large = (8.016/35) × 2.5 = 0.57 mL/min 
- buffer = (21.106/35) × 2.5 = 1.51 mL/min.

### CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b60281158608a7e259fdf83?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>


## Fabrication Steps 
#### SLA Printing of Mold 
SLA printing was performed with a 0.050 mm layer thickness, and the mold’s bottom surface was oriented to be perfectly flat and parallel to the resin vat to avoid layer artifacts, with cupping warnings ignored when present. After printing, the device was washed for 5 minutes on the build platform in the larger FormWash and an additional 5 minutes in the smaller unit, without exceeding 15 minutes total to prevent IPA absorption, then dried upside down for 30 minutes to avoid resin pooling while ensuring a uniform matte interior finish indicating complete resin removal. Internal surfaces were not touched or wiped to preserve channel smoothness, and any debris was gently removed using compressed air with appropriate safety precautions. The part was then subjected to a 60-second room-temperature surface cure with supports attached to minimize warping before careful support removal, and the device was cleaned promptly. 

#### Injection Modling of Part
Resin-printed molds are treated becausepartially reactive species from the SLA resin inhibit PDMS curing. The following steps are performed to create the final mold. 
- Mold surface treatment
- Sylgard 184 PDMS is prepared at a 10:1 base-to-curing-agent ratio and thoroughly mixed.
- The mixture is degassed to remove trapped air bubbles.
- PDMS is poured into the mold 
- Thermal curing is performed 
- Cured PDMS is carefully demolded 
- Oxygen plasma treatment is applied to activate surfaces for bonding (Figure 4). 
- The mold is bonded to the glass slide, followed by a bake for 15 - 30 minutes. 

<img src="/assets/img/Plasma-Treating-Image (3).jpg" alt="plasma treatment" style="width:400px;"/>

*Figure 4. Plasma Treatment*

#### Final Casting 

<img src="/assets/img/IMG_9340" alt="final casting" style="width:400px;"/>

*Figure 5. Final Casting of Microfluidic Used for Testing*

## Testing 
The testing station operated at a total volumetric flow rate of 2.5 mL/min across the channels, with inlet channels set to 0.25 mL/min. The particle-containing inlet was held vertically to improve mixing and prevent bead settling, and beads were suspended in a 3% Tween solution to reduce aggregation and promote uniform dispersion. The full setup also included a camera for particle tracking, as shown in Figure 6.

<img src="/assets/img/IMG_9357" alt="testing setup" style="width:400px;"/>

*Figure 6. Testing Setup

### The Present Device

<img src="/assets/img/Video Project 3.mp4" alt="Mona's Microfluidic" style="width:600px;"/>

### Novel Solution from Other Classmate

<img src="/assets/img/Kathleen_Video (1).mp4" alt="Kathleen's Microfluidic" style="width:600px;"/>

### 
## Anaylsis and Discussion 


{% include gallery caption="Gallery of Microfluidic Project" %}
