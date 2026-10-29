# A8 – Gears

## Objective

The objective of this assignment was to design a gearbox with a 24:9 gear ratio that delivers an output torque of 1.25 in-lbf at 1100 rpm. I analyzed the shaft stresses and bearing loads to determine whether the selected dimensions and bearing material were suitable. Using these results, I modeled the shafts and two-piece housing in SolidWorks and assembled them with the selected gears and bearings.

## Design Calculations
### Gear Ratio Calculations

Before moving into the shaft and bearing calculations, I first needed to determine the input speed, input torque, and power being transmitted through the gearbox. The assignment gives us a gear ratio of 24:9, an output speed of 1100 rpm, and an output torque of 1.25 in-lbf. Following the assignment’s assumption that the gear train is ideal, we can consider the input and output power equal, with no power lost through the gears. Using the gear ratio, I found that the input speed is 2933.33 rpm and the input torque is 0.46875 in-lbf. The transmitted power was then calculated as approximately 0.02182 hp. These results show that the smaller input gear rotates faster with less torque, while the larger output gear rotates slower with more torque. These values were then used in the remaining shaft and bearing calculations.

<img width="1087" height="287" alt="image" src="https://github.com/user-attachments/assets/3eb8a698-dfce-4098-a1b5-aebe841bfa39" />

### Shaft Shear Stress Calculations

For this section, I needed to determine whether the given shaft diameters were sufficient to handle the torque transmitted through the gears. The input shaft has a diameter of 0.125 inches and a torque of 0.46875 in-lbf, while the output shaft has a diameter of 0.250 inches and a torque of 1.25 in-lbf. The unknowns were the shear stresses in each shaft. For this simplified analysis, we considered both shafts as solid circular members under torsion. The FBDs show equal and opposite torques, giving a total moment of zero. Using the torsional stress equation, I substituted the polar moment of inertia and the shaft radius, simplifying the equation algebraically to τ = 16T/(πd³).

For the input power-transmission shaft, I used an allowable shear stress of 4000 psi from Machinery’s Handbook. The calculated shear stress was 1222.31 psi, which falls below this limit, meaning the given 0.125-inch diameter is sufficient. For the output short shaft, the allowable shear stress was 8500 psi, while the calculated stress was only 407.44 psi. This means that the given 0.250-inch output diameter is also sufficient. Based on these results, both assigned diameters were kept without needing to increase their sizes.

<img width="1630" height="747" alt="image" src="https://github.com/user-attachments/assets/fd81c065-b7d7-4531-a346-f798c80bb1ba" />

### Gear Force Calculations

Based on our previous torque calculations, I needed to determine the tangential and radial forces acting between the gears. The input pinion has a pitch diameter of 0.375 inches, while the output gear has a pitch diameter of 1.000 inch. The selected gears have a pressure angle of 20 degrees. Using the equation Ft = 2T/d, I calculated the tangential force for each gear separately, with both resulting in 2.5 lbf. Although their torques and diameters are different, the forces at the gear contact are equal in magnitude and opposite in direction.

The radial force was then calculated using Fr = Ft tan(α), resulting in 0.90993 lbf. This is the separating force that pushes the gears away from each other, while the tangential force transfers the torque. The diagram shows these two perpendicular components and their resultant, W. These forces were then used to determine the load for the journal bearing calculations.

<img width="1711" height="477" alt="image" src="https://github.com/user-attachments/assets/3c006cbe-b56c-4414-9178-8cdbf7d5c352" />

### Journal Bearing Pressure, Surface Velocity, and PV

In this section, I determined the operating pressure, surface velocity, and PV for both bearing sizes. I selected a bearing length of 0.250 inches for each shaft. Using our previous tangential and radial forces, I combined the two perpendicular components to find a resultant load of approximately 2.66044 lbf. For simplicity, I conservatively used this entire load to size each bearing, assuming the gear is positioned between its supports. The bearing FBD shows the applied shaft load and an equal, opposite housing reaction. Pressure was calculated by dividing the load by the projected area, dL. This resulted in an input bearing pressure of 85.134 psi and an output bearing pressure of 42.57 psi. The larger output shaft gives a larger projected area, which reduces its bearing pressure.

