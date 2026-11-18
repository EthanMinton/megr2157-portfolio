# A11 – Motor Selection

## Objective


## Motor Selection — Grant

### Knowns and Unknowns

The goal of this section was to select a motor that could turn each lead screw while meeting the tensile load and crosshead speed requirements. We used the results from A10 as our starting point. The total 2,000 N load is assumed to be centered between the two screws, giving a load of 1,000 N per screw.

We selected two identical motor and gearbox assemblies, with one assembly driving each lead screw. The torque and power requirements below therefore apply to one screw and its motor.

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


The calculation above gives a required design output torque of **6.52 N·m per assembly**. This is the torque required at the shaft connected to the lead screw. Since the original torque represents one screw, this requirement also applies to one screw and its motor. The safety factor is already included in this result.

### Required Power

We calculated the mechanical power using the torque requirement and the maximum screw speed from A10. We used the maximum speed because it requires the greatest mechanical power when the torque remains the same.

<img width="897" height="315" alt="image" src="https://github.com/user-attachments/assets/b80213b0-74ed-4a3b-9472-71cb0636b9c9" />

The estimated operating power is **2.69 W per screw**, while the required design power is **10.75 W per screw** at the maximum speed. These values describe mechanical power at the gearbox output. Electrical input power would be higher because of losses in the motor and gearbox.

### Motor Type and Selection

We selected the **23HS30-2904S-MG10**, a NEMA 23 bipolar stepper motor with a 10:1 planetary gearbox. A stepper motor fits this application because it moves in small increments, which is useful for slowly moving the crosshead during a tensile test.

The gearbox reduces the output speed and increases the available output torque. This helps match the motor to the low screw speed and torque requirements carried forward from A10.

<img width="2253" height="1251" alt="image" src="https://github.com/user-attachments/assets/35b51ef6-f612-46e2-a42a-f1bfa8e64e37" />

The screenshot above identifies the selected motor assembly. Two assemblies are included so that each lead screw has its own motor. The keyed output shaft will connect to the coupler, while the front mounting interface will be used to design the motor bracket.

<img width="1817" height="1200" alt="image" src="https://github.com/user-attachments/assets/bea1f16a-c630-469a-b6b0-62d4cc7f84f2" />

The 90% efficiency applies to the gearbox. We used this value when determining the torque required from the motor rotor. It does not include the motor's electrical losses, so it does not represent the overall efficiency of the complete assembly.

### Motor Speed Verification

After selecting the motor, we used its 10:1 gearbox ratio to determine the rotor speed needed to achieve the screw speed calculated in A10. The motor rotor turns ten times for every one revolution of the gearbox output shaft.

<img width="897" height="265" alt="image" src="https://github.com/user-attachments/assets/e323affc-acf5-4b81-8caf-87f437496ff5" />

The calculation above gives a required motor rotor speed of **3.15–157.5 RPM**. This corresponds to a gearbox output and screw speed of **0.315–15.75 RPM**, producing the required crosshead movement of 1–50 mm/min.

### Torque Output Verification

We used the selected gearbox ratio and efficiency to determine the motor rotor torque needed to produce our required output torque. The gearbox increases torque through its reduction ratio, while its efficiency accounts for mechanical losses.

<img width="887" height="277" alt="image" src="https://github.com/user-attachments/assets/3495ee8a-68f7-4cc3-beb8-ded13b3758f9" />

The calculation above shows the motor rotor must provide approximately **0.725 N·m** to deliver the required **6.52 N·m** at the gearbox output. The safety factor is already included in this requirement.

This establishes the motor-side torque requirement. We then need to compare the required torque with the available running torque at the corresponding speed.

### Torque–Speed Curve Verification

We used the torque–speed curve to check whether the selected assembly could provide enough torque while rotating. This matters because a stepper motor's available torque changes with speed. Holding torque alone would not establish whether the motor could turn the lead screw under load.

<img width="1747" height="805" alt="image" src="https://github.com/user-attachments/assets/6f712d57-54c1-4bf0-9d94-0b51225dd8b3" />

