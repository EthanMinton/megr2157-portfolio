# A11 – Motor Selection

Group Members:

Grant Parker

Ethan Minton

Bryan Mccanch

## Objective — Ethan

The objective of this assignment is to continue the tensile tester design from A10 by selecting motors and designing the mounts, couplers, frame connections, and floating bearing mounts. We will use engineering calculations and FEA to check whether the design can support the 2,000 N load with a safety factor of 4 while providing a crosshead speed of 1–50 mm/min. We will also create the CAD assembly and drawings, document our design decisions, and estimate the material and labor costs.

Ethan completed the documentation, organizing the calculations, CAD screenshots, FEA results, and explanations into the portfolio. Grant completed the engineering calculations, including the motor torque and power requirements, motor mount thickness, coupler torsional stress, and frame bracket stress checks. Bryan created the CAD models and assemblies, including the motor mounting plate, coupler, floating bearing mount, and frame arrangement.

## Motor Selection — Grant

### Knowns and Unknowns

The goal of this section was to select a motor that could turn each lead screw while meeting the tensile load and crosshead speed requirements. We used the results from A10 as our starting point. The total 2,000 N load is assumed to be centered between the two screws, giving a load of 1,000 N per screw.

We selected two identical motor and gearbox assemblies, with one assembly driving each lead screw. The torque and power requirements below apply to one screw and its motor.

| **Known Parameter** | **Value** |
| :--- | :--- |
| Maximum Tensile Load | 2,000 N |
| Number of Lead Screws | 2 |
| Load per Screw | 1,000 N |
| Screw Lead | 3.175 mm/rev |
| Required Crosshead Speed | 1–50 mm/min |
| Required Screw Speed from A10 | 0.315–15.75 RPM |
| Estimated Operating Torque per Screw from A10 | 1.63 N·m |
| Required Safety Factor | 4 |

| **Unknown Parameter** | **What Needed to Be Determined** |
| :--- | :--- |
| Required Design Output Torque | Torque required at each lead screw after applying the safety factor |
| Required Mechanical Power | Power needed at the required torque and maximum screw speed |
| Selected Motor Type and Model | Motor and gearbox suitable for the application |
| Required Motor Rotor Speed and Torque | Motor-side requirements based on the selected gearbox |
| Available Running Torque | Torque available throughout the required speed range |
| Motor Operating Specifications | Voltage, current, and efficiency |
| Shaft and Mounting Dimensions | Dimensions needed for the coupler and motor mount |

### Required Torque

The estimated operating torque from A10 was 1.63 N·m per screw. We applied the required safety factor of 4 to determine the design torque that each motor and gearbox assembly needs to deliver.

<img width="896" height="337" alt="image" src="https://github.com/user-attachments/assets/fa38610c-198d-442f-882d-03d2f7b7a7ce" />

The calculation gives a required output torque of **6.52 N·m for each motor and gearbox assembly**. This includes the safety factor of 4 and represents the torque needed at each lead screw.

### Required Power

We calculated the mechanical power using the torque requirement and the maximum screw speed from A10. We used the maximum speed because it requires the greatest mechanical power when the torque remains the same.

<img width="897" height="315" alt="image" src="https://github.com/user-attachments/assets/b80213b0-74ed-4a3b-9472-71cb0636b9c9" />

The estimated operating power is **2.69 W per screw**, while the required design power is **10.75 W per screw** at the maximum speed. These values describe mechanical power at the gearbox output. Electrical input power would be higher because of losses in the motor and gearbox.

### Motor Type and Selection

We selected the **23HS30-2904S-MG10**, a NEMA 23 bipolar stepper motor with a 10:1 planetary gearbox. A stepper motor fits this application because it moves in small increments, which is useful for slowly moving the crosshead during a tensile test.

The gearbox reduces the output speed and increases the available output torque. This helps match the motor to the low screw speed and torque requirements carried forward from A10.

<img width="2253" height="1251" alt="image" src="https://github.com/user-attachments/assets/35b51ef6-f612-46e2-a42a-f1bfa8e64e37" />

The screenshot above identifies the selected motor assembly. Each lead screw has its own motor. The keyed output shaft connects to the coupler, while the front mounting face connects to the motor mounting plate.

<img width="1817" height="1200" alt="image" src="https://github.com/user-attachments/assets/bea1f16a-c630-469a-b6b0-62d4cc7f84f2" />

The **90% efficiency** applies to the gearbox. We used this value when determining the torque required from the motor rotor. It does not include the motor's electrical losses, so it does not represent the overall efficiency of the complete assembly.

### Motor Speed Verification

After selecting the motor, we used its 10:1 gearbox ratio to determine the rotor speed needed to achieve the screw speed calculated in A10. The motor rotor turns ten times for every one revolution of the gearbox output shaft.

<img width="897" height="265" alt="image" src="https://github.com/user-attachments/assets/e323affc-acf5-4b81-8caf-87f437496ff5" />

The calculation gives a required motor rotor speed of **3.15–157.5 RPM**. This corresponds to a gearbox output and screw speed of **0.315–15.75 RPM**, producing the required crosshead movement of **1–50 mm/min**.

### Torque Output Verification

We used the selected gearbox ratio and efficiency to determine the motor rotor torque needed to produce our required output torque. The gearbox increases torque through its reduction ratio, while its efficiency accounts for mechanical losses.

<img width="887" height="277" alt="image" src="https://github.com/user-attachments/assets/3495ee8a-68f7-4cc3-beb8-ded13b3758f9" />

The calculation shows that the motor rotor must provide approximately **0.725 N·m** to deliver the required **6.52 N·m** at the gearbox output. The safety factor is already included in this requirement.

We then compared the required torque with the running torque shown on the torque–speed curve.

