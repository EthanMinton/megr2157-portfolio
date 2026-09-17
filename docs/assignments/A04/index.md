# A4 – Motor Mount


## Objective

This assignment asks you to design a motor mount for a Brushed 24V DC gear motor (3.6 kg · cm/46 RPM) with a 99.5:1 planetary gearbox, with its edge attached to a rigid wall. This involves a 2-step process that must account for a maximum deflection of around 0.3 mm and the maximum yield strength of your chosen material for both features involved. The first image below is a figure that details all of the dimensions of the listed motor. This will be utilized throughout the design process. The second image is the given image showing the location where the force P = 300 N is applied. Both of these images will be utilized to create the motor mount.

<img width="937" height="312" alt="image" src="https://github.com/user-attachments/assets/5511ea02-e7cc-4998-8b00-ff651b99743f" />

<img width="891" height="168" alt="image" src="https://github.com/user-attachments/assets/66a03692-c2aa-4069-b314-dbd8c614c90b" />

## Feature 1 Calculations

### F1 Assumptions 

The directions give us a multitude of variables that we are required to utilize in this assignment. These variables include the Force applied, P = 300 N; the max allowable deflection, defl_max = 0.3 mm; and the Factor of safety, FOS = 3. There are then a handful of variables that we must make assumptions about based on our own decisions. For material properties, I chose PLA plastic, as it is considered a common and reliable standard for 3D print design. Using MatWeb (link within resources), I was able to find information on its mechanical properties that are required to perform later calculations. For its yield strength, I decided to utilize the average value listed under "Tensile Strength, Yield," which was 45.2 MPa (Stress_yield = 45.2 MPa). I then grabbed the Modulus of Elasticity average, which was valued at 2.35 GPa, or as I had listed within my work, 2,350 MPa (defl_max = 2350 MPa)

<img width="1890" height="595" alt="image" src="https://github.com/user-attachments/assets/b99c77c4-6462-40d7-8af9-c3a75cb5c07d" />

The next group of assumptions that are required is the basic geometric assumption. Using the provided dimensions of the Motor above, I roughly determined the Length of feature 1 as 45 mm (L_1 = 45 mm). The logic behind this value is taking the greatest diameter value of the motor, which in this case is the midsection at 28 mm, and adding a rough tolerance of 15 mm that will enable me to include adaptations that will help prevent deflections. Such as a chamfer that can support the elbow more. The next was the base/width of the structure for both feature 1 and feature 2. Using the same diameter value from the motor, 28 mm, I decided to set the base to be 30 mm, as it makes calculations easier and provides a short tolerance that encompasses the entire motor mount (b = 30 mm). The last step was determining the distance at which the force P is applied to the shaft and then generates a moment on feature 1.

<img width="937" height="312" alt="image" src="https://github.com/user-attachments/assets/5511ea02-e7cc-4998-8b00-ff651b99743f" />

The graphic provided visually shows how the Force P is applied to the shaft of the Motor mount, but due to its simplistic nature, it makes it considerably difficult to determine the actual distance at which the force is applied. To ensure that an underestimation is not made of the design, I decided to use the 18 mm dimension of the entire shaft, including the lip section prior to the 28 diameter section (s = 18 mm).

<img width="891" height="168" alt="image" src="https://github.com/user-attachments/assets/66a03692-c2aa-4069-b314-dbd8c614c90b" />

### Solving for Feature 1's Height

#### F1 Free Body Diagram 

Feature 1 is the portion of the Motor Mount that will be housing the Motor itself. We are instructed by Appendix B that when solving for the height, we treat the specific section as a cantilever beam when creating our free body diagram. 

<img width="807" height="192" alt="image" src="https://github.com/user-attachments/assets/5d00e513-6d82-4c49-bde2-9400ccaf3459" />

The 2 free-body diagrams below are each designed to communicate important information to move through. The first, found at the top, is to communicate how exactly we calculate the moment applied to the feature. With 300 newtons being applied in the parallel direction to the beam itself, we multiply it by our assumed distance of the shaft of 18 mm. Giving a result of 5400 N mm. Performing the other equilibrium equations gives us a little more insight into the other forces created by the feature, although they will not be of any further use.

