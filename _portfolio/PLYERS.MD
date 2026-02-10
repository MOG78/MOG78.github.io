---
title: "Additive Manufacturing Project 1: Multimaterial Pliers"
excerpt: "Functional pliers capable of picking up a resistor."
header:
  image: /assets/img/horizontal_header.jpg
  teaser: /assets/img/final.jpg
gallery:
  - image_path: /assets/img/1.jpg
  - image_path: /assets/img/2.png
  - image_path: /assets/img/springs.jpg
  - image_path: /assets/img/final.jpg
---


## Background

The goal of this FFF project was to design functional pliers capable of picking up a resistor. A key design constraint was that the pliers needed to be composed of two thermoplastic materials, one rigid plastic and one flexible plastic, in order to produce the characteristic mechanical “squeezing” motion of the pliers. For this specific project, the components were printed separately. However, there is a technique known as **print-in-place**, in which parts are printed as a single assembly without any post-processing or manual assembly (Thingiverse Blog, 2024, Print-in-Place: A Beginner’s Guide).

Thingiverse forums provide practical examples of print-in-place parts. These include components with folding mechanisms, such as a [parametric hinge] (https://www.thingiverse.com/thing:2187167) and a [folding wallet] (https://www.thingiverse.com/thing:123670). Print-in-place fabrication can be useful in manufacturing to reduce a step of assembly. 


<img src="/assets/img/parametric_hinge.jpg" alt="print-in" style="width:400px;"/>

*Figure 1. 3D printed print-in-place functional hinge, with modifiable geometry*


Other examples include parts with adjustable geometries, such as a [phone stand] (https://www.thingiverse.com/thing:3146835). There are also the fun print-in-place trinkets, such as articulated animal figurines. 

<img src="/assets/img/shark.jpg.jpg" alt="print-in" style="width:400px;"/>

*Figure 2. 3D printed print-in-place fun/shark*


For single-material parts, a standard FFF printer can be used, such as the Voron 3D printers in the digital fabrication lab. However, printing in-place, multimaterial parts requires a different type of 3D printer, such as one with dual fixed extruders or a tool-changing system. In order for materials to adhere properly during a multimaterial print, their surface energies, chemical compositions, and mechanical properties must be similar. Due to the differences between the flexible plastic (TPU) and the rigid plastics used in this project (PLA and PET-G), material-locking connections were instead implemented, as discussed further in the design discussion (David Florian-L03-Dual Extrusion, 2026). 


## Design Criteria and 3D Printing 
### CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811a758652141036e8a?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

A further goal (personal design choice) was to design pliers that were as small as possible, mimicking tweezers, with the thinking that this could maximize the number of resistors picked up. There were several categories through which the design was iterated.

#### Top-Down Modeling 
New to this project was top-down-level modeling, in which the parts were designed within the same document, and the projected geometry of the spring defined the interlocking components of the handles and jaws. The joints were created “as-built” to fix the entire assembly. As a first attempt at top-down-level modeling, there were definite areas for improvement. For instance, while the plier jaws were designed so that one body was the “mirror” of the other, each jaw remained attached when moved. This prevented the use of the revolute joint in opposite directions, which would have accurately captured the true motion of the pliers.

#### Angles
There were two angles in the geometry of the pliers that were important to define: the angle between the jaws that creates the compressive force, and the angle of the jaw surface relative to the vertical plane that slices the pliers, which comes together to make contact with the resistor. After one iteration, the angle of the handles needed to be expanded to allow for more squeezing (see first image in gallery). The final angle used between both handles was 57 degrees (Figure 3). Before the second jaw component was mirrored, a revolute joint was created between the jaw and the spring (Figure 3). Through rotating the jaw manually, the angle that would likely result in even, flush contact was chosen to be 7 degrees.
The final breakdown of the specifications of the jaws are as follows:

- Jaw Total Length: 29.8 mm
- Jaw Contact Length: 7 mm
- Jaw Capacity: small, <5 mm parts

<img src="/assets/img/plyer_ss_labels.jpg" alt="Labeled CAD Model" style="width:400px;"/>

*Figure 3. Design Choices - Labeled CAD Model*

#### Fastener and Offset 
To ensure that the components could be assembled without losing connection, T-fasteners were used throughout the design iterations. One key parameter that was iterated on was the offset. The first iteration (gallery image 1) was printed using PLA. I learned that another feature that makes PLA a solid rapid prototyping material is that over-extrusion is less problematic, so my first iteration, with a 0.15 mm offset between the rigid components and the spring, was successful.
However, for the remaining iterations, PET-G was used. This same offset resulted in components that did not fit together (gallery image 2). After discussing this issue with Dr. Florian, and considering both the tendency of PET-G toward over-extrusion and the fact that my fasteners (on the 1-2 mm scale) push the accuracy limits of a 0.6 mm nozzle, a 0.4 mm nozzle was used for the final iteration. This configuration worked well (gallery image 4 and header).

#### TPU Spring Composition 
Multiple tests were also printed in a single print iteration of the TPU 95A spring, with varying infill densities and patterns (gallery image 3). Ultimately, a grid infill pattern with 18% infill was chosen. **The final breakdown of print settings were as follows:**


##### TPU 95A 
Default Voron 3D printer settings for TPU 95A, with the following changes: 

| Setting | Rationale |
|--------|-----------|
| Print Nozzle: 0.6 mm | TPU, and flexible plastics in general, cannot be printed with a 0.4 mm nozzle. |
| Infill Pattern: Grid | The grid orientation is perpendicular to the applied force, allowing bending of the spring. |
| Infill Density: 18% | Through multiple iterations, 18% provided the best flexibility and strength. |
| Top and Bottom Layers: 0 | Adding top and bottom layers increased stiffness that were not ideal for the flexibility for the spring. |
| Infill Extrusion Width: 1.2 mm | The increased extrusion width strengthened the grid lines, especially for the small spring geometry, this improved structural strength. |


##### PET-G  
Default Voron 3D printer settings for PET-G, with the following changes:

| Setting | Rationale |
|--------|-----------|
| Print Nozzle: 0.4 mm | Enabled finer geometries required for the interlocking features. |
| Infill Density: 31% | Provided strength for rigid components while maintaining fast iteration times. |
| Extrusion Factor: 95% | Reduced over-extrusion of PET-G. |

### 
The pliers were ultimately functional and easy to manipulate, as displayed in below: 
<img src="pliers_gif.gif" alt="Plier squeezing gif" style="width:600px;"/>

{% include gallery caption="The printed iterations of the pliers" %}