Using the shaft diameters and rotational speeds, I calculated the surface velocity with V = πdN/12, where dividing by 12 converts inches per minute to feet per minute. The input surface velocity was approximately 95.99 ft/min, while the output was 71.99 ft/min. Multiplying each pressure by its corresponding velocity resulted in an input PV of 8172.30 psi-ft/min and an output PV of 3064.61 psi-ft/min. Since the input bearing has the highest pressure, velocity, and PV, it governs our material selection. We then compared these calculated values with the material limits in the lecture slides.

<img width="1677" height="826" alt="image" src="https://github.com/user-attachments/assets/a5c32945-1bbf-486d-a473-a48637b7ad4b" />

### Material Selection 

Based on our previous bearing calculations, I selected porous bronze using the material table provided in the lecture slides. The table lists limits of 4500 psi for pressure, 1500 ft/min for surface velocity, and 50,000 psi-ft/min for PV. Our highest calculated values were 85.134 psi, 95.99 ft/min, and 8172.30 psi-ft/min. Since all three values fall below the material limits, porous bronze is suitable for both bearing sizes.

### Journal Bearing Thickness 

To determine the required wall thickness, I used a simplified compression model that assumes two bearing walls share the applied load equally. The total load-carrying area was therefore represented as 2tL. Using a bearing length of 0.250 inches, a resultant load of approximately 2.66 lbf, and a representative compressive yield strength of 11,000 psi for SAE 841 bronze, I assumed a safety factor of 2. This gives an allowable compressive stress of 5500 psi. After rearranging the stress equation algebraically and substituting these values, the minimum wall thickness was approximately 0.000967 inches. Both bearing sizes have the same load and selected length, so this model gives the same minimum thickness for each.

I then compared this result with the selected stock bearing dimensions. Using nominal inside and outside sizes of 0.125 and 0.250 inches for the input bearing, and 0.250 and 0.375 inches for the output bearing, both have a nominal wall thickness of 0.0625 inches. This exceeds the calculated minimum, meaning both selected walls are sufficient under the simplified compression model.

<img width="1685" height="722" alt="image" src="https://github.com/user-attachments/assets/33b34946-48bd-448c-935b-2524818b88a2" />

The 11,000 psi compressive yield strength came from page 2 of the NBM Metals SAE 841 sintered bronze material sheet, available through Aviva Metals. I used this as a representative material strength for our simplified bearing-wall calculation. With an assumed safety factor of 2, the allowable compressive stress was 5500 psi.

<img width="1077" height="193" alt="image" src="https://github.com/user-attachments/assets/97d62180-f53a-4b0c-8085-e0ec07a15e66" />

### Sketch of Gearbox Housing 

This sketch shows how the main and secondary housing halves fit together at their mounting flanges. I included four aligned screw holes, one at each corner, to secure the halves while allowing the gearbox to be disassembled. Removing the screws allows the halves to separate, providing access to the gears, shafts, and bearings. The shafts extend through opposite sides of the housing to provide the input and output connections.

<img width="820" height="753" alt="Math Scratch Paper (32)" src="https://github.com/user-attachments/assets/b6985ac1-c9a1-471e-b42b-cd85d504c5f7" />

## Design CAD Model
### Input Shaft Model

I created the global variables “INNER_DIA” = 0.125 inches and “INNER_LENGTH” = 1 inch to control the input shaft dimensions.

<img width="1250" height="518" alt="image" src="https://github.com/user-attachments/assets/f92ffbb5-e34f-48e1-83f4-dcb86542799e" />

I sketched a circle centered at the origin and linked its diameter to “INNER_DIA,” fully defining the sketch.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/768f3638-7881-4b4a-b967-2c326db53f71" />
I used extrusion and linked the extrusion depth to “INNER_LENGTH” to create the shaft.

<img width="1616" height="960" alt="image" src="https://github.com/user-attachments/assets/81024b4d-e6d4-458a-9a8d-f30201cd9a7d" />

#### 2157 Input Shaft Drawing
<img width="962" height="620" alt="image" src="https://github.com/user-attachments/assets/75d7eb8f-f158-45ed-9860-b8688697f61a" />

### Output Shaft Model 

I created the global variables “OUT_SHAFT_DIA” = 0.250 inches and “SHAFT_LENGTH” = 1 inch to control the output shaft dimensions.

<img width="1243" height="517" alt="image" src="https://github.com/user-attachments/assets/35dc0d7a-b573-4d39-a67d-018ee18cc653" />

