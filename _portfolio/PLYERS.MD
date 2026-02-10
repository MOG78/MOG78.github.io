---
title: "Multimaterial Plyers"
excerpt: "A DIY programmable syringe pump that is compatible with 10 mL and 20 mL syringes, reaching maximum flow rates for each syringe at 1.24 mL/s and 2.2 mL/s, respectively."
header:
  image: /assets/img/header_circuitsurfers.jpg
  teaser: /assets/img/RealImageSyringePump.jpg
gallery:
  - image_path: /assets/img/cad_rendering.png
  - image_path: /assets/img/interior_electronics.png
---


## Background

The goal of this FFF project was to design functional pliers capable of picking up a resistor. A key design constraint was that the pliers needed to be composed of two thermoplastic materials, one rigid plastic and one flexible plastic, in order to produce the characteristic mechanical “squeezing” motion of the pliers. For this specific project, the components were printed separately. However, there is a technique known as print-in-place, in which parts are printed as a single assembly without any post-processing or manual assembly (Thingiverse Blog, 2024, Print-in-Place: A Beginner’s Guide).

Thingiverse forums provide practical examples of print-in-place parts. These include components with folding mechanisms, such as a [parametric hinge] (https://www.thingiverse.com/thing:2187167) and a [folding wallet] (https://www.thingiverse.com/thing:123670). Other examples include parts with adjustable geometries, such as a [phone stand] (https://www.thingiverse.com/thing:3146835). Of course, there are also the fun print-in-place trinkets, such as bending snakes or pandas.

For single-material parts, a standard FFF printer can be used, such as the Voron 3D printers in the digital fabrication lab. However, printing in-place, multimaterial parts requires a different type of 3D printer, such as one with dual fixed extruders or a tool-changing system. For materials to adhere properly during a multimaterial print, their surface energies, chemical compositions, and mechanical properties must be similar . Due to the differences between the flexible plastic (TPU) and the rigid plastics used in this project (PLA and PET-G), material-locking connections were instead implemented, as discussed further in the design discussion (David Florian-L03-Dual Extrusion, 2026). 


<img src="/assets/img/electrical_wiring_diagram.jpg" alt="Electrical Wiring Diagram" style="width:400px;"/>

*Figure 1. Electrical Wiring Diagram*

## Design Criteria and 3D Printing 


### CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811642fa9b14f56ac7c?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

### Print Settings - Rigid Parts 

| Item                        | Quantity |
| :-------------------------: | :------: |
| M3 × 10 mm bolt             |       10 |
| M5 × 8 mm bolt              |        6 |
| M5 Tree Nut                 |        6 |
| TR8×8 Nut                   |        1 |
| Lock Collar – Lead Screw    |        2 |
| LM8UU Linear Bearing        |        1 |
| A4988 Stepper Driver        |        1 |
| Linear Rod – 8 mm × 200 mm  |        1 |
| Lead Screw – TR8×8 × 250 mm |        1 |
| Flexible Coupler            |        1 |
| Lock Collar – Linear Rod    |        2 |
| F688ZZ Flanged Ball Bearing |        1 |
| M10 Start Button            |        1 |
| 0.5" Forward / Back Button  |        2 |
| RGB Common Cathode LED      |        1 |
| NEMA-17 Motor               |        1 |
| 10 kΩ Potentiometer         |        1 |
| AC-DC Power Supply          |        1 |
| Arduino Uno                 |        1 |
| Limit Switch                |        1 |
| 2048 Aluminum Extrusion     |        1 |
| Breadboard                  |        1 |


### Print Settings - Flexible Spring

| Item                        | Quantity |
| :-------------------------: | :------: |
| Syringe Hub Support         |        1 |
| Syringe Barrel Support      |        1 |
| Motor Mounting Plate        |        1 |
| Extra Support               |        1 |
| Enclosure Front Panel       |        1 |
| Enclosure Left Panel        |        1 |
| Enclosure Right Panel       |        1 |
| Enclosure Lid               |        1 |



{% include gallery caption="Syringe Pump CAD Gallery" %}