### Torque–Speed Curve Verification

We used the torque–speed curve to check whether the selected assembly could provide enough torque while rotating. A stepper motor's available torque changes with speed, so holding torque alone would not show whether the motor could turn the lead screw under load.

<img width="1747" height="805" alt="image" src="https://github.com/user-attachments/assets/6f712d57-54c1-4bf0-9d94-0b51225dd8b3" />

The torque–speed curve shows approximately **13.28 N·m of pull-out torque at 15.7 output RPM**, which is close to our maximum required screw speed of **15.75 RPM**. This exceeds the required design torque of **6.52 N·m**, which already includes the safety factor of 4.

Since the curve shows gearbox output torque, we compared it directly with our required output torque. The available torque also remains above our requirement at the lower speeds shown within the operating range.

### Motor Supply Voltage

We selected **36 V DC** as the driver supply basis for our motor verification. The published motor torque–speed chart includes 36 V and 48 V curves, and our supplied gearbox-output curve matches the 36 V data after accounting for the gearbox.

The published test conditions list a **DM542Y driver**, **2,000 pulses per revolution**, and **2.84 A peak current**. The motor itself is rated for **2.9 A per phase**.

### Motor Selection Conclusion

We selected the **23HS30-2904S-MG10** for each lead screw based on the calculated requirements and supplied torque–speed curve. The displayed running torque near the maximum required screw speed exceeds our design torque requirement.

We used **36 V DC** as the driver supply basis for this selection. The supplied graph does not extend down to the minimum required output speed of **0.315 RPM**, so operation at that speed remains unverified. The applicable gearbox torque rating also remains to be confirmed.

| **Parameter** | **Value** |
| :--- | :--- |
| Selected Motor | 23HS30-2904S-MG10 |
| Motor Type | NEMA 23 Bipolar Geared Stepper |
| Quantity | 2 — one per lead screw |
| Gear Ratio | 10:1 |
| Gearbox Efficiency | 90% |
| Rated Current | 2.9 A/phase |
| Driver Supply Voltage Basis | 36 V DC |
| Published Curve Test Current | 2.84 A peak |
| Required Design Output Torque | 6.52 N·m per assembly |
| Required Motor Rotor Torque | Approximately 0.725 N·m |
| Required Gearbox Output Speed | 0.315–15.75 RPM |
| Required Motor Rotor Speed | 3.15–157.5 RPM |
| Required Crosshead Speed | 1–50 mm/min |
| Required Design Mechanical Output Power | 10.75 W per assembly at maximum speed |
| Pull-Out Torque at 15.7 Output RPM | 13.28 N·m |
| Motor Frame Size | 57 × 57 mm |
| Front Mounting Holes | 4 × Ø5.2 mm |
| Mounting Hole Pattern | 47.14 × 47.14 mm square |
| Locating Boss Diameter | 40 mm |
| Output Shaft Type | Keyed |
| Output Shaft Diameter | 14 mm |
| Output Shaft Length | 34 mm |

## Motor Mount Design — Grant

### Knowns and Unknowns

The goal of this section was to design a mount that secures the motor to the frame and maintains alignment between the gearbox output shaft and lead screw. We used the selected motor's mounting pattern to determine the bolt locations, then calculated the plate thickness required to resist bearing stress at the bolt holes.

| **Known Parameter** | **Value** |
| :--- | :--- |
| Estimated Operating Torque per Screw | 1.63 N·m |
| Required Safety Factor | 4 |
| Number of Motor Mounting Bolts | 4 |
| Motor Mounting Hole Pattern | 47.14 × 47.14 mm |
| Motor Mounting Hole Diameter | 5.2 mm |
| Selected Bolt Diameter | 5.0 mm (M5) |
| Assumed Aluminum Yield Strength Used in Calculation | 276 MPa |

| **Unknown Parameter** | **Symbol** |
| :--- | :--- |
| Distance from Shaft Center to Each Bolt | r |
| Force per Bolt | Fb |
| Bearing Stress at Each Bolt Hole | σb |
| Minimum Plate Thickness for Bearing Stress | t_min |
| Selected Plate Thickness | t |

### Mounting Pattern and Dimensions

We used the manufacturer drawing to locate the four mounting holes around the gearbox output shaft. The holes form a **47.14 × 47.14 mm square pattern** and have a diameter of **5.2 mm**. We selected M5 bolts to connect the motor to the mounting plate.

<img width="805" height="797" alt="image" src="https://github.com/user-attachments/assets/be62c0b4-3570-47c4-acbe-86d612b2a5f4" />

<img width="2260" height="881" alt="image" src="https://github.com/user-attachments/assets/7b899ee5-0c09-4292-832c-d1be898a770f" />

We used these dimensions to position the motor mounting holes and center opening. The circular recess fits around the gearbox's locating boss, keeping the mount centered on the output shaft.

### Free-Body Diagram

We modeled the motor torque as being resisted equally by the four mounting bolts. Each bolt applies a tangential reaction at the same distance from the shaft center. These reactions resist rotation of the motor housing.

<img width="1114" height="428" alt="image" src="https://github.com/user-attachments/assets/574f0bcd-f694-40e4-a8e7-0147e8896e7d" />

The diagram shows how the torque is distributed across the bolt pattern. This analysis assumes that the four bolts share the torque equally and resist it through bearing contact at the holes.

### Bearing Stress and Thickness Calculations

We used the force at each bolt to calculate bearing stress in the aluminum plate. The bearing area depends on the plate thickness and bolt diameter. Increasing the thickness increases this area and reduces the bearing stress.

We applied the safety factor of 4 to the assumed material yield strength to determine the allowable stress.

<img width="1048" height="982" alt="image" src="https://github.com/user-attachments/assets/e2f4b127-9e3c-401e-a8f9-fcf35786c74c" />

