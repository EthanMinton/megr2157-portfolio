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

## Design CAD Model
## Analyze


## Decide


## Communicate