I sketched a circle and linked its diameter to “OUT_SHAFT_DIA.”
<img width="1620" height="956" alt="image" src="https://github.com/user-attachments/assets/9c6f65aa-58fa-407a-a80c-f1bfc7e32720" />

I then used the Boss Extrude and linked its depth to “SHAFT_LENGTH” to complete the output shaft.

<img width="1616" height="957" alt="image" src="https://github.com/user-attachments/assets/7be59a8a-7025-4e15-99d7-eac7c31c4d49" />

#### 2157 Output Shaft Drawing

<img width="998" height="630" alt="image" src="https://github.com/user-attachments/assets/6d110e83-c275-436e-af95-48128f888a9c" />

### Bronze Sleeve Bearing 6391K131

I downloaded the CAD model for the McMaster-Carr 6391K131 bronze sleeve bearing to support the 0.250-inch output shaft. Its 0.250-inch length matches our calculations, and the drawing’s outside and inside diameters give a wall thickness of (0.376 − 0.251)/2 = 0.0625 inches. This exceeds our calculated minimum of 0.000967 inches under the simplified compression model. Our output bearing pressure of 42.57 psi, velocity of 71.99 ft/min, and PV of 3064.61 psi-ft/min also fall below the porous-bronze limits from the slides.

#### 2157 Bronze Sleeve Bearing 6391K131

<img width="1173" height="760" alt="image" src="https://github.com/user-attachments/assets/aff520df-47b4-455f-ba07-f1f018a4a7bb" />

### Bronze Sleeve Bearing 6391K111

I downloaded the CAD model for the McMaster-Carr 6391K111 bronze sleeve bearing to support the 0.125-inch input shaft. Its 0.250-inch length matches our calculations, and its nominal wall thickness of 0.0625 inches exceeds our calculated minimum of 0.000967 inches under the simplified compression model. Our input bearing pressure of 85.134 psi, velocity of 95.99 ft/min, and PV of 8172.30 psi-ft/min also fall below the porous-bronze limits from the slides.

#### 2157 Bronze Sleeve Bearing 6391K111

<img width="1176" height="760" alt="image" src="https://github.com/user-attachments/assets/975ff3b8-ab2a-491a-802e-22a8594cc403" />

### Main Gearbox Housing

I created global variables to control the housing wall thickness, gear dimensions, clearance, and bearing-hole sizes.

<img width="1246" height="521" alt="image" src="https://github.com/user-attachments/assets/dfa5ecfb-6a16-4880-925f-b17c0090c9c2" />

I sketched the rectangular housing walls and linked their 0.250-inch thickness to “THICKNESS_WALL.”

<img width="1621" height="957" alt="image" src="https://github.com/user-attachments/assets/6919ade3-5942-4e47-aa3c-256efbdabd1d" />

I extruded the wall profile using “MAX_GEAR_HEIGHT” to control the housing depth.

<img width="1616" height="960" alt="image" src="https://github.com/user-attachments/assets/d7010146-e5e6-41bb-a224-dd9becae05ee" />

I sketched a rectangle matching the outside edges of the housing to create the closing wall.

<img width="1617" height="953" alt="image" src="https://github.com/user-attachments/assets/735e4dfb-d675-43a6-8a75-799eb01d20cd" />

I extruded this rectangle using “THICKNESS_WALL” to give it a thickness of 0.250 inches.

<img width="1611" height="956" alt="image" src="https://github.com/user-attachments/assets/45109b4f-6717-4ac1-b138-2b00bbf9d864" />

I sketched the output bearing hole and positioned its center 0.80 inches from the upper edge.

<img width="1617" height="956" alt="image" src="https://github.com/user-attachments/assets/d905400a-0219-4a8d-be51-dfffe50d1e09" />

I used a Through All cut to create the opening for the output bearing.

<img width="1616" height="958" alt="image" src="https://github.com/user-attachments/assets/c5256325-9c37-49f0-86ea-b9cbf0dcdb07" />

I sketched an outer mounting flange and linked its width to “THICKNESS_WALL.”

<img width="1615" height="962" alt="image" src="https://github.com/user-attachments/assets/737698db-1b21-45a9-b462-0d32807c3bba" />

I extruded the flange using “THICKNESS_WALL” divided by two, giving it a thickness of 0.125 inches.