The derivation gives the minimum plate thickness needed for this bearing-stress check. The operating torque is used to calculate the bolt force, and the safety factor is applied through the allowable stress.

### Numerical Calculations

We first determined the distance from the shaft center to each bolt using the square mounting pattern. This gave a bolt radius of approximately **33.33 mm**. We then used the operating torque to calculate the force at each bolt.

<img width="1102" height="707" alt="image" src="https://github.com/user-attachments/assets/04cb0bb6-4aba-486b-8094-11a4cd6570e3" />

The calculated operating force is **12.23 N per bolt**, giving a minimum plate thickness of **0.0354 mm** for bearing stress with the safety factor included.

This small result applies specifically to local bearing stress at the motor mounting holes. The complete bracket must also resist bending and maintain alignment during operation.

### Selected Thickness

We selected a **6.35 mm (0.25 in) aluminum plate**, which exceeds the calculated minimum bearing thickness. This provides a practical plate thickness for mounting the motor, although the bracket's overall stiffness still depends on its shape and connection to the frame.

| **Parameter** | **Value** |
| :--- | :--- |
| Motor Mounting Hole Pattern | 47.14 × 47.14 mm |
| Motor Mounting Hole Diameter | 5.2 mm |
| Bolt Diameter | 5.0 mm (M5) |
| Bolt Radius | 33.33 mm |
| Operating Force per Bolt | 12.23 N |
| Safety Factor Used in Bearing Check | 4 |
| Minimum Thickness for Bearing Stress | 0.0354 mm |
| Selected Plate Thickness | 6.35 mm (0.25 in) |

### Motor Mount Conclusion

The selected **6.35 mm aluminum plate** exceeds the minimum thickness required by the motor-hole bearing-stress calculation. We used the manufacturer mounting pattern to position the motor relative to the lead screw.

The final assembly shows the four-fastener connection between each motor mount and the top frame member. The bearing-stress calculation checks the bolt-hole area; it does not verify the bending stiffness of the complete mount.

### Aluminum Mounting Plate CAD Model

We modeled the motor mounting plate using the selected thickness of **6.35 mm** and the mounting dimensions from the manufacturer's drawing. The plate includes four mounting holes, a center opening for the output shaft, and a circular recess for the gearbox's locating boss.

<img width="1546" height="988" alt="image" src="https://github.com/user-attachments/assets/fd12ba95-bdaa-4d2d-ac7c-391dc01f1649" />

The center opening and recess are aligned with the mounting pattern so the plate can sit against the gearbox mounting face while allowing the output shaft to extend through it.

We then assembled the plate to the motor in CAD, aligning the center features with the gearbox and matching the mounting holes.

<img width="2030" height="1212" alt="image" src="https://github.com/user-attachments/assets/242dbed3-3fae-4dd7-8b33-cbc9b58aaf72" />

<img width="2168" height="1074" alt="image" src="https://github.com/user-attachments/assets/0e48cc42-3724-4e00-9049-229ca62c8225" />

The assembly view shows the plate against the gearbox, with the output shaft extending through the center opening for the coupler.

## Coupler Design — Grant

### Knowns and Unknowns

| **Known Parameter** | **Value** |
| :--- | :--- |
| Design Torque, T | 6.52 N·m |
| Internal Diameter Used, Di | 16.891 mm |
| Proposed Outer Diameter, Do | 30 mm |
| Material | AISI 1018 Steel |
| Assumed Yield Strength, Sy | 220 MPa |

| **Unknown Parameter** | **Symbol** |
| :--- | :--- |
| Maximum Torsional Shear Stress | τ_max |
| Shear Yield Strength | τ_yield |
| Minimum Outer Diameter | Do_min |
| Minimum Wall Thickness | t_min |

### Coupler Layout and Free-Body Diagram

We began with a sketch showing the motor shaft, coupler, and lead screw along the same axis. The motor supplies torque through the key, and the coupler transfers that torque to the threaded lead screw connection.

<img width="886" height="617" alt="image" src="https://github.com/user-attachments/assets/765bb8f9-888f-4563-b89a-ab810db079fe" />

The opposing torques shown in the sketch represent the torque transmitted through the coupler. We selected a starting outer diameter of **30 mm** and estimated the engagement depth at each end. We used these dimensions for the initial stress calculation and CAD model.

### Torsional Stress and Diameter Check

We modeled the coupler as a hollow circular section and used the larger internal diameter for the torsion calculation. This represents the thinner wall section of the proposed coupler.

We used the assumed steel yield strength to determine the shear yield strength, then compared this limit with the calculated shear stress. Since the design torque already includes the safety factor, we did not apply it a second time.

<img width="791" height="552" alt="image" src="https://github.com/user-attachments/assets/f2fe860a-12d2-4262-8de2-c927366ac597" />

The calculated shear stress is approximately **1.37 MPa**, below the **110 MPa shear yield strength** used in the analysis. The minimum outer diameter is approximately **17.15 mm**, so the selected **30 mm outer diameter** passes this nominal torsional-stress check.

Using the larger internal diameter, the selected geometry provides approximately **6.55 mm of radial wall thickness**.

| **Result** | **Value** |
| :--- | :--- |
| Calculated Maximum Nominal Shear Stress | 1.37 MPa |
| Shear Yield Strength Used | 110 MPa |
| Minimum Outer Diameter | Approximately 17.15 mm |
| Minimum Radial Wall Thickness | Approximately 0.13 mm |
| Selected Outer Diameter | 30 mm |
| Selected Radial Wall Thickness | Approximately 6.55 mm |

### CAD Model

We modeled the coupler with separate connection features at each end. The motor side includes a bore and keyway, while the lead screw side includes an internal thread.

