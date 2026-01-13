---
title: "Syringe Pump"
excerpt: "A DIY programmable syringe pump that is compatible with 10 mL and 20 mL syringes, reaching maximum flow rates for each syringe at 1.24 mL/s and 2.2 mL/s, respectively."
header:
  image: /assets/img/LF3DP-Banner-2.jpg
  teaser: /assets/img/Large-Format-3D-Printer-Thumbnail.png
gallery:
  - image_path: assets/img/Slide-3.png
  - image_path: assets/img/Slide-2.png
  - image_path: assets/img/Slide-4.png
   
---

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |


# Features
### Design Overview
The syringe pump operates through the use of a Nema 17 Stepper motor, which is connected to a lead screw. A 3D-printed carriage holds a nut that is coupled to the plunger of the
syringe. As the lead screw rotates and the nut traverses along the screw, the plunger is pushed forward, expelling a proportional volume of liquid from the syringe. A linear rod secures the carriage, preventing side-to-side motion, ensuring that it does not rotate with the lead screw, and instead only has linear motion. A motor mounting plate holds the stepper motor at the correct height. Additionally, a support piece is used to prop up the barrel of the syringe, supporting both 20 mLand 10 mLsyringes. An end support functions to secure the lead screw and linear rod, while also propping up the nozzle of the syringe during use. Each support piece is secured to an aluminum extrusion using tee-nuts and M5 bolts. The
entire mechanical syringe pump assembly rests on a custom-designed electronic enclosure that holds all the necessary electronic components. It also features user-controlled buttons and displays for customization and control. 

### CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH90d2dQT28d5b602811642fa9b14f56ac7c?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

### Real-life Image of Syringe Pump Assembly


### Electrical Design 
The electronic enclosure was designed with a focus on adaptability and optimal print
quality. The enclosure features removable panels that seamlessly slide into the base, secured by corner slots. The lid fits into an inset in the corner supports, locking the side panels in place. Heat-set threaded inserts on the corner supports allow for easy fastening of the lid onto the base, ensuring complete security and repeatable removal. To enhance user experience, the enclosure includes clearly labeled buttons and a power cord insert, providing users with defined controls. The removable side panels provide numerous benefits. This design approach facilitates easy iteration and adjustment of designs allowing for swift corrections or improvements to specific panels without reprinting the entire enclosure. Additionally, the design allows for the panels to be printed lying flat on the print bed, enhancing strength in the z-direction and ensuring better print quality for holes and engraved text.
Inside the electronics enclosure, there are designated spaces dimensioned to hold the power supply, Arduino, and breadboard. The power supply and breadboard each are surrounded by walled sections, high enough for secure placement, but not obstructing any required access points. This prevents these components from shifting around when the assembly is picked up or moved. The Arduino is sitting on a raised platform that uses rods to secure it through its mounting holes, elevating the Arduino to lie flat with its backside pins protruding beneath it. A
pathway extends from the power supply holder through and between the Arduino and breadboard, allowing space for the power cord to run flat, avoiding bends and minimizing potential stresses. Proximity between the Arduino placement and breadboard allows for minimum wiring length and a clean electrical setup. Figure 2 below displays this interior design for the electronics.

### User Operation 
To operate the syringe pump at a given flow rate, first input the syringe size and desired flow rate into the Arduino code. Upload the code to the Arduino, then plug the syringe pump into
the wall outlet. Ensure the lid of the enclosure is properly secured down, and the syringe is placed properly in the pump. If slight adjustments to the carriage position need to be made, do so with the forward and reverse buttons on the control panel. Once the user is ready to dispense, click the start/stop button once and the syringe pump will begin operating at your desired flow rate. The LED will turn green when in motion. To slow the constant flow rate of the syringe pump, turn the potentiometer knob counterclockwise. When the user has dispensed the desired amount of fluid, press the start/stop button again to pause the motion of the carriage, the LED should turn yellow when paused. If the pump is allowed to dispense the total volume of the syringe, the pump will automatically stop operating and the LED will turn red. Use the forward and reverse buttons to readjust your carriage to the desired position, then unplug when finished operating. 


# Materials and Components
### Off-the-Shelf Parts


### Custom Parts 


# Code 
The syringe pump apparatus is programmed using an Arduino Uno microcontroller to control a stepper motor and a light-emitting diode (LED) with a three-button system. The code for the system can be found [here.](https://github.com/MOG78/SyringePumpCode/blob/main/ArduinoCode)

{% include gallery caption="Large Format 3D Printer Gallery" %}
