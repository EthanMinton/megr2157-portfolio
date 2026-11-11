# A10 – Lead Screw Translating System

## Objective


## Leadscrew Selection 

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


## Lessons Learned

### Ethan — Lead Screw Calculations

I completed the lead screw calculations and learned how the screw’s lead determines the rotational speed needed to move the crosshead. For the selected screw, each revolution moves the nut 0.125 inches. Using this value, I calculated the speed range needed to meet the required crosshead movement. I also learned how to use the inclined plane model from class to solve for the force needed to overcome the axial load and friction. Multiplying that force by the pitch radius gave the required torque. Working through the force balances made the torque equation easier to understand. Another thing I learned was to use the thread root diameter when calculating axial stress because this is the smallest section carrying the load.

### Grant — Second Calculation Section

I completed the second math section and learned how to connect the free-body diagram to the equations used to size the components. Solving symbolically first helped me understand how changing the load, material strength, or dimensions would affect the result. I also learned how to apply the safety factor of 4 by reducing the allowable stress used in the calculations. The selected hardware also affected the design because the calculated dimensions needed to provide space for the nut and flange mounting features. This helped me understand why the calculations and part selection needed to be considered together.

### Bryan — CAD Modeling and Assembly

I completed the CAD modeling and assembly and learned how to create a screw mate in SolidWorks. Setting the travel per revolution connected the rotation of the lead screw to the linear movement of the nut and crosshead. I also learned how to combine mates that kept the components aligned while allowing the intended movement. The screw mate required checking the direction of travel and the amount of movement produced by each revolution. Working with downloaded components also taught me to check the thread size, thread direction, and number of thread starts when selecting compatible parts.

The project took approximately 20 combined hours to complete.