The second free body diagram is designed to show the applied moment and the reactions from the cantilever beam. 

<img width="1640" height="997" alt="IMG_0065" src="https://github.com/user-attachments/assets/a0622608-0086-42a6-9bb9-b95ea64555b3" />

#### F1 Stress Analysis

The image below shows the derivation and the calculated solution for finding the height. The reasoning and logic we apply to solving for the height or the thickness of the feature is that it provides the greatest impact when reducing deflection and stress within a structure. As the 2nd Area Moment of Inertia is found within the denominators of both calculations. With the other geometric values such as base and length being determined primarily by the motor's dimensions itself, it leaves us to solve for the geometry's height. 

You can observe that all of the initially grabbed equations are found on the left; taking these equations and plugging them into each other we receive the product where the blue arrows meet. The next step was to isolate for the height h. Following the red arrows, we begin to simplify values and variables until we are able to have the height squared on the right. Square rooting both sides, we now have our algebraic equation to solve for height. The green arrows follow the plugging in of our known values to receive our result with 8.47 mm of height required to satisfy the stress constraint.

<img width="1640" height="1725" alt="IMG_0067 jpg" src="https://github.com/user-attachments/assets/a91617af-6770-488b-87c8-7f64eb161009" />


#### F1 Deflection Analysis

Similarly to the previous logic and reasoning, height was also chosen as the value to solve for due to all other constraints being satisfied by the dimensions of the motor or the material properties selected. Height is the variable that both gives us the most ability to alter the geometry with the most impact on deflection and also isn't satisfied by any other geometric constraint.

You can observe that when solving, we only require the equation for solving deflection max and the 2nd Area Moment of Inertia. Plugging these equations into each other, following the blue arrows. We then begin to isolate the height, following the red arrows. Following the green arrows, we begin to plug in our known values to solve for height, which is calculated to be 14.58 mm of height required to satisfy the deflection constraints.

<img width="1640" height="1522" alt="IMG_0068 jpg" src="https://github.com/user-attachments/assets/520a82c2-2407-46ec-a501-fd89cc996c2c" />

#### F1 Governing Height and Cross-Sectional Area Calculation 

After completing our calculations, we determined that the height required to satisfy the stress and deflection constraints is 8.47 mm and 14.58 mm, respectively. Under this consideration, the governing height MUST be 14.58 mm, as any value below would violate the maximum allowed deflection. Stress would only become a concern below 8.47 mm, but by then we would have already violated the deflection constraint. With our governing height, we can now calculate the cross-sectional area of feature 1 by multiplying the height by our base of 30 mm, giving 437.4 mm^2.

<img width="1600" height="599" alt="IMG_0063" src="https://github.com/user-attachments/assets/d4cc43e3-50e4-4bb8-b86b-7799966f0f5e" />

### Solving for Feature 2's Height 

#### F2 Free Body Diagram

The geometry of Feature 2 is considerably more complicated than that of Feature 1, as it involves a rigid section and a free section that is allowed to bend, as presented by the graphic below. I spent roughly an hour and a half researching how the specific moment would be applied to Feature 2 based on the force P. I was not able to locate any clear source that pertained specifically to a cantilever beam being attached in such a way pertaining to a rigid body. This required me to assume, with the 2 key options being to consider the length to calculate the moment as either the entire length of the beam or just the length of the free body. I decided to choose the length of the entire body, as the decision to pick the free length and to be wrong about it would generate a design that isn't constrained to properly meet the required deflection and stress limits. The worst case for assuming the moment for the entire length is that the design is overengineered. In a real world senario I would deliberately simulate either in real life or within a Finite Element Analysis to consider what actually happens within the design. 

<img width="803" height="307" alt="image" src="https://github.com/user-attachments/assets/eba98fe7-7a2f-472c-a0f9-08a0c2ad2809" />