<img width="1627" height="955" alt="image" src="https://github.com/user-attachments/assets/180064f4-b119-4ead-bbc1-fdf4997c7b5b" />

I used Hole Wizard to add four mounting holes sized for #2 binding-head screws.

<img width="1622" height="937" alt="image" src="https://github.com/user-attachments/assets/72684510-9e99-4109-8894-cd0c141cdec5" />

I added 0.050-inch fillets to the selected housing edges to round the sharp corners.

<img width="1616" height="957" alt="image" src="https://github.com/user-attachments/assets/e4502a3c-bc43-4bed-80ee-9732e1f59e9b" />

#### 2157 Main Gearbox Housing 

<img width="1117" height="723" alt="image" src="https://github.com/user-attachments/assets/8413c9d7-5a44-456e-b952-7003bd39f860" />


### Secondary Gearbox Housing

I created the secondary housing using the same wall thickness, extrusions, mounting flange, screw holes, and fillets as the main housing. The main difference was the bearing-hole sketch, which I resized for the smaller input bearing and constrained to align with the input shaft in the assembly. I also added the pitch-diameter equation to calculate the required 0.6875-inch spacing between the shaft centers.

<img width="1248" height="516" alt="image" src="https://github.com/user-attachments/assets/f5af9df4-f750-4486-b413-b02926600fa5" />

<img width="1621" height="960" alt="image" src="https://github.com/user-attachments/assets/12e7ddf0-cb46-4ce1-817e-4c1a4ecbb28e" />

#### 2157 Secondary Gearbox Housing
<img width="1118" height="721" alt="image" src="https://github.com/user-attachments/assets/816ea2c8-545d-45dc-81e0-7563506bb920" />

### Assembly 

To assemble the gearbox as the assembly shows, the bronze bearings are first seated in their corresponding housing holes. The gears are press-fitted onto their shafts, and the shafts are inserted through the bearings. The housing halves are then brought together, aligning the mounting holes while positioning the gears at the calculated 0.6875-inch center distance. Screws and matching nuts secure the joining flanges and allow the housing to be opened again. In SolidWorks, the gears are locked rotationally to their shafts, while the shafts remain free to rotate inside the bearings. A gear mate controls their relative rotation using the 18:48 tooth ratio. Removing the fasteners allows the housing halves to separate so the internal components can be accessed.


<img width="1617" height="961" alt="image" src="https://github.com/user-attachments/assets/43d087ca-36b7-428d-ad1c-ef71ae7753e6" />

<img width="1616" height="958" alt="image" src="https://github.com/user-attachments/assets/38e4f8f7-4d8d-4d6c-ba3a-2a67c16315fb" />

## Lessons Learned 

The most difficult part of this assignment was getting the gears and shafts to rotate properly in the assembly. I was mostly used to static mating, where the goal was to fully constrain the parts so they could not move. This assignment required me to think about which movements needed to remain available. At first, some parts would not rotate, while others moved out of position. Working through these issues helped me understand how concentric mates, axial positioning, and locking rotation affect the assembly. I also learned that the gear mate controls the rotation ratio, while the other mates establish the position and alignment of the gears.

Another difficulty was SolidWorks crashing and causing me to lose progress. Having to repeat work was frustrating and added time to the project, but it reinforced the importance of saving frequently, especially before making larger changes to the assembly.

One part I thought was really cool was being able to download the gear and bearing models directly from McMaster-Carr. This saved modeling time and allowed me to design around the dimensions of actual purchased components. I will use this resource in future projects when working with standard parts. Overall, this assignment helped me connect hand calculations, parametric modeling, and moving assemblies while showing how a small change in one part can affect the fit of the entire gearbox.

The project took roughly 14 hours to complete, with most of the time being dedicated to all of the CAD requirements ask of me.

## Resources 

PLEASE NOTE: You must download all of the files below in order to properly access the assembly.

[Input Gear — 7880K19](https://www.mcmaster.com/7880K19/)

[Output Gear — 7880K24](https://www.mcmaster.com/7880K24/)

[Input Bearing — 6391K111](https://www.mcmaster.com/6391K111/)

[Output Bearing — 6391K131](https://www.mcmaster.com/6391K131/)

[Binding-Head Screw — 91793A077](https://www.mcmaster.com/91793A077/)

[SAE 841 Bronze Strength Data Sheet](https://www.avivametals.com/assets/files/nbm-sae841.pdf)
