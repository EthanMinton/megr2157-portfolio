# A9 – Pulleys

## Objective

The objective of this assignment is to design a belt and pulley system that transfers power between two parallel shafts.

## Belt Design

### Belt Calculations
I started with two 3-inch pulleys spaced 5 inches apart and an initial belt tension of 5 lbf. Since the pulleys are the same diameter, the belt wraps halfway around each pulley. I assumed a coefficient of friction of 1.0 and used the belt friction equation at the point where the belt would start to slip. This gave me 9.586 lbf on the tight side and 0.414 lbf on the loose side.

I used the tight-side force to size the belt because that side sees the highest tensile stress. Using the given polyurethane yield strength of 471 psi and a safety factor of 3, I calculated a minimum cross-sectional area of 0.0610 in² and a minimum belt diameter of 0.2788 in. Adding the two straight spans and the two curved sections gave an installed outer circumference of 20.301 in for that minimum diameter.

<img width="3471" height="1248" alt="Belt_Calculations" src="https://github.com/user-attachments/assets/f87b5949-7968-4c0a-be48-78b0cb3d9aa7" />

### Belt Selection

I selected a 5/16-inch polyurethane round belt from McMaster-Carr. Its diameter of 0.3125 in gives it a cross-sectional area of 0.0767 in², which exceeds the required area. McMaster lists a minimum pulley diameter of 2.5 in, so the 3-inch pulleys meet that requirement. With the selected belt diameter, the installed outer circumference is 20.407 in. The belt’s unstretched circumference needs to be slightly shorter to achieve the initial tension of 5 lbf. 

<img width="1917" height="990" alt="image" src="https://github.com/user-attachments/assets/52b211ec-67e6-4499-8f83-7915f46f9b68" />

<img width="672" height="403" alt="image" src="https://github.com/user-attachments/assets/87f8e311-5814-470e-83db-61b2def8c03e" />

## Shaft Design

### Shaft Material 
I selected oil-quenched and tempered AISI 1060 steel from MatWeb. The heat treatment matters because the yield strength of 1060 steel depends on its condition. I used the listed yield strength of 89,500 psi for this condition in my torsion calculation

<img width="1900" height="988" alt="image" src="https://github.com/user-attachments/assets/95aa8bc7-65e9-473a-98dd-087761d7f7f4" />

### Shaft Calculations 
I used the difference between the tight-side and loose-side belt forces to find the shaft torque. Multiplying that difference by the 1.5-inch pulley radius gave a torque of 13.758 in·lbf. I set the torsional shear stress equal to the allowable shear stress using a safety factor of 3, then solved for the minimum shaft diameter. This gave me a minimum diameter of 0.1675 in under torsion. I chose a 0.20-inch shaft because it exceeds that minimum.

<img width="2302" height="1041" alt="Shaft_Calculations" src="https://github.com/user-attachments/assets/dfd83b0f-9fd5-443b-841a-0c574c091400" />

## Journal Bearing Design 
### Journal Bearing Calculations
I added the tight-side and loose-side belt forces to find the 10-lbf radial load on each shaft. I assumed the pulley was centered between two bearings, so each bearing carried 5 lbf. I used a 0.20-inch nominal bore to match the shaft and chose a 1-inch bearing length.

I divided the load on one bearing by its projected area to get a pressure of 25 psi. At 1500 rpm, the shaft surface speed was 78.54 ft/min. Multiplying pressure by surface speed gave a PV of 1,963.5 psi·ft/min.

<img width="2510" height="1564" alt="Journal_Bearing_Calculations" src="https://github.com/user-attachments/assets/a6e4de8f-8288-411a-aefc-0059e9010edb" />
### Journal Bearing Selection
I selected porous bronze because all three calculated values were below the limits listed in Table 4 of Machinery’s Handbook.

<img width="636" height="465" alt="image" src="https://github.com/user-attachments/assets/ef285918-ce2f-4259-b87f-f4d3dfcfa6cf" />

| Property | Calculated Value | Porous Bronze Limit |
|---|---:|---:|
| Bearing pressure | 25 psi | 4,500 psi |
| Surface speed | 78.54 ft/min | 1,500 ft/min |
| PV | 1,963.5 psi·ft/min | 50,000 psi·ft/min |

## Frame Design 

I made a rough sketch of the support frame to show how the two pulleys and their bearings would be arranged. I chose an 8.5 × 3.5 in mounting plate that would attach to the ceiling, as shown by the red dashed lines. The supports hang down from the plate. In the front view, the support is 6.5 in wide and 2.5 in tall, with the pulley shaft centers 5 in apart and 2 in below the underside of the mounting plate. The solid red outline shows the path of the belt around both pulleys.

In the side view, the pulley sits between two bearing housings. I used 1 in of length for each bearing seat and placed the bearing centers 2 in apart along the shaft. This leaves a 1 in gap for the pulley. The sketch uses a 0.50 in seat diameter based on the assumed outside diameter of the bearing. I used the sketch to lay out the main dimensions and check how the parts would fit together.

<img width="1528" height="970" alt="94891" src="https://github.com/user-attachments/assets/bd2bda4a-c15c-4026-885e-fc29a7abff52" />

## Lessons Learned 

One thing I learned was why the belt forces get subtracted for the shaft calculation but added for the bearing calculation. The tight side and loose side turn the pulley in opposite directions, so the difference between the forces determines the torque. Both sides pull the shaft toward the other pulley, so their forces add to give a 10-lbf radial load. With the pulley centered between two bearings, each bearing carries 5 lbf.

I also learned to separate the minimum size I calculated from the size I actually selected. My minimum belt diameter was 0.2788 in, but the belt I selected was 5/16 in. Using that larger diameter changed the installed outer circumference from 20.301 in to 20.407 in. Next time, I would update the belt length as soon as I choose a catalog size so the calculations and part selection match.

When I selected the journal bearing material, I learned that pressure alone was only one part of the check. The bearing also had to handle the shaft surface speed and the combined pressure and velocity, or PV. Several materials met the requirements, but I chose porous bronze because it had room across all three limits if the load or speed changed.