The torque–speed curve shows approximately **13.28 N·m of pull-out torque at 15.7 output RPM**, which is close to our maximum required screw speed of 15.75 RPM. This exceeds the required design torque of **6.52 N·m**, which already includes the safety factor of 4.

Since the curve shows gearbox output torque, we compared it directly with our required output torque. The available torque also remains above our requirement at the lower speeds shown within the operating range. This supports our motor selection near the maximum required speed.

### Motor Selection Conclusion

We selected the 23HS30-2904S-MG10 as the motor candidate for each lead screw based on the calculated requirements and supplied torque–speed curve. The displayed running torque near the maximum required speed exceeds our design requirement, and the required torque is below the lower listed gearbox limit.

The remaining verification items are the curve's supply voltage and current conditions, performance down to 0.315 output RPM, and confirmation of the applicable gearbox torque rating. The supplied graph does not extend to the lowest required output speed.


| **Parameter** | **Value** |
| :--- | :--- |
| Selected Motor | 23HS30-2904S-MG10 |
| Motor Type | NEMA 23 Bipolar Geared Stepper |
| Quantity | 2 — one per lead screw |
| Gear Ratio | 10:1 |
| Gearbox Efficiency | 90% |
| Rated Current | 2.9 A/phase |
| Driver Supply Voltage | To be confirmed from torque-curve test conditions |
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

We used the manufacturer drawing to locate the four mounting holes around the gearbox output shaft. The holes form a 47.14 × 47.14 mm square pattern and have a diameter of 5.2 mm. We selected M5 bolts to connect the motor to the mounting plate.

<img width="805" height="797" alt="image" src="https://github.com/user-attachments/assets/be62c0b4-3570-47c4-acbe-86d612b2a5f4" />

<img width="2260" height="881" alt="image" src="https://github.com/user-attachments/assets/7b899ee5-0c09-4292-832c-d1be898a770f" />

The drawing establishes the motor-side mounting dimensions. The bracket also needs a center opening that accommodates the gearbox's locating boss and provides access to the shaft and coupler. Keeping these features centered on the mounting pattern helps maintain alignment with the lead screw.

### Free-Body Diagram

We modeled the motor torque as being resisted equally by the four mounting bolts. Each bolt applies a tangential reaction at the same distance from the shaft center. These reactions resist rotation of the motor housing.

<img width="1114" height="428" alt="image" src="https://github.com/user-attachments/assets/574f0bcd-f694-40e4-a8e7-0147e8896e7d" />


The diagram above shows how the torque is distributed across the bolt pattern. This analysis assumes the four bolts share the torque equally and resist it through bearing contact at the holes.

### Bearing Stress and Thickness Model

We used the force at each bolt to calculate bearing stress in the aluminum plate. The bearing area depends on the plate thickness and bolt diameter. Increasing the thickness increases this area and reduces the bearing stress.

We applied the safety factor of 4 to the assumed material yield strength to establish the allowable stress.

<img width="1048" height="982" alt="image" src="https://github.com/user-attachments/assets/e2f4b127-9e3c-401e-a8f9-fcf35786c74c" />


The derivation above gives the minimum plate thickness needed for this bearing-stress check. The operating torque is used to calculate the bolt force, and the safety factor is applied through the allowable stress.

### Numerical Calculations

We first determined the distance from the shaft center to each bolt using the square mounting pattern. This gave a bolt radius of approximately 33.33 mm. We then used the operating torque to calculate the force at each bolt.

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

The selected 6.35 mm aluminum plate exceeds the minimum thickness required by the motor-hole bearing-stress calculation. The motor mounting pattern is based on the manufacturer drawing to maintain alignment between the output shaft and lead screw.

The completed bracket design must also show its four-hole connection to the top of the frame, access for assembly and maintenance, and how it resists bending and reaction loads.


### CAD Model Aluminum Plate

