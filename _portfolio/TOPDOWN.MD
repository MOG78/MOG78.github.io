---
title: "Additive Manufacturing Project 4: Top-Down Level Modeling"
excerpt: "Functional phone mount for bike handle bar."
---


### Late submission to test with pSLS, but please see design description:

## Introduction: Top-Down Modeling
I used top-down modeling in this design. Top-down modeling describes a Hybrid Design approach in Fusion where a design can be constructed based on projections and existing geometry. This was the second time I used this approach, as I had also used it previously in the Plyer Project. Autodesk more formally defines top-down modeling as a workflow where geometry and relationships are created from higher-level references so that components remain linked to one another throughout the design process. This approach has several advantages, including rapid iteration and prototyping, improved consistency of design, and saved resources due to reduced errors. By projecting geometry and maintaining constraints between components, designers can verify spacing and relationships throughout the modeling process [Source: Autodesk](https://www.autodesk.com/solutions/top-down-modeling?msockid=1185b33029d26c24395da59128176da6).

Overall, I found that this approach worked well for creating the overall phone geometry and clamp components. However, during the design process I made a significant mistake. At one point I hid the handlebar component in order to clear the design space while working on the clamp geometry. While this made the modeling environment easier to see temporarily, it ultimately caused a fundamental flaw in the design process: Because the handlebar reference was hidden, the orientation of the phone clamp was unintentionally reversed. This mistake highlights one of the most important lessons from this assignment: in a top-down modeling workflow, all geometry should remain visible and connected.

The final model was submitted for printing in this reversed configuration. As a result, the tested model can only be clamped at the end of the handlebar rather than along its length. In addition, the phone mount is not visible to the bike user in the intended orientation. After completing the final assembly and recognizing this issue, I redesigned the clamp to correct the orientation. 

This experience reinforced the importance of properly maintaining references and creating joints throughout the design process. 

## Design
### The CAD Model Used for Fabrication 
#### Bar Clamp

When designing this phone mount, I wanted the model to require as little assembly as possible. My goal was to create a design where the detent mechanism and clamp were integrated together.

I designed the clamp mechanism to function similarly to a hose clamp. The user can squeeze the clamp arms together and latch the teeth to secure the mount around the handlebar. This approach allows the mount to attach securely while avoiding the need for additional hardware. One of the biggest considerations in the design was determining the correct clamp width. Ideally, I would iterate through multiple clamp widths to determine the optimal point where the clamp could be squeezed easily while still maintaining sufficient holding force on the handlebar. Finding this balance is important because the clamp needs to be flexible enough to install, but rigid enough to prevent movement during use.

#### Phone Holder

The phone holder itself consisted of a stationary base plate and a sliding plate that could be secured using a threaded knob. This configuration allowed the mount to accommodate different phone sizes while still holding the phone securely.The threads of the knob were designed to be large enough to be successfully 3D printed, which helped ensure that the mechanism would function reliably without requiring post-processing. When tightened, the threaded knob presses the sliding plate against the phone, holding it firmly in place.

To guide the motion of the sliding plate, I designed a groove along the flat side portion of the mount. This groove allowed the plate to slide smoothly while maintaining alignment with the base plate. I also included small offsets at the top of the extruded features to prevent the phone from falling out in the perpendicular direction. 

#### Detent Mechanism

The detent mechanism was designed to allow the phone mount to rotate between fixed positions without requiring additional components such as springs or bearings.

The mechanism features a flexible ring that interfaces with circular “teeth.” When the knob is rotated, the ring flexes slightly and moves between the teeth, creating discrete positions. I chose to use a ring rather than individual prongs thinking that this would increase the stability of the mechanism. Because the phone adds significant weight to the mount, distributing the force around a continuous ring could help  maintain some structural integrity. The ring also ensures that the detent only disengages when the knob is intentionally rotated, preventing accidental movement of the phone mount.

### The Smarter CAD Model



### Manufacturing and Material Choice
This project strongly reinforced to me that the manufacturing method must be considered during the design process.

For the first and only filament print, I chose PLA. However, the use of support material caused the final design to fail. Initially, I believed I could rely on the technique of bridging, where filament solidifies across gaps without requiring support material. I expected that the geometry of the detent mechanism could be printed using this technique. However, other structures in the clamp required support material. Because the slicer could not regionally select support structures, supports were generated in areas that interfered with other parts of the design, which ultiamtely could not be removed. 

*While the importance of manufacturing constraints has been emphasized in class, this failure reinforced the concept.*

The design was  much better suited for pSLS printing rather than filament printing. In pSLS printing, powder naturally supports the printed structure and can easily be removed afterward. This eliminates many of the support issues encountered with filament printing. In addition, flexible Nylon would be a better material choice for this design. Nylon has greater flexibility and resilience than PLA, which would allow the clamp arms and detent mechanism to flex and move as intended without breaking.
