# A10 – Lead Screw Translating System

## Objective


## Leadscrew Selection - Ethan Minton

### Minimum Diameter

For part 1, I used axial stress to calculate the minimum lead screw diameter. I assumed the centered 2 kN load was shared equally between the two separate screws found on each side of the model shown, giving 1,000 N per screw. Using a reference yield strength of 205 MPa sourced from Atimaterials to find a general value for Stainless Steels and then using the required safety factor of 4, I solved symbolically for the diameter before plugging in the values. This gave a minimum thread root diameter of 0.196 inches. The root diameter is used because it is the smallest section carrying the axial load.


<img width="785" height="297" alt="Screenshot 2026-11-10 233445" src="https://github.com/user-attachments/assets/8085e7e4-f46d-44cb-93fc-f2e134ed09bc" />

<img width="1380" height="642" alt="Screenshot 2026-11-10 233513" src="https://github.com/user-attachments/assets/8fe7a00c-178e-4d29-8371-bab71aa17e24" />

https://www.atimaterials.com/Products/Pages/ati-316.aspx

### Rotational Speed

For part 2, I calculated the rotational speed needed to move the crosshead between 1 and 50 mm/min. The selected screw has a lead of 0.125 inches per revolution, which converts to 3.175 mm/rev. I treated the screw as rotating in place while the nut was prevented from rotating, allowing the nut and crosshead to move along the screw. Starting with (v=Ln), I solved symbolically for (n=v/L), then substituted the minimum and maximum linear speeds. This gave a required speed range of 0.315–15.75 rpm for each screw.

<img width="1305" height="560" alt="Screenshot 2026-11-10 233934" src="https://github.com/user-attachments/assets/e8d629b8-1731-4511-861b-747561bdf1ec" />

### Max Torque 

For part 3, I used the inclined plane method from class to calculate the torque needed to turn each lead screw. I assumed the centered 2 kN specimen load was shared equally, giving 1,000 N per screw. I used the basic Acme thread geometry to estimate the pitch radius because an exact pitch diameter was not listed on the product page. Since a friction coefficient for the selected screw and bronze nut was not provided, I back-calculated an effective coefficient of 0.15434 from Roton’s published torque ratio. I assumed this could represent the McMaster combination because both use a 5/8–8 Acme screw with a bronze nut. After solving the force balances symbolically, I substituted the values and multiplied the driving force by the pitch radius. This gave an estimated raising torque of 1.63 N·m per screw at steady speed under the specified specimen load.

<img width="1365" height="697" alt="Screenshot 2026-11-10 234209" src="https://github.com/user-attachments/assets/b06e9238-0c3f-4fd7-9b5b-bf6e61c87437" />

<img width="1628" height="565" alt="Screenshot 2026-11-10 234250" src="https://github.com/user-attachments/assets/4908238c-c82d-4f40-bc97-fa5ea1d6e06b" />

https://www.roton.com/products/acme-lead-screws-nuts/engineering-data/

## Nut and Flange Design — Grant Parker