We modeled the motor mounting plate using the selected thickness of **6.35 mm** and the mounting dimensions from the manufacturer's drawing. The plate includes four mounting holes, a center opening for the output shaft, and a circular recess to accommodate the gearbox's locating boss.

<img width="1546" height="988" alt="image" src="https://github.com/user-attachments/assets/fd12ba95-bdaa-4d2d-ac7c-391dc01f1649" />

The four holes follow the motor's **47.14 × 47.14 mm mounting pattern**. The center features are aligned with this pattern so the plate can sit against the gearbox mounting face while allowing the output shaft to extend through it.

We then assembled the plate to the motor in CAD, aligning the center features with the gearbox and matching the mounting holes.

<img width="2030" height="1212" alt="image" src="https://github.com/user-attachments/assets/242dbed3-3fae-4dd7-8b33-cbc9b58aaf72" />

<img width="2168" height="1074" alt="image" src="https://github.com/user-attachments/assets/0e48cc42-3724-4e00-9049-229ca62c8225" />


The assembly view shows how the plate fits against the selected motor and leaves the output shaft exposed for the coupler connection. This establishes the motor-side mounting arrangement before integrating the mount with the tester frame.

## 3. Coupler Design

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

The opposing torques shown in the sketch represent the torque transmitted through the coupler. We selected a starting outer diameter of 30 mm and estimated the engagement depth at each end. These dimensions established the initial geometry for the stress calculation and CAD model.

### Torsional Stress and Diameter Check

We modeled the coupler as a hollow circular section and used the larger internal diameter for the torsion calculation. This represents the thinner wall section of the proposed coupler.

We used the assumed steel yield strength to determine the shear yield strength, then compared this limit with the calculated shear stress. Since the design torque already includes the safety factor, we did not apply it a second time.

<img width="791" height="552" alt="image" src="https://github.com/user-attachments/assets/f2fe860a-12d2-4262-8de2-c927366ac597" />


The calculated shear stress is approximately **1.37 MPa**, below the **110 MPa shear yield strength** used in the analysis. The minimum outer diameter is approximately **17.15 mm**, so the selected **30 mm outer diameter** satisfies this nominal torsional-stress check.

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

The motor-side bore accommodates the output shaft, while the keyway provides a location for the key to transfer torque between the shaft and coupler.

<img width="1093" height="565" alt="image" src="https://github.com/user-attachments/assets/3e3d7bc9-217f-4594-98a2-232283f4b3d7" />

We modeled the key as a separate component so it could be included in the assembly between the motor shaft and coupler.

<img width="1113" height="640" alt="image" src="https://github.com/user-attachments/assets/eafb00e0-758c-4248-a7b1-31ee4d64a647" />

The threaded end provides the connection to the lead screw. Its thread specification must match the selected 5/8"-8 right-hand ACME screw.

### Motor and Coupler Assembly

We positioned the coupler on the gearbox output shaft and aligned the key with the shaft and coupler keyways.

<img width="1453" height="796" alt="image" src="https://github.com/user-attachments/assets/a316f82f-3839-4b3a-b992-d12c32353795" />

The transparent view shows how the connection features fit together inside the coupler. It also allows the engagement and coupler position relative to the motor mounting plate to be reviewed.

<img width="1599" height="975" alt="image" src="https://github.com/user-attachments/assets/c455c77b-2eec-494d-b96f-c91d5d863505" />

The completed view shows the coupler extending from the motor assembly, with the threaded opening available for the lead screw connection.

### Coupler Design Conclusion

The selected 30 mm outer diameter exceeds the calculated minimum diameter of approximately 17.15 mm. The nominal torsional shear stress is also below the shear yield strength used in the analysis. This supports the coupler body dimensions for the applied design torque.

### Resources

- [Selected Motor — STEPPERONLINE](https://www.omc-stepperonline.com/nema-23-stepper-motor-l-76mm-gear-ratio-10-1-mg-series-planetary-gearbox-23hs30-2904s-mg10)
- [Manufacturer Specifications and Dimension Drawing](https://files.omc-stepperonline.com/23HS30-2904S-MG10.pdf)