Now that the length for calculating moment has been established, we must analyze how we considered our length value. Although it isn't common for motor mounts to be designed this way, I chose to utilize the overall geometry for the motor to determine the total length. Taking into consideration the height of feature 1, as it would overlap within the corner section, at 14.58 mm. Then considering the Motor size at 38 mm and the Gearbox size at 36.3 mm. Combining these values gives us a total length of roughly 89.18 mm. For the sake of simpler calculations and dimension values when modeling, we round this value up to 90mm.

<img width="1640" height="1682" alt="IMG_0064" src="https://github.com/user-attachments/assets/c6a7a342-b9e8-457b-9289-1f75800b31f0" />

With the obtained total length, we can now calculate the moment about Feature 2. The original force applied, P = 300 N, is used within our calculations, being multiplied by the length of Feature 2, which is 90 mm, and the distance at which P was initially applied, 18 mm. This produces a product of 32,400 N mm of moment being generated on Feature 2.

<img width="1640" height="1250" alt="IMG_0066" src="https://github.com/user-attachments/assets/303b692d-f6fd-4fef-a7b2-0c22cf437398" />

#### F2 Stress Calculations

Similar to Feature 1's stress calculations, I decided to use PLA for the material of Feature 2. This is mainly because it keeps the calculations consistent, makes manufacturing easier, and lets us create Features 1 and 2 as a single part, improving strength around the connection section. If they were separate materials, it would have required us to fuse the parts in some alternative way that could complicate the manufacturing process. Because we continue to use PLA plastic, we will use the same material-property variables as feature 1: yield stress of 45.2 MPa and modulus of elasticity of 2350 MPa.

Using the previously derived equation for finding the minimum height based on stress, we take our newly calculated moment of 32,400 N mm and apply it to find the calculated value of 20.7 mm,

<img width="1640" height="1803" alt="IMG_0069 jpg (1)" src="https://github.com/user-attachments/assets/576a841f-d9c4-4a97-aefc-327a225c14ec" />

#### F2 Displacement Calculations 

The way that feature 2 is presented within the appendix, we find that the bottom portion of the model is the only free section that can bend, being determined by combining the height of feature 1, which is 14.58 mm, the distance of the pins from the corner where feature 1 and feature 2 meet, which is 18.65 mm, and half the diameter of the given bolts, which is 3.4 mm. This gives us a total free length of 34.93 mm. You can see that within this calculations we find the dimenstional constraints that will be utilized when modeling the motor mount.

<img width="1640" height="1362" alt="IMG_0072 jpg" src="https://github.com/user-attachments/assets/c61e9e17-147f-46d6-b790-c772d4de14e1" />

To calculate the Displacement height, we take our previously derived equation, our new calculated moment of 32,400 N mm, and the length that is free to move of 34.93 mm. We find that the minimum height based on displacement is 22.38 mm.

<img width="1640" height="1751" alt="IMG_0071 jpg" src="https://github.com/user-attachments/assets/8f02ff94-ea76-49a4-a03b-c91f1aafdc7e" />


#### F2 Governing Height and Cross-Sectional Area Calculation 

After completing our calculations for Feature 2 height with the stress- and deflection-based calculations, the values attributed are 20.7 mm and 22.38 mm, respectively. Meaning that the governing height must be 22.38 mm, as choosing any height below this value will fail the deflection constraint. With our now-known governing height, we can calculate the cross-sectional area with the height of 22.38 mm and the base of 30 mm; we find the area to be 671.4 mm^2.

<img width="1640" height="636" alt="IMG_0073 jpg (1)" src="https://github.com/user-attachments/assets/4f329b65-c349-4c31-b848-8a9b590e74f3" />

### Isometric View of Geometry 

<img width="1112" height="1112" alt="IMG_0074 PNG" src="https://github.com/user-attachments/assets/4e5f76c6-b085-40a6-9f58-2f890319a4fa" />

### CAD Model

#### Parametric Equations 

Before establishing the model, I first began to create global variables, assigning the many given, assumed, and calculated values from the work above. Significant variables that are not immediately obvious are the "h1" and "h2" variables using the deflection equations, due to the height found being considered the governing value. The "L_t" is a create If statement that essentially takes the found value of "h1", in this case 14.58 mm, and the assumed value of "L_m" that we found by taking the measurements of the motor itself at 74.6 mm. This gives us a rounded value of 90 mm. All of the dependent equations used within the variable sheet are directly copied from the calculations above, each with a comment providing a quick description of what each variable represents and its units.

