# A11 – Motor Selection

## Objective


## 1. Motor Selection — Grant

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


### Resources

- [Selected Motor — STEPPERONLINE](https://www.omc-stepperonline.com/nema-23-stepper-motor-l-76mm-gear-ratio-10-1-mg-series-planetary-gearbox-23hs30-2904s-mg10)
- [Manufacturer Specifications and Dimension Drawing](https://files.omc-stepperonline.com/23HS30-2904S-MG10.pdf)