<img width="890" height="621" alt="image" src="https://github.com/user-attachments/assets/75123a33-ec1d-4ad5-a83a-3146cf373290" />

The motor-side bore fits over the output shaft, while the key transfers torque between the shaft and coupler.

<img width="1093" height="565" alt="image" src="https://github.com/user-attachments/assets/3e3d7bc9-217f-4594-98a2-232283f4b3d7" />

We modeled the key as a separate component so it could be included in the assembly between the motor shaft and coupler.

<img width="1113" height="640" alt="image" src="https://github.com/user-attachments/assets/eafb00e0-758c-4248-a7b1-31ee4d64a647" />

The threaded end provides the connection to the lead screw. Its thread specification must match the selected **5/8"-8 right-hand ACME screw**.

### Motor and Coupler Assembly

We positioned the coupler on the gearbox output shaft and aligned the key with the shaft and coupler keyways.

<img width="1453" height="796" alt="image" src="https://github.com/user-attachments/assets/a316f82f-3839-4b3a-b992-d12c32353795" />

The transparent view shows how the key fits between the shaft and coupler and where the coupler sits relative to the motor mount.

<img width="1599" height="975" alt="image" src="https://github.com/user-attachments/assets/c455c77b-2eec-494d-b96f-c91d5d863505" />

The completed view shows the coupler extending from the motor assembly, with the threaded opening available for the lead screw connection.

### Coupler Design Conclusion

The selected **30 mm outer diameter** exceeds the calculated minimum diameter of approximately **17.15 mm**. The nominal torsional shear stress is also below the shear yield strength used in the analysis. These results support the coupler body dimensions for the applied design torque.

## Frame Connector Analysis — Bryan

### Knowns and Unknowns

The goal of this section was to check the brackets connecting the top frame member to the vertical supports. These connections must transfer the tensile load into the uprights and resist the twisting caused by the motors.

We used two **1,000 N screw loads** and a torque of **13.28 N·m per motor** from the selected torque–speed curve. The bracket calculations use a thickness of **6 mm** and an effective section width of **39 mm**.

| **Known Parameter** | **Value** |
| :--- | :--- |
| Total Axial Load | 2,000 N |
| Number of Motors | 2 |
| Torque Used per Motor | 13.28 N·m |
| Moment Arm Used in Calculation | 107 mm |
| Bracket Thickness | 6 mm |
| Effective Bracket Width | 39 mm |
| Assumed Tensile Yield Strength | 276 MPa |
| Assumed Shear Strength | 207 MPa |
| Required Safety Factor | 4 |

| **Unknown Parameter** | **Symbol** |
| :--- | :--- |
| Vertical Reaction at Each End | Pv |
| Transverse Reaction from Motor Torque | Pt |
| Nominal Normal Stress | σ |
| Nominal Shear Stress | τ |

### Frame and Bracket Arrangement

We used L-shaped connector plates to connect the horizontal frame members to the vertical supports. Each plate spans the corner so that its fasteners connect both frame members.

<img width="446" height="557" alt="1_Frame_Idea_to_verify" src="https://github.com/user-attachments/assets/b6dd3eee-3ba1-47cd-840f-02a6da58a667" />

The CAD view shows the bracket arrangement at the top and bottom of the frame. This analysis focuses on the upper connections, where the lead screw loads and motor reaction torques enter the frame.

### Free-Body Diagrams and Calculations

We began by drawing the two **1,000 N screw loads** on the top frame member. With symmetric loading and support locations, each end carries a vertical reaction of **1,000 N**.

The normal-stress calculation assumes that two bracket plates share each end reaction equally, giving a vertical load of **500 N per plate**.

We also represented the two motor torques as a combined moment resisted by opposing transverse reactions at the frame connections. Using the **107 mm moment arm** shown in the calculations gives a transverse reaction of approximately **248.22 N**.

The diagrams separate the vertical loading from the motor-induced twisting. We used these reactions in the bracket stress calculations.

We calculated the nominal stresses using the bracket's **6 mm thickness** and **39 mm effective width**. The transverse reaction was used for the shear-stress check, while the **500 N vertical load per plate** was used for the normal-stress check.

The material strengths were divided by the required safety factor of 4 to determine the allowable stresses.

<img width="438" height="341" alt="2_Bracket_Hand_Calcs" src="https://github.com/user-attachments/assets/365a15af-a841-49ed-bc29-0f923b65a782" />

The calculated shear stress is approximately **1.06 MPa**, below the assumed allowable shear stress of **51.75 MPa**. The calculated normal stress is approximately **2.14 MPa**, below the allowable normal stress of **69 MPa**.

| **Result** | **Value** |
| :--- | :--- |
| Vertical Reaction per Frame End | 1,000 N |
| Vertical Load per Plate, Assuming Equal Sharing | 500 N |
| Transverse Reaction Used in Shear Check | 248.22 N |
| Calculated Nominal Shear Stress | 1.06 MPa |
| Allowable Shear Stress | 51.75 MPa |
| Calculated Nominal Normal Stress | 2.14 MPa |
| Allowable Normal Stress | 69 MPa |

### Frame Connector Conclusion

The proposed **6 mm-thick brackets** pass the nominal normal- and shear-stress checks under the loading assumptions used. These results support the bracket section for transferring the calculated reactions between the top member and vertical supports. The fasteners and T-slot connections still need to be checked separately.

## Top Frame FEA — Bryan

### Fixtures and Axial Loading

We constrained both ends of the top member to represent its connections to the vertical frame supports. These fixtures treat the connections as rigid and do not include movement within the brackets or fasteners.

The intended axial loading is **1,000 N at each lead screw location**, giving a total load of **2,000 N**. The loads enter the extrusion through the mounting regions around the shaft openings.