I selected the [McMaster 95120A119 flange nut](https://www.mcmaster.com/95120A119/), made from 932 bearing bronze with 5/8–8 right-hand Acme threads. The nut has a listed height of 1.25 inches, a body diameter of 0.875 inches, and a flange diameter of 1.50 inches. These dimensions were used to plan the mounting features on the crosshead.

### Knowns and Unknowns

| Known | Value |
|---|---|
| Total specimen load | 2,000 N |
| Load per nut, assuming equal sharing | 1,000 N = 224.81 lbf |
| Assumed effective engagement length, L_e | 1.25 in |
| Thread pitch, p | 0.125 in |
| Internal thread root diameter, d_r | 0.645 in |
| Assumed nut yield strength, S_y | 14,000 psi |
| Required safety factor | 4 |

The unknowns were the number of engaged threads, thread bending stress, allowable stress, and calculated safety factor.

I assumed the centered load was shared equally between the two nuts. The FBD represents the force transferred between the screw threads and the crosshead through one nut.

<img width="461" height="350" alt="Nut free-body diagram" src="https://github.com/user-attachments/assets/3396a6a6-e738-4068-9653-57dc6e0ed011" />

I assumed the full 1.25-inch nut height provided effective thread engagement and that the engaged threads shared the load equally. This simplified the initial thread calculation. Dividing the engagement length by the pitch gave 10 engaged threads.

The 0.645-inch value came from the minimum internal major diameter in Dependable Acme’s 5/8–8 Class 2G thread table. For the nut, this is the diameter at the internal thread roots.

Since the McMaster listing did not provide yield strength, I used 14,000 psi as a preliminary material estimate. St. Paul Foundry lists this minimum value for as-cast C93200 bronze. Applying it to the purchased nut remains an assumption because its exact material condition was not confirmed.

<img width="750" height="377" alt="Thread engagement and thread bending calculations" src="https://github.com/user-attachments/assets/08cc9528-a58e-495a-906a-ce6b0ee97578" />

The estimated bending stress was 533 psi. Dividing the assumed yield strength by the required safety factor gave an allowable stress of 3,500 psi. The calculated safety factor was approximately 26.3, so the nut passed this preliminary thread-bending check under the stated assumptions.

## Crosshead Design — Grant Parker

### Dimension Selection

I used the selected nut’s 1.50-inch flange diameter to help determine the crosshead dimensions. I selected a width of 2 inches, leaving 0.25 inches between each centered flange and the side edges. With an 8-inch spacing between the screws and a 10-inch overall length, each screw center was 1 inch from the nearest end. This also left 0.25 inches between the flange and the end of the crosshead. These dimensions were design choices based on the researched hardware dimensions.

I modeled the crosshead as a simply supported beam with the 2,000 N specimen load acting at the center. The support span was 8 inches, giving equal support reactions of 1,000 N, or 224.81 lbf. I used an initial rectangular cross section of 2 inches wide by 1 inch thick.

<img width="743" height="253" alt="Crosshead free-body diagram" src="https://github.com/user-attachments/assets/821e25fd-067b-48cd-886d-afcc90f1f6c3" />

### Strength Analysis

<img width="323" height="335" alt="Strength analysis knowns" src="https://github.com/user-attachments/assets/ddf1148f-ead4-48d4-b19b-e38467390bcf" />

<img width="278" height="337" alt="Strength analysis unknowns" src="https://github.com/user-attachments/assets/0fbc593c-b251-45f2-806a-b86c15c69ed7" />

I calculated the maximum bending moment and area moment of inertia, then substituted these into the bending stress equation. This gave a maximum bending stress of approximately 2,698 psi. Applying the required safety factor of 4 gave a minimum required yield strength of 10,791 psi.

I selected 6061-T6 aluminum and used a reference yield strength of 40,000 psi. Kaiser Aluminum lists this typical yield strength and an elastic modulus of 10 million psi for T6/T651 material. Using these reference properties gave a preliminary safety factor of approximately 14.83.

<img width="934" height="922" alt="Crosshead strength calculations" src="https://github.com/user-attachments/assets/ff84e66b-6c34-4854-832b-28d2a79972ec" />

### Deflection Analysis

<img width="465" height="342" alt="Deflection analysis knowns" src="https://github.com/user-attachments/assets/5cacd7b4-f086-4fa1-8ca7-0b0f79f2a73b" />

<img width="297" height="332" alt="Deflection analysis unknowns" src="https://github.com/user-attachments/assets/84258154-f4cf-471e-bd1b-71eb3938ae00" />

I used the same dimensions and loading to check the 0.10 mm deflection requirement. Rearranging the beam deflection equation gave a minimum required elastic modulus of approximately 7.3 × 10⁶ psi. The selected reference modulus of 10 × 10⁶ psi exceeded this requirement.

Using this modulus gave a calculated deflection of 0.002878 inches, or 0.0731 mm. This was approximately 73.1% of the allowable deflection, so the initial dimensions passed the deflection check.

<img width="881" height="699" alt="Crosshead deflection calculations" src="https://github.com/user-attachments/assets/65860c67-d6ba-4686-bd3c-10600402158b" />

These hand calculations treated the crosshead as a solid rectangular beam with ideal supports. The center hole, mounting holes, and attachment details would be evaluated further in the FEA.

### Crosshead Sketch

I included front, top, and side views showing the overall dimensions and mounting arrangement. The sketch connects the dimensions used in the calculations to the SolidWorks model.

<img width="1190" height="916" alt="Crosshead multiview sketch" src="https://github.com/user-attachments/assets/42fc37bb-33da-4859-a434-ecd4525cbfe0" />

## Bill of Materials - Ethan Minton

| Item Number | Quantity | Name | Cost/Item | Cost | Purchase Link |
|---|---|---|---|---|---|
| 1 | 2 | 316 Stainless Steel Acme Lead Screw, 5/8"-8, 36" Long; Cut to 18" | $102.38 | $204.76 | [97014A320](https://www.mcmaster.com/97014A320/) |
| 2 | 2 | 932 Bronze Acme Flange Nut, 5/8"-8 Right-Hand Thread | $138.20 | $276.40 | [95120A119](https://www.mcmaster.com/95120A119/) |
| 3 | 1 pack of 10; 8 used | 18-8 Stainless Steel Socket Head Screw, 6-32 × 3/4" | $4.41 per pack | $4.41 | [92200A151](https://www.mcmaster.com/92200A151/) |
| 4 | 1 stock length | 80 × 40 mm, 40-Series Double T-Slot Aluminum Profile, 10 ft; Assignment Reference Price | $262.23 | $262.23 | [Assignment Frame Profile Resource](https://www.grainger.com/category/material-handling/structural-framing-systems/t-slot-framing-systems/profiles-for-t-slot-framing/metric-profiles-for-t-slot-framing?attrs=Relative+Profile+Weight%7CHeavy~~Series%7C40+Series&filters=attrs) |
| 5 | 12 | 40-Series Two-Hole Gusseted Inside Corner Bracket | $7.73 | $92.76 | [80/20 40-4332](https://8020.net/40-4332.html) |
| 6 | 24 | M8 × 16 mm Button Head Screw and Compatible Slide-In T-Nut Assembly | $1.14 | $27.36 | [80/20 75-3422](https://8020.net/75-3422.html) |
| | | | **Total Estimated Cost of Listed Components** | **$867.92** | |


## Parametric Modeling and Assembly - Bryan Mccanch

### Crosshead Design

I started by creating the tensile tester assembly and adding a new crosshead part.

<img width="185" height="209" alt="1_Assembly Part_Creation" src="https://github.com/user-attachments/assets/d9fa2edb-13d2-4a60-9969-a089aed68789" />

I added global variables for the crosshead dimensions, hole diameter, and hole spacing. This allowed me to control the dimensions and make changes in one place.

<img width="523" height="104" alt="2_Global_vars" src="https://github.com/user-attachments/assets/38dc6d83-4a85-4477-9dba-56a216ca54c9" />

I sketched a rectangle and linked the dimensions to the global variables. The crosshead was set to 10 inches long and 2 inches wide.

<img width="353" height="233" alt="3_CH_Sketch" src="https://github.com/user-attachments/assets/bacab578-8b61-46fe-bac4-47485c269d4c" />

I extruded the rectangle to a thickness of 1 inch using the height variable.

<img width="830" height="362" alt="4_CH_Extrusion" src="https://github.com/user-attachments/assets/957c513a-173c-4391-b43e-c0913a14dbc0" />

I sketched two holes along the centerline and set their centers 8 inches apart. Both hole diameters were linked to the 0.875-inch global variable.

<img width="617" height="227" alt="5_Hole_Sketch" src="https://github.com/user-attachments/assets/f2dde11a-36fe-4e6f-9ba7-9488cc146ba8" />

I cut both holes through the crosshead to create the openings for the lead screw nuts.

<img width="659" height="462" alt="6_Hole_Cut" src="https://github.com/user-attachments/assets/f7661d44-3362-4987-b23b-322f9221830e" />

I used a circular sketch pattern to create four equally spaced bolt locations around the first opening.

<img width="461" height="534" alt="7_Bolthole_sketch" src="https://github.com/user-attachments/assets/f2e590bb-2f9e-4df8-89b3-7af12040adf5" />

I mirrored the bolt locations across the middle of the crosshead. This gave both ends the same mounting pattern.

<img width="691" height="273" alt="8_Bolthole_mirrored" src="https://github.com/user-attachments/assets/450326f0-9964-4c09-88f8-e0810037568c" />

I used Hole Wizard to select #6-32 tapped holes. I set the holes and threads to go through the crosshead.

<img width="184" height="624" alt="9_Holewizard_Details" src="https://github.com/user-attachments/assets/eade1ef6-af2c-450c-8dc7-1b33806b224a" />

I placed the tapped holes at the sketch points around both openings. This created four mounting holes for each nut flange.

<img width="740" height="283" alt="10_bolthole_feature" src="https://github.com/user-attachments/assets/57d6a305-f397-4756-8201-c3c0ddf960a3" />

I assigned 6061-T6 aluminum from the SolidWorks material library to the crosshead.

<img width="614" height="486" alt="11_Material_Assigned" src="https://github.com/user-attachments/assets/4d115857-3c0e-4226-b87a-8e94caf92fbc" />

The finished crosshead has two main openings and eight tapped mounting holes. The part was ready to be used in the tensile tester assembly.

<img width="838" height="583" alt="12_Finished_Part" src="https://github.com/user-attachments/assets/9e5b0795-7872-488c-9e10-64e99c66f49f" />

### Flange Nut Assembly

I started by importing the flange nut CAD model into the assembly. This gave me the nut geometry and threads without having to model them separately.

<img width="371" height="239" alt="1_Imported_Nut" src="https://github.com/user-attachments/assets/54be6891-fd21-4f12-b492-8950da94a42d" />

I used a circular sketch pattern to create four equally spaced bolt locations around the flange. These locations matched the mounting pattern on the crosshead.

<img width="440" height="486" alt="2_Hole_Sketch" src="https://github.com/user-attachments/assets/a2d905b1-f95f-4873-aed7-e21d5e981f37" />

I used Hole Wizard to create four #24 drilled holes through the flange. These holes allow the mounting screws to pass through and thread into the crosshead.

<img width="595" height="476" alt="3_HoleWizard" src="https://github.com/user-attachments/assets/fefab1e4-cd9e-4715-bfeb-c9a022a0ba58" />

I mated the nut to the crosshead with the center openings lined up. The flange sat against the bottom face of the crosshead.

<img width="228" height="286" alt="4_Mated_w_Crosshead" src="https://github.com/user-attachments/assets/a031dda2-7d50-4894-83bf-bedce36a3425" />

I assigned Commercial Bronze, UNS C22000, from the SolidWorks material library to the nut.

<img width="614" height="482" alt="5_Assigned_Matl" src="https://github.com/user-attachments/assets/59e7fd3e-f3d9-4fc5-a193-d734dd541f74" />

I added a second flange nut and mated it to the opening at the other end of the crosshead. Both nuts were now positioned for the lead screws.

<img width="397" height="209" alt="6_Added_2nd_Nut" src="https://github.com/user-attachments/assets/1175218b-9447-451f-909e-fcc1644b2266" />

### Mounting Bolt and Leadscrew Assembly 

I imported the socket head screws and mated them into the mounting holes. I added four screws to each flange to secure both nuts to the crosshead.

<img width="803" height="586" alt="Imported Mated_bolts" src="https://github.com/user-attachments/assets/b395b4b3-f1c2-4659-a0ca-e5b40939753b" />

I imported the lead screw model and created a reference plane 18 inches from the end. This gave me a location to shorten the screw to the selected length.

<img width="614" height="514" alt="1_Imported_LS" src="https://github.com/user-attachments/assets/d7b9420c-54f8-4710-8086-04391bcf8b4f" />

I sketched on the reference plane and used a through-all extruded cut to remove the extra length. This shortened the lead screw model from 36 inches to 18 inches.

<img width="881" height="572" alt="2_Cutting_LS" src="https://github.com/user-attachments/assets/bdbafef0-2863-469e-9184-cb4ab6996111" />

I added the second lead screw and mated both screws to the flange nuts. This positioned the screws parallel to each other and completed this portion of the assembly.

<img width="400" height="422" alt="3_Mated_LS+Final assembly" src="https://github.com/user-attachments/assets/5bba3e83-5ce1-4ff6-8ca4-862240d48aab" />

## Finite Element Analysis — Bryan Mccanch

### FEA Setup

I added a hole at the center of the crosshead to represent the specimen attachment location. This provided a surface for applying the specimen load.

<img width="689" height="347" alt="Center specimen attachment hole" src="https://github.com/user-attachments/assets/63ab500e-9224-44ba-8818-023885bd028c" />

I created a static study named “Initial_Static” in SolidWorks Simulation. This allowed me to evaluate the stresses and displacement under the applied load.

<img width="200" height="527" alt="Creating the static study" src="https://github.com/user-attachments/assets/5d91a088-b814-4f10-a59e-6d05b0d9644c" />

I applied a 2,000 N downward force to the inside surface of the center hole. This represented the load transferred from the specimen into the crosshead.

<img width="587" height="505" alt="Applying the 2000 N specimen load" src="https://github.com/user-attachments/assets/2a5a19df-5465-4fd4-9dcc-43300f5d4f7f" />

## Design 1

### Mesh 1

#### Stress

I ran the initial study using a reported mesh count of 236,650 cells. The maximum von Mises stress was approximately 12,160 psi, with the peak reported at the flange nut threads.

<img width="545" height="548" alt="Mesh1_Stress" src="https://github.com/user-attachments/assets/7eeba02d-2324-4e0e-bebf-6d113fb60188" />

#### Maximum Stress Location

I viewed the underside of the crosshead to locate the stress concentration. The highest stress was concentrated near the nut and lead screw interface, so this area needed closer attention during mesh refinement.

<img width="431" height="376" alt="Mesh1_Max_Stress" src="https://github.com/user-attachments/assets/e4b527cf-56d2-43aa-8831-082be0591384" />


#### Displacement

The maximum resultant displacement was 0.09711 mm near the middle of the crosshead. This was below 0.10 mm and followed the expected pattern of the center moving farther than the supported ends.

<img width="506" height="567" alt="Mesh1_Delf" src="https://github.com/user-attachments/assets/dc30d0f3-e72a-42b6-b1bc-92e5097f76f4" />


### Mesh 2

#### Stress

I refined the mesh, increasing the reported count to 275,946 cells. The maximum stress increased to 21,800 psi and remained at the flange nut threads. This was a 79.28% increase from Mesh 1.

<img width="573" height="576" alt="Mesh2_Stress" src="https://github.com/user-attachments/assets/5b8bc805-9a6b-421d-b28d-8b39f245d768" />

#### Displacement

The maximum resultant displacement was 0.09689 mm near the middle of the crosshead. This changed by approximately 0.23% from Mesh 1, showing that the displacement was much less sensitive to this refinement than the peak stress.

<img width="592" height="565" alt="Mesh2_Defl" src="https://github.com/user-attachments/assets/1d026cd4-6040-4b94-9e59-9c8de690cada" />

### Mesh 3

#### Stress

I refined the mesh again, increasing the reported count to 293,619 cells. The maximum stress increased to 24,140 psi at the same reported location. The increase from Mesh 2 was approximately 10.73%.

<img width="604" height="525" alt="Mesh3_Stress" src="https://github.com/user-attachments/assets/86b5b8da-a125-4a59-9b20-316545b4bc39" />

#### Displacement

The maximum resultant displacement was 0.09711 mm near the middle of the crosshead. This changed by approximately 0.23% from Mesh 2 and remained below 0.10 mm.

<img width="577" height="580" alt="Mesh3_Defl" src="https://github.com/user-attachments/assets/f9d3eaeb-4a1c-4cc9-a0cb-b65ad6969635" />

### Mesh Comparison

| Result | Mesh 1 | Mesh 2 | Mesh 3 |
|---|---|---|---|
| Reported mesh cells | 236,650 | 275,946 | 293,619 |
| Maximum von Mises stress | 12,160 psi | 21,800 psi | 24,140 psi |
| Reported maximum stress location | Flange nut threads | Flange nut threads | Flange nut threads |
| Maximum resultant displacement, URES | 0.09711 mm | 0.09689 mm | 0.09711 mm |
| Maximum displacement location | Middle of crosshead | Middle of crosshead | Middle of crosshead |
| Stress change from previous mesh | — | 79.28% | 10.73% |
| Displacement change from previous mesh | — | 0.23% | 0.23% |
| Estimated nut safety factor using 14,000 psi yield | 1.15 | 0.64 | 0.58 |

### Convergence Discussion

I noticed unusual behavior in the maximum stress near the flange nut threads. The peak was concentrated in a very small area and increased as the mesh was refined, while the maximum displacement stayed nearly constant. Between Mesh 2 and Mesh 3, the stress increased by 10.73%, while the displacement changed by approximately 0.23%.

This localized peak appeared questionable and may be a mesh or contact artifact associated with the modeled thread geometry. A sharp thread root or contact edge could produce a numerical stress singularity. However, the screenshots alone do not confirm this, so the peak should be investigated rather than automatically treated as a realistic stress or ignored.

### Safety Factor

Using the assumed bronze yield strength of 14,000 psi and the Mesh 3 peak stress gave an estimated safety factor of 0.58. This value was controlled by the highly localized stress at the flange nut threads.

Because that peak may be affected by the mesh and contact definitions, I treated this safety factor as preliminary. Further checks of the thread geometry, material assignments, contacts, and local mesh are needed before drawing a final strength conclusion. These results do not yet verify the required safety factor of 4.

### Load Path and Deformation

The specimen load enters through the center hole and bends the crosshead between the two nut connections. The load then transfers through the flange nuts into the lead screws and their supports.

The displayed deformation also shows sideways bending of the lead screws. This needs further review of the support and contact definitions. Crosshead twisting cannot be determined from these views alone; displacement across both sides of the crosshead should be compared.

## Design 2

### Revised Crosshead Geometry

I added two pockets to the crosshead to remove material and reduce mass. I kept solid material around the center attachment hole and the flange nut mounting areas. The pockets also included rounded corners to avoid sharp internal corners.

<img width="384" height="584" alt="Optimized_design" src="https://github.com/user-attachments/assets/3fa6a230-fb2b-4d4d-b59f-1bda5faba0c4" />

### Mesh 1

#### Stress

I ran the revised design using a reported mesh count of 110,830 cells. The maximum von Mises stress was approximately 18,360 psi, with the peak again reported at the flange nut threads.

<img width="477" height="473" alt="Mesh1_Stress (1)" src="https://github.com/user-attachments/assets/d04850a3-8999-4a96-9a89-e51cb3fe2811" />

#### Displacement

The maximum resultant displacement was 0.1444 mm near the middle of the crosshead. This was higher than the 0.09711 mm reported for Design 1, showing a stiffness penalty in the revised model.

<img width="526" height="476" alt="Mesh1_Defl" src="https://github.com/user-attachments/assets/0a50178e-ba86-4889-9bbc-d2b020a61bc9" />

### Mesh 2

#### Stress

I refined the mesh, increasing the reported count to 133,727 cells. The maximum stress increased to 21,560 psi at the flange nut threads. This was a 17.43% increase from Mesh 1.

<img width="493" height="438" alt="Mesh2_Stress (1)" src="https://github.com/user-attachments/assets/d080bcda-4945-4d09-bdcd-fb2893ea841f" />

#### Displacement

The maximum resultant displacement remained approximately 0.1444 mm near the middle of the crosshead. The displayed result changed very little even though the peak stress increased.

<img width="467" height="440" alt="Mesh2_Defl (1)" src="https://github.com/user-attachments/assets/05e9d8d0-7635-4f39-af3c-d05e03808fa2" />

### Mesh 3

#### Stress

I refined the mesh again, increasing the reported count to 142,338 cells. The maximum stress decreased to 15,110 psi, which was approximately 29.92% lower than Mesh 2. The reported maximum remained at the flange nut threads.

<img width="515" height="470" alt="Mesh3_Stress (1)" src="https://github.com/user-attachments/assets/43ab4d8d-38d2-4f9d-93ab-3aa26a313b5a" />

#### Displacement

The maximum resultant displacement remained approximately 0.1444 mm near the middle of the crosshead. The displacement was stable to the precision shown across all three meshes.

<img width="467" height="465" alt="Mesh3_Defl (1)" src="https://github.com/user-attachments/assets/9ae4a40f-9fb3-4902-aaba-fa52bdebecce" />

### Mesh Comparison

| Result | Mesh 1 | Mesh 2 | Mesh 3 |
|---|---|---|---|
| Reported mesh cells | 110,830 | 133,727 | 142,338 |
| Maximum von Mises stress | 18,360 psi | 21,560 psi | 15,110 psi |
| Reported maximum stress location | Flange nut threads | Flange nut threads | Flange nut threads |
| Maximum resultant displacement, URES | 0.1444 mm | 0.1444 mm | 0.1444 mm |
| Maximum displacement location | Middle of crosshead | Middle of crosshead | Middle of crosshead |
| Stress change from previous mesh | — | 17.43% increase | 29.92% decrease |
| Displacement change at displayed precision | — | Approximately 0.00% | Approximately 0.00% |
| Estimated nut safety factor using 14,000 psi yield | 0.76 | 0.65 | 0.93 |

### Flange Nut Stress Concentration and Convergence

I noticed the same unusual stress concentration at the flange nut that appeared in Design 1. The maximum stress was concentrated in a very small region near the threads, while most of the surrounding assembly showed much lower stress.

The isolated peak seemed unrealistic as a measure of the overall crosshead strength. It may be affected by the mesh, thread geometry, or contact definitions. The stress increased between Mesh 1 and Mesh 2, then decreased between Mesh 2 and Mesh 3, while the displacement stayed nearly constant. This showed that the reported peak stress was still sensitive to the mesh.

These results suggest a possible mesh or contact artifact, but they do not prove that the concentration is artificial. Further checks are needed before dismissing the peak or using it as a final strength result.

### Safety Factor

Using the previously assumed bronze yield strength of 14,000 psi gave estimated nut safety factors of 0.76, 0.65, and 0.93. These values were controlled by the localized peak reported at the flange nut threads.

Because the peak stress had not converged and may be affected by the modeled thread contact, I treated these safety factors as preliminary. The results did not verify the required safety factor of 4. The crosshead’s own stress and safety factor also need to be evaluated separately from the nut.

### Comparison with Design 1

| Result Using Mesh 3 | Design 1 | Design 2 |
|---|---|---|
| Maximum reported von Mises stress | 24,140 psi | 15,110 psi |
| Reported maximum stress location | Flange nut threads | Flange nut threads |
| Maximum resultant displacement | 0.09711 mm | 0.1444 mm |
| Estimated nut safety factor using 14,000 psi yield | 0.58 | 0.93 |
| Reported mass | 5.25 lb | 4.32 lb |
| Reported volume | 52.57 in³ | 44.49 in³ |

The revised design reduced the reported mass by 0.93 lb, or approximately 17.7%. The reported volume decreased by 8.08 in³, or approximately 15.4%. This showed that the pockets removed material from the crosshead.

The maximum resultant displacement increased by approximately 48.7%, showing a stiffness penalty in the revised model. Although Design 2 had a lower reported peak stress on Mesh 3, neither design established a converged peak stress. The localized concentration at the flange nut remained questionable and may be affected by the mesh or contact definitions.


### Deflection Requirement

The reported resultant displacement of 0.1444 mm was above the numerical limit of 0.10 mm. However, these plots show URES rather than the vertical displacement component requested in the assignment.

A vertical displacement plot at the grip line is needed before making a final comparison with that requirement. Based on the available results, I could not report Design 2 as meeting all constraints.

### Load Path and Deformation

The load enters through the center attachment hole and travels through the remaining crosshead material to the flange nut connections. It then transfers into the lead screws and their supports.

The displayed deformation shows bending near the middle of the crosshead and sideways bending of the lead screws. The support and contact definitions need further review, and displacement across both sides of the crosshead should be compared to evaluate twisting.

### Final Verification 

The revised FEA predicted a maximum resultant displacement of approximately 0.1444 mm, compared with the required vertical deflection limit of 0.10 mm. I suspected that the simulation setup and thread-contact behavior may have affected the results. 

The low estimated safety factor was controlled primarily by the highly concentrated stress at the flange nut threads. This peak changed considerably with mesh refinement, suggesting that the thread geometry and contact definitions may not accurately represent the actual load sharing. I therefore treated the reported safety factor as preliminary.

In all honesty, the limits seem to be disrupted by the FEA itself, and not how, in actuality, the Lead Screw would perform. This is likely due to how the assembly was exactly set up; with our knowledge being limited to how it should be set up, these issues can slip through the cracks and seemingly would require an entire overhaul of the design. If I were given the opportunity again, I would definitely attempt to reconstruct the assembly in an attempt to avoid this issue of outlier concentration entirely. Unfortunately, these analysis can be extremely finicky which can otherwise turn a extremely support and well build model to have a completely gross outlier concentrations.


### Crosshead Drawing 

<img width="1147" height="892" alt="image" src="https://github.com/user-attachments/assets/7973a283-0d1e-4f38-b049-5f27b04e6da8" />


## Lessons Learned

### Ethan — Lead Screw Calculations

I completed the lead screw calculations and learned how the screw’s lead determines the rotational speed needed to move the crosshead. For the selected screw, each revolution moves the nut 0.125 inches. Using this value, I calculated the speed range needed to meet the required crosshead movement. I also learned how to use the inclined plane model from class to solve for the force needed to overcome the axial load and friction. Multiplying that force by the pitch radius gave the required torque. Working through the force balances made the torque equation easier to understand. Another thing I learned was to use the thread root diameter when calculating axial stress because this is the smallest section carrying the load.

### Grant — Second Calculation Section

I completed the second math section and learned how to connect the free-body diagram to the equations used to size the components. Solving symbolically first helped me understand how changing the load, material strength, or dimensions would affect the result. I also learned how to apply the safety factor of 4 by reducing the allowable stress used in the calculations. The selected hardware also affected the design because the calculated dimensions needed to provide space for the nut and flange mounting features. This helped me understand why the calculations and part selection needed to be considered together.

### Bryan — CAD Modeling and Assembly

I completed the CAD modeling and assembly and learned how to create a screw mate in SolidWorks. Setting the travel per revolution connected the rotation of the lead screw to the linear movement of the nut and crosshead. I also learned how to combine mates that kept the components aligned while allowing the intended movement. The screw mate required checking the direction of travel and the amount of movement produced by each revolution. Working with downloaded components also taught me to check the thread size, thread direction, and number of thread starts when selecting compatible parts.

The project took approximately 30 dedicated hours to complete.

## Resources

[Lead Screw](./Lead_Screw.SLDPRT)

[Flange Nut](./Flange_Nut.SLDPRT)

[Crosshead](./Crosshead.SLDPRT)

[Crosshead Drawing](./Crosshead.SLDDRW)

[2 ft Rail](./2ft_Rail.SLDPRT)

[1 ft Rail](./1ft_Rail.SLDPRT)

[6-32 Mounting Screw](./%236_32_Screw.SLDPRT)

[ATI — 316 Stainless Steel Properties](https://www.atimaterials.com/Products/Pages/ati-316.aspx)

[Roton — Acme Lead Screw Engineering Data](https://www.roton.com/products/acme-lead-screws-nuts/engineering-data/)

[Dependable Acme — Thread Dimensions](https://www.dependableacme.com/internal-and-external-thread-dimensions/)

[St. Paul Foundry — C93200 Bronze Properties](https://www.stpaulfoundry.com/AlloySpecs/alloy_specifications_data_page.aspx?id=C93200)

[Kaiser Aluminum — 6061 Material Properties](https://online.kaiseraluminum.com/depot/PublicProductInformation/Document/1015/Kaiser_Aluminum_6061_Sheet_Coil_and_Plate.pdf)

[Assignment Resource — Grainger Frame Profiles](https://www.grainger.com/category/material-handling/structural-framing-systems/t-slot-framing-systems/profiles-for-t-slot-framing/metric-profiles-for-t-slot-framing?attrs=Relative+Profile+Weight%7CHeavy~~Series%7C40+Series&filters=attrs)

[McMaster — Lead Screw](https://www.mcmaster.com/97014A320/)

[McMaster — Bronze Flange Nut](https://www.mcmaster.com/95120A119/)

[McMaster — Mounting Screw](https://www.mcmaster.com/92200A151/)