<img width="1656" height="587" alt="image" src="https://github.com/user-attachments/assets/96bc3522-942d-476d-9b3b-72d96a07fa1c" />

#### Design Process

Utilizing the sketch interface of the Right Plane, I created a sketch that completely outlines both features 1 and 2. Giving a L-bracket shape to work with. Using both of the height variables, "h1" = 14.58 mm and "h2" = 22.39 mm, to determine the thickness of each feature. Then, use the "L1" and "L_t" variables to define the total length of each of the features.

<img width="1647" height="981" alt="image" src="https://github.com/user-attachments/assets/f08b86e6-f03c-4cd9-9d06-fb2518811ab6" />

Once the sketch is established, I then moved on to extruding the sketch outwards. Due to how I planned the design, I could easily use the base variable, "b" = 30 mm, to extrude the shape outwards. You can find the variable used on the left sidebar.

<img width="1915" height="982" alt="image" src="https://github.com/user-attachments/assets/b27e3d61-5943-4d29-89f1-d364ec19409d" />

Now, with an established L-shape for the motor mount, I then moved to creating the cuts within the model for the motor shaft and the surrounding bolts. Centering the shaft hole in the center of feature 1 using a geometric constraint and the variable for the length of the base "b" = 30 mm, and divided it by 2. So that, in the situation of the base being changed, these holes should reorient themselves back to the center of the feature. The diameter of the shaft hole is given by the dimensions of the motor at 6 mm. The reason this is not parametrically modeled is that this diameter had no use in determining other variables, and that often is the case; motors have much different lip geometry that would require much more complex modifications to the model. To constrain these bolts, I used construction lines to create a sketched circle with a diameter of 22 mm to align them with the given geometry; this feature was not defined parametrically for the same reasons as the shaft diameter. I then used the given bolt diameter variable "4_M3" = 3.4 mm to constrain all of the outside bolt diameters. 

<img width="1647" height="937" alt="image" src="https://github.com/user-attachments/assets/69372bff-30de-46d9-b4df-b56f07eb81f6" />

Once the sketch had been completed, I then extruded the 5 holes to go through all the geometry below them. 

<img width="1916" height="983" alt="image" src="https://github.com/user-attachments/assets/8b3ecd46-ad34-441d-85b8-fad0b93c1374" />

Creating another sketch on the same feature 1 surface, I began to create a circle, aligned in the center of the shaft hole, with a diameter of 18 mm. This was not parametrically defined due to the complex geometry that would need to be modified to accomidate other motors.

<img width="1647" height="937" alt="image" src="https://github.com/user-attachments/assets/bc22c37c-c17e-4edd-87fc-dbbb4e176955" />

Once sketched, it was extruded downward by 2 mm, cutting the material. 

<img width="1912" height="982" alt="image" src="https://github.com/user-attachments/assets/5e215a95-9f1d-4436-a333-d95368f834a7" />

Once completed, I then moved on to creating the bolt holes found on the face of feature 2. I geometrically constrained the 4 of them to be vertically and horizontally aligned to ensure they are properly spaced.  I then utilized the "B_w" = 7.5 mm and the  "B_h" = 18.65 mm  variables established to constrain them from the side edges, the top edge, and the corner where feature 1 and feature 2 meet. Once their positions were constrained, I set all of their diameters to be equal to each other and then used the "4_M3" = 3.4 mm to dimension their diameters.

<img width="1642" height="938" alt="image" src="https://github.com/user-attachments/assets/8dd4bd49-d256-4a18-8951-8257760838e3" />

I then extruded the sketch to cut through the entirety of feature 2. 

<img width="1917" height="976" alt="image" src="https://github.com/user-attachments/assets/9482b9ce-e9ac-4690-a51c-fe6e3d27b5dd" />

#### Minimize Deflection 