<img width="499" height="386" alt="3_Top_Bar_Fixture Force" src="https://github.com/user-attachments/assets/2eb52255-94c5-4462-b614-4915252760e3" />

The screenshot shows the supported ends and selected loading faces. This represents the load passing from the two screw locations through the top member and into the vertical supports.

### Motor Torque Loading

We also included motor reaction torque at the mounting locations. We used **13.28 N·m** from the selected torque–speed curve to examine the frame under the motor's displayed output torque.

<img width="379" height="393" alt="4_Top_Bar_Torque" src="https://github.com/user-attachments/assets/d1ec49d1-7b42-458a-8567-75567e9ad90a" />

Including torque accounts for twisting as well as bending from the axial loads. The complete loading case requires torque at both motor locations.

### Initial Stress and Displacement Results

We first reviewed the coarse-mesh results to identify the stress distribution and overall deformation.

<img width="755" height="451" alt="5_Top_Bar_Stress1" src="https://github.com/user-attachments/assets/2b5d9eb8-b18f-4554-97c9-f236967ec64d" />

The initial maximum von Mises stress was **41.54 MPa**. The higher stresses were concentrated near the shaft openings and mounting regions, where the loads enter the extrusion.

<img width="701" height="445" alt="6_Top_Bar_Defl1" src="https://github.com/user-attachments/assets/7345c21a-6dac-41ba-8697-330bec0b2d0a" />

The initial maximum resultant displacement was **0.02844 mm**. Movement was greater between the supported ends, while displacement at the fixtures remained constrained.

### Mesh Refinement and Comparison

We compared the coarse-mesh results with a medium-mesh run to see how much the results changed with refinement.

<img width="527" height="377" alt="8_Top_Bar_Stress2" src="https://github.com/user-attachments/assets/31e05165-a88b-463e-82eb-d5f8dbb04490" />

<img width="683" height="384" alt="9_Top_Bar_Defl2" src="https://github.com/user-attachments/assets/bc358897-2d57-44f2-87bb-02f046accc01" />

| **Result** | **Coarse Mesh** | **Medium Mesh** |
| :--- | :--- | :--- |
| Maximum von Mises Stress | 41.54 MPa | 43.70 MPa |
| Maximum Resultant Displacement | 0.02844 mm | 0.02857 mm |
| Stress Change | — | Approximately 5% |
| Displacement Change | — | Approximately 0.46% |

<img width="351" height="138" alt="10_Top_Bar_Convergence" src="https://github.com/user-attachments/assets/8eb70c47-30bc-40cf-970d-8a8390fc85e7" />

The displacement changed very little between the two runs, while the maximum stress increased by approximately **5%**. The displacement was less sensitive to the mesh than the local peak stress. Another refinement near the critical opening would help determine whether the peak stress has stabilized.

### Critical Stress Location and Safety Factor

We reviewed a close-up of the refined result to identify the maximum-stress location.

<img width="595" height="539" alt="7_Max_Stress_Location" src="https://github.com/user-attachments/assets/b20ed6a6-649e-4978-8b7f-8ab1c7a42b51" />

The maximum stress occurs at the edge of a shaft opening near the loaded mounting region. The opening interrupts the extrusion wall and concentrates stress as the load passes into the surrounding material.

Using the study's displayed yield strength of **275 MPa** and refined maximum stress of **43.70 MPa** gives a minimum factor of safety of approximately **6.29**. This exceeds the required safety factor of **4**.

| **Final Result** | **Value** |
| :--- | :--- |
| Maximum von Mises Stress | 43.70 MPa |
| Critical Location | Edge of a shaft opening near the mounting region |
| Maximum Resultant Displacement | 0.02857 mm |
| Calculated Minimum Factor of Safety | 6.29 |
| Required Factor of Safety | 4 |

### Load Path and Proposed Improvement

The axial loads pass through the mounting regions into the extrusion walls and internal ribs, then toward the supported ends. The motor torques also twist the member. The displacement plots show the combined deformation, although angular twist was not separately measured.

We proposed using larger load-spreading plates around the mounting openings. These could distribute the loads over more of the extrusion and reduce local deformation. A revised study would be needed to determine whether this reduces the peak stress or moves its location.

### Top Frame Conclusion

Under the modeled loading and support conditions, the refined maximum stress gives a factor of safety of **6.29**, exceeding the required value of **4**. The maximum resultant displacement is **0.02857 mm**.

These results support the strength of the modeled top member. The remaining verification includes confirming the complete load settings, documenting the mesh details, and measuring vertical displacement at the grip line.

## Vertical Frame FEA — Bryan

### Fixtures and Loading

We fixed the bottom face of the vertical member to represent its connection to the base. This treats the base connection as rigid and prevents movement at the selected face.

<img width="380" height="281" alt="11_Side_Bar_Fixture" src="https://github.com/user-attachments/assets/d97fbfd2-b625-4821-ad38-9bbc4c0e4ec5" />

The intended axial compression is **1,000 N per upright**, based on the symmetric load distribution from the frame calculations. The screenshots show the fixed support and transverse loading. The axial compression load settings are not shown.

We also applied a transverse force at the top of the member to represent the lateral reaction transferred through the upper frame connection.

<img width="594" height="597" alt="13_Side_Bar_Transverse_Force" src="https://github.com/user-attachments/assets/61ca56e5-8dc9-4f19-9cb3-c833f988adce" />

For this loading case, compression acts along the upright while the transverse force bends it. Both loads are needed to represent the combined loading.

### Initial Stress Result

We first reviewed the coarse-mesh stress result to identify the most heavily loaded region.

