# A10 – Lead Screw Translating System

## Objective


## Leadscrew Selection - E

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

## Bill of Materials

| Item Number | Quantity | Name | Cost/Item | Cost | Purchase Link |
|---|---|---|---|---|---|
| 1 | 2 | Acme Lead Screw, 5/8"-8, 36" Long | $102.38 | $204.76 | [97014A320](https://www.mcmaster.com/97014A320/) |
| 2 | 2 | Bronze Acme Flange Nut, 5/8"-8 | $138.20 | $276.40 | [95120A119](https://www.mcmaster.com/95120A119/) |
| 3 | TBD packs | Socket Head Screw, 6-32, 3/4" Long | $4.41 per pack of 10 | TBD | [92200A151](https://www.mcmaster.com/92200A151/) |
| | | | **Total Cost** | **TBD** | |


## Parametric Modeling and Assembly - B

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

## Lessons Learned

### Ethan — Lead Screw Calculations

I completed the lead screw calculations and learned how the screw’s lead determines the rotational speed needed to move the crosshead. For the selected screw, each revolution moves the nut 0.125 inches. Using this value, I calculated the speed range needed to meet the required crosshead movement. I also learned how to use the inclined plane model from class to solve for the force needed to overcome the axial load and friction. Multiplying that force by the pitch radius gave the required torque. Working through the force balances made the torque equation easier to understand. Another thing I learned was to use the thread root diameter when calculating axial stress because this is the smallest section carrying the load.

### Grant — Second Calculation Section

I completed the second math section and learned how to connect the free-body diagram to the equations used to size the components. Solving symbolically first helped me understand how changing the load, material strength, or dimensions would affect the result. I also learned how to apply the safety factor of 4 by reducing the allowable stress used in the calculations. The selected hardware also affected the design because the calculated dimensions needed to provide space for the nut and flange mounting features. This helped me understand why the calculations and part selection needed to be considered together.

### Bryan — CAD Modeling and Assembly

I completed the CAD modeling and assembly and learned how to create a screw mate in SolidWorks. Setting the travel per revolution connected the rotation of the lead screw to the linear movement of the nut and crosshead. I also learned how to combine mates that kept the components aligned while allowing the intended movement. The screw mate required checking the direction of travel and the amount of movement produced by each revolution. Working with downloaded components also taught me to check the thread size, thread direction, and number of thread starts when selecting compatible parts.

The project took approximately 20 combined hours to complete.