To minimize deflection within the overall design, I took the initiative to first create a chamfer that was asymmetrically dimensioned at 12 mm vertical and 7 mm horizontal, located right in the corner of the L between feature 1 and feature 2. I specifically chose this location due to how stress and deflection will likely concentrate at the corner due to its rigid structure. The chamfer is meant to add more material that can help resist this motion and stress.

<img width="1912" height="981" alt="image" src="https://github.com/user-attachments/assets/12c962c7-f734-4cdf-9efd-a6165d8e00eb" />

The second feature was an additional double fillet found on both of the edges of the previously created chamfer. This fillet was constrained to have a radius of 2 mm. The reasoning behind this design choice to prevent stress and deflection concentration is that it is generally known that sharp edges are a major cause of the buildup of these restrictions; with the added material from the chamfer and the smoother edges from the fillet, we can help prevent any major deflection/stress from building up at our weakest points.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/f5770db5-6d1f-487f-899e-f912c7283330" />

Once I had completed the model and moved on to the Chamfer and fillet, I realized that when I was initializing the model, my scale for units had not saved with mm as the basic unit, and had instead saved with cm as the basic unit. Thankfully, utilizing the Scale feature, I was able to scale down the model by 0.1 to ensure that all units were correctly processed. I plan on attaching both the normal model that contains the incorrectly scaled units but has the same dimensions and the scaled-down model that is appropriately sized with the Scale feature.

<img width="1911" height="978" alt="image" src="https://github.com/user-attachments/assets/1e16a7bf-9eaa-48f8-b818-4b3dd6cbb461" />

With the final design completed below. To note, the ring you find surrounding the bolts on feature 1 is the max diameter that the motor was dimensioned to have. I left the sketch there to signal where I could chamfer and fillet without interacting with the motor itself.

<img width="1642" height="938" alt="image" src="https://github.com/user-attachments/assets/8fa66d6f-15ea-4ee8-8741-875eb72453fe" />
### Drawing (2157)


### Lessons Learned 

Within this assignment, I learned the importance of keeping my work heavily organized and checking my assumptions before moving too far into the design process. One of the biggest examples of this was when I realized that my CAD model had been created using centimeters instead of millimeters. Every attempt I made to change the units from centimeters into millimeters would result in SolidWorks crashing. Even though the numerical dimensions within the model were correct, the overall scale of the part was incorrect. Thankfully, I was able to correct the issue by using the Scale feature, but this could have caused much larger problems if I had not caught it before finishing the model. It taught me that checking the units and settings before beginning a CAD model is a small step that can prevent a much larger issue later. It definitely will not happen again.

I also learned that organizing my work throughout the design process makes the overall assignment much easier to complete. During previous assignments, I constantly kept having to search for documentation and scratch work that I had to clean up. But by keeping track of my assumptions, equations, calculations, sketches, and CAD dimensions as I worked, I was able to go back and use the information from earlier steps instead of having to redo work. This was especially helpful when creating the parametric model because I could directly use the dimensions that I had already calculated. Overall, staying organized and checking small details throughout the process can save a significant amount of time and prevent mistakes from carrying over into later parts of the design.

The total time spent on the project was approximately 11 hours 30 minutes. Much of it was dedicated primarily to documenting the step-by-step process.

### Resources
Link to MatWeb: [https://www.matweb.com/search/DataSheet.aspx?MatGUID=ab96a4c0655c4018a8785ac4031b9278&ckck=1](https://www.matweb.com/search/DataSheet.aspx?MatGUID=ab96a4c0655c4018a8785ac4031b9278&ckck=1)

Link to Real Motor Mount: [https://www.omc-stepperonline.com/brushed-24v-dc-gear-motor-3-6kg-cm-46rpm-w-99-5-1-planetary-gearbox-pa28-28245800-g100](https://www.omc-stepperonline.com/brushed-24v-dc-gear-motor-3-6kg-cm-46rpm-w-99-5-1-planetary-gearbox-pa28-28245800-g100)

Link to CAD Pre-Scale: [Moter_mount_A4.SLDPRT](Moter_mount_A4.SLDPRT)

Link to Cad Post-Scale:[Moter_mount_A4_scaled.SLDPRT](Moter_mount_A4_scaled.SLDPRT)