<img width="440" height="417" alt="14_Side_Bar_Stress1" src="https://github.com/user-attachments/assets/d175039a-5aa3-4f9c-b722-d50757baa8db" />

The initial maximum von Mises stress was **8.365 MPa**. Stress increased toward the bottom of the member, where the fixed support resists the bending caused by the transverse load.

<img width="440" height="417" alt="14_Side_Bar_Stress1" src="https://github.com/user-attachments/assets/c646fafd-73bc-4778-a447-5401b7a95455" />

The close-up shows the peak stress near the fixed bottom edge. This location is affected by both the loading and the rigid support assumption.

### Initial Displacement Result

<img width="558" height="521" alt="16_Side_bar_Defl1" src="https://github.com/user-attachments/assets/0019b7a5-d652-4c31-96d7-c258685e2198" />

The maximum resultant displacement was **0.1398 mm**, occurring near the top of the member. Displacement increased with distance from the fixed base, showing the bending caused by the transverse load.

This plot reports total displacement, which includes movement in all directions. It does not separately report vertical displacement at the grip line.

### Mesh Refinement and Comparison

We compared the coarse-mesh results with a medium-mesh run to see how the results changed after refinement.

<img width="631" height="494" alt="16_Side_Bar_Stress2" src="https://github.com/user-attachments/assets/3281fe89-1c8b-4828-8488-6ae7e974df04" />

The refined maximum von Mises stress was **8.167 MPa**, with the critical region remaining near the fixed base.

<img width="539" height="462" alt="17_Side_Bar_Defl2" src="https://github.com/user-attachments/assets/f93d98a3-fae0-465d-9a6d-8ae866241900" />

The maximum resultant displacement remained **0.1398 mm** at the displayed precision.

| **Result** | **Coarse Mesh** | **Medium Mesh** |
| :--- | :--- | :--- |
| Maximum von Mises Stress | 8.365 MPa | 8.167 MPa |
| Maximum Resultant Displacement | 0.1398 mm | 0.1398 mm |
| Stress Change | — | 2.37% |
| Displacement Change | — | No change at displayed precision |

<img width="350" height="143" alt="18_Side_bar_Converges" src="https://github.com/user-attachments/assets/4d749039-09ed-4a2e-9269-75cf30c6edf6" />

The maximum stress changed by **2.37%**, while displacement stayed the same at the displayed precision. We completed one refinement from coarse to medium mesh. A second refinement has not been included.

### Factor of Safety

Using the displayed yield strength of **275 MPa** and refined maximum stress of **8.167 MPa** gives a minimum factor of safety of approximately **33.67**. This exceeds the required value of **4** for the yielding check.

| **Final Result** | **Value** |
| :--- | :--- |
| Maximum von Mises Stress | 8.167 MPa |
| Critical Stress Region | Near the fixed base |
| Maximum Resultant Displacement | 0.1398 mm |
| Maximum Displacement Region | Near the top |
| Calculated Minimum Factor of Safety | 33.67 |
| Required Factor of Safety | 4 |

### Load Path and Proposed Improvement

The axial load passes down the upright toward the base. The transverse load bends the member, creating the highest bending demand near the fixed support. The plots primarily show bending; twisting was not separately measured.

We proposed adding transverse bracing to reduce lateral movement and improve frame stiffness. A lighter section could then be considered, but its displacement and strength would need to be checked again.

<img width="797" height="65" alt="19_FoS_and_Optimization" src="https://github.com/user-attachments/assets/6d5c9300-ed8e-490f-b00a-f3d73af1d121" />

We have not run an FEA with the added bracing, so its effect on displacement and the maximum-stress location is not yet known.

### Vertical Frame Conclusion

The refined model gives a minimum factor of safety of **33.67** against yielding under the modeled loads and support conditions. The maximum resultant displacement is **0.1398 mm**, so stiffness remains important even though the calculated stress is low. We proposed transverse bracing to reduce this movement.

## Floating Bearing Mount — Bryan

We designed the mount as a square bronze plate with a centered bearing bore and four mounting holes. The centered bore locates the screw, while the corner holes provide attachment points to the bottom frame.

| **Feature** | **Final Drawing Dimension** |
| :--- | :--- |
| Mount Length and Width | 2.36 × 2.36 in |
| Mount Thickness | 0.31 in, using 5/16 in stock |
| Bearing Bore Limits | Ø0.6256–0.6263 in |
| Bearing Bore Depth | 0.19 in |
| Mounting Hole Pattern | 1.57 × 1.57 in |
| Mounting Fasteners | 4 × M5 |
| Mounting Hole Diameter | 0.217 in through |
| Counterbore Diameter | 0.413 in |
| Counterbore Depth | 0.118 in |

We centered the bearing pocket within the four mounting holes. The plate thickness provides space for the bearing pocket and recessed fastener heads. The sketch below shows our initial layout; the table above follows the final drawing included later in this section.

<img width="1189" height="969" alt="image" src="https://github.com/user-attachments/assets/ab93dedb-92a6-4a3f-b215-7d151db79b1e" />

### RC3 Fit and Alignment

We selected an RC3 precision running fit to provide clearance for rotation while limiting sideways movement of the screw end. The bore limits are **0.6256–0.6263 in**.

For a shaft-basis RC3 fit at this nominal size, the corresponding smooth shaft limits are **0.6246–0.6250 in**. Together, these limits provide **0.0006–0.0017 in of diametral clearance**.

The bearing bore must align with the screw axis established by the upper support. The lower support must also allow axial movement so the screw does not become trapped between two axially fixed supports.

### Surface Speed and Material Check

We used the maximum screw speed to determine the sliding speed at the bearing surface. The calculated surface speed is approximately **2.58 ft/min**, below the **1,500 ft/min limit recorded in the notes**.

The pressure and PV calculations still need to be revised before confirming the bronze selection. The handwritten pressure calculation uses the circular shaft-end area. A radial journal-bearing check requires the radial bearing load and the projected contact area based on shaft diameter and engagement length.

The **1,000 N specimen load per screw** is not automatically the radial load carried by this floating support.

### CAD Model

We modeled the bronze plate with a central bearing pocket and four counterbored mounting holes.

<img width="1044" height="928" alt="image" src="https://github.com/user-attachments/assets/2bab82c9-5c73-44d8-af3d-6da8f8a0d2ba" />

The counterbores recess the fastener heads, while the central pocket supports the screw end. The assembly must leave clearance beneath the shaft end so the blind pocket does not unintentionally carry axial thrust.

### Floating Bearing Mount Conclusion

The final drawing defines the bearing bore, mounting-hole pattern, and counterbores. The RC3 fit requires a smooth mating shaft within the stated limits. The radial bearing load and pressure check still need to be confirmed.

## Bill of Materials and Labor Cost — Grant

We combined the components from A10 and A11 into one BOM. The updated quantities include two motors, two motor mounts, and two fabricated couplers. We also included the aluminum stock for the crosshead.

| **Quantity** | **Name** | **Cost/Item** | **Cost** | **Purchase Link** |
| :--- | :--- | ---: | ---: | :--- |
| 4 | 80 × 40 mm T-Slot Aluminum Extrusion, 2 ft | $51.82 | $207.28 | [5537T112](https://www.mcmaster.com/5537T112/) |
| 8 | 40-Series Flush 90° Corner Plates | $20.18 | $161.44 | [3136N924](https://www.mcmaster.com/3136N924/) |
| 8 | M5 × 65 mm Socket Head Screws — purchase one 25-pack | $4.10/pack | $4.10 | [91290A270](https://www.mcmaster.com/91290A270/) |
| 8 | M5 Flange Locknuts — purchase one 100-pack | $3.52/pack | $3.52 | [94920A120](https://www.mcmaster.com/94920A120/) |
| 8 | T-Slot Nut and Screw Combinations — purchase two 4-packs | $25.10/pack | $50.20 | [5021N15](https://www.mcmaster.com/5021N15/) |
| 1 stock piece | 932 Bearing Bronze Stock for Floating Bearing Mounts | $187.45 | $187.45 | [8234K22](https://www.mcmaster.com/8234K22/) |
| 2 | Custom Motor Couplers — Fabricated | TBD | TBD | — |
| 2 | NEMA 23 Motor Mounting Brackets | $5.75 | $11.50 | [RobotShop](https://www.robotshop.com/products/stepper-motor-mounting-bracket-nema-23) |
| 2 | NEMA 23 Geared Stepper Motors, 10:1 | $40.05 | $80.10 | [STEPPERONLINE](https://www.omc-stepperonline.com/nema-23-stepper-motor-l-76mm-gear-ratio-10-1-mg-series-planetary-gearbox-23hs30-2904s-mg10) |
| 2 | ACME Lead Screws, 5/8"-8, 36 in Long | $102.38 | $204.76 | [97014A320](https://www.mcmaster.com/97014A320/) |
| 2 | Bronze ACME Flange Nuts, 5/8"-8 | $138.20 | $276.40 | [95120A119](https://www.mcmaster.com/95120A119/) |
| 1 pack of 10 | Socket Head Screws, #6-32 × 3/4 in | $4.41/pack | $4.41 | [92200A151](https://www.mcmaster.com/92200A151/) |
| 1 | 6061 Aluminum Crosshead Stock, 1.5 × 2 × 12 in | $32.25 | $32.25 | [Grainger 2EZZ5](https://www.grainger.com/product/Aluminum-Flat-Bar-Stock-6061-2EZZ5) |
| | **Priced Materials and Components Subtotal** | | **$1,223.41** | |

The hardware costs include the complete packs that must be purchased. The bronze stock will be used to machine the floating bearing mounts, while the aluminum stock will be used for the crosshead. The two fabricated couplers remain unpriced and are excluded from the subtotal.

### Design Cost

We estimated **36 combined team hours**, split evenly among the three group members. Using the assignment's required rate of **$35 per hour**, each member contributes **$420.00** in design labor. This gives a total design cost of **$1,260.00**.

| **Person** | **Hours Worked** | **Cost/Hour** | **Labor Cost** |
| :--- | ---: | ---: | ---: |
| Grant | 12 | $35.00 | $420.00 |
| Ethan | 12 | $35.00 | $420.00 |
| Bryan | 12 | $35.00 | $420.00 |
| **Total** | **36** | | **$1,260.00** |

### Total Project Cost

| **Category** | **Cost** |
| :--- | ---: |
| Priced Materials and Components | $1,223.41 |
| Design Labor | $1,260.00 |
| **Total Priced Project Cost** | **$2,483.41** |

The current priced project cost is **$2,483.41**, including the listed materials, components, and design labor. This remains a subtotal because it does not yet include the cost of manufacturing the two custom couplers.

## Engineering Drawings — Bryan

We created drawings showing the dimensions, materials, and tolerances for our designed parts. We included section and detail views where needed to show features that are harder to see in the main views.

### Crosshead Drawing

<img width="1001" height="772" alt="Screenshot 2026-11-18 233838" src="https://github.com/user-attachments/assets/6da2bc11-7cdb-469f-af71-0e556f65beb7" />

We included the crosshead drawing from A10 to show how it connects to the lead screw nuts. The drawing shows the **10 in overall length**, **2 in width**, and **8 in spacing between the screw locations**. The section view shows the internal pocket geometry, while Detail A identifies the nut opening and threaded mounting holes. The nut-opening tolerance controls how the flange nut fits into the crosshead.

### Floating Bearing Mount Drawing

<img width="1000" height="772" alt="Screenshot 2026-11-18 233855" src="https://github.com/user-attachments/assets/6723053b-f3c0-4f3d-9b78-0cbced74c30a" />

The floating bearing drawing shows the center bearing pocket, four mounting holes, and counterbores. The mounting holes are located on a **1.57 × 1.57 in pattern**. The center bore has a separate tolerance for the intended RC3 fit, while the side view shows the plate thickness and pocket depths. These dimensions define the bearing pocket and mounting holes used to attach the bronze plate to the bottom frame.

### Motor Mount Drawing

<img width="997" height="772" alt="Screenshot 2026-11-18 233912" src="https://github.com/user-attachments/assets/9a49c633-3a31-48c6-89a7-92ea199f1e39" />

We created the motor mount drawing to show the four mounting holes, center shaft opening, and recess for the gearbox locating boss. The side view identifies the selected **0.25 in plate thickness** and recess depth. These features position the plate against the gearbox while leaving the output shaft accessible for the coupler.

### Top Frame Member Drawing

<img width="1002" height="775" alt="Screenshot 2026-11-18 233930" src="https://github.com/user-attachments/assets/210e7f20-0b79-4a62-ac1b-1dd662c23da8" />

The top bar drawing shows the **13.6 in member length**, two shaft openings, and eight motor mounting holes. The end view shows the extrusion profile, while the isometric view shows how the openings are positioned along the member. The drawing shows where the purchased extrusion needs to be machined for the motor assemblies.

## Final Assembly — Bryan

After modeling the components, we assembled the frame, motors, mounting plates, couplers, lead screws, crosshead, and floating bearing mounts in CAD. This allowed us to review how the parts fit together and where they connect.

<img width="1120" height="867" alt="Screenshot 2026-11-18 233958" src="https://github.com/user-attachments/assets/730b62d7-d0ce-4a1d-a265-08a1eea981c1" />

The assembly drawing provides an overall isometric view of the tensile tester. The motors are positioned above the top frame member, with one motor driving each lead screw. The crosshead spans the two screws, and the floating bearing mounts support their lower ends.

<img width="859" height="1141" alt="image" src="https://github.com/user-attachments/assets/8410a8e1-baaf-4554-b05e-a3be571de754" />

The shaded view shows the complete frame and the crosshead between the vertical supports. The corner plates connect the horizontal and vertical frame members, while the extended base members support the assembly.

<img width="1224" height="958" alt="image" src="https://github.com/user-attachments/assets/31138aac-b2cb-47aa-828c-1db09767fe1d" />

We used a transparent view to show the shaft and coupler connections inside the top frame member. This makes the motor mounting arrangement and screw alignment easier to see. It also shows the four-fastener connection at each motor location.

## Lessons Learned — Ethan

Throughout this assignment, we learned how to organize our work around each other's schedules and the amount of work each person could take on. We divided tasks based on our strengths in calculations, CAD, simulation, and documentation. This helped us make progress while balancing our other responsibilities. We also learned that dividing the work requires communication because each section depends on decisions made in the others. Teamwork was important in connecting our individual contributions into one design.

The mount and coupler calculations helped us choose dimensions based on the material strength. We then used CAD to show how the parts fit together. We learned that making a part strong enough is only one part of the design. The mounting holes, shafts, and connecting surfaces also need to line up when everything is assembled.

One mistake we made repeatedly was updating the BOM without updating every quantity and total connected to it. As we combined A10 and A11, some entries still listed one motor or mount even though our assembly required two, and earlier totals remained after we added components. We corrected the listed quantities, checked the pack costs, and recalculated the material and labor totals. This taught us to keep one shared BOM and review the complete cost summary whenever the design changes.

Through FEA, we learned how fixtures, load locations, and mesh refinement affect the results. Comparing mesh runs helped us judge whether the reported stresses and displacements were stable. The vertical frame results also showed that a high factor of safety does not necessarily mean a part is stiff enough, which led us to consider additional transverse bracing.

The assignment required approximately **36 combined team hours**, including calculations, CAD modeling, FEA, coordination, and documentation.

## Resources

[CAD FILES](https://drive.google.com/drive/folders/1u-TWogEifa_BrdLtgf8Pgp2fLFRhht96)

[Machinery’s Handbook](https://www.tfgusa.com/wp-content/uploads/2023/11/Machinerys-Handbook.pdf)

[STEPPERONLINE — Selected Motor](https://www.omc-stepperonline.com/nema-23-stepper-motor-l-76mm-gear-ratio-10-1-mg-series-planetary-gearbox-23hs30-2904s-mg10)

[Motor Specifications and Drawing](https://files.omc-stepperonline.com/23HS30-2904S-MG10.pdf)

[Motor Torque–Speed Curve and Test Conditions](https://www.skysmotor.com/images/upload/File/23HS30-2904S_Torque_Curve.pdf)

[McMaster 5537T112 — Frame Extrusion](https://www.mcmaster.com/5537T112/)

[McMaster 3136N924 — Corner Plates](https://www.mcmaster.com/3136N924/)

[McMaster 91290A270 — M5 Screws](https://www.mcmaster.com/91290A270/)

[McMaster 94920A120 — M5 Locknuts](https://www.mcmaster.com/94920A120/)

[McMaster 5021N15 — T-Slot Hardware](https://www.mcmaster.com/5021N15/)

[McMaster 8234K22 — Bronze Stock](https://www.mcmaster.com/8234K22/)

[RobotShop — Motor Bracket](https://www.robotshop.com/products/stepper-motor-mounting-bracket-nema-23)

[National Bronze — Bearing Design Guide](https://www.nationalbronze.com/catalog.pdf)
