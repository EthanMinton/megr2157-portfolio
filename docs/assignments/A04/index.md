# A4 – Motor Mount


## Objective

This assignment asks you to design a motor mount for a Brushed 24V DC gear motor (3.6 kg · cm/46 RPM) with a 99.5:1 planetary gearbox, with its edge attached to a rigid wall. This involves a 2-step process that must account for a maximum deflection of around 0.3 mm and the maximum yield strength of your chosen material for both features involved. The first image below is a figure that details all of the dimensions of the listed motor. This will be utilized throughout the design process. The second image is the given image showing the location where the force P = 300 N is applied. Both of these images will be utilized to create the motor mount.

<img width="937" height="312" alt="image" src="https://github.com/user-attachments/assets/5511ea02-e7cc-4998-8b00-ff651b99743f" />

<img width="891" height="168" alt="image" src="https://github.com/user-attachments/assets/66a03692-c2aa-4069-b314-dbd8c614c90b" />

## Feature 1 Calculations

### Assumptions 

The directions give us a multitude of variables that we are required to utilize through this assignment. These variables include the Force applied, P = 300 N; the max allowable deflection, defl_max = 0.3 mm; and the Factor of safety, FOS = 3. There are then a handful of variables that we must make assumptions about based on our own decisions. For material properties, I chose PLA plastic, as it is considered a common and reliable standard for 3D print design. Using MatWeb (link within resources), I was able to find information on its mechanical properties that are required to perform later calculations. For its yield strength, I decided to utilize the average value listed under "Tensile Strength, Yield," which was 45.2 MPa (Stress_yield = 45.2 MPa). I then grabbed the Modulus of Elasticity average, which was valued at 2.35 GPa, or as I had listed within my work, 2,350 MPa (defl_max = 2350 MPa)

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

remind: image of fbd 1 ( need to do one last check of variables)

#### F1 Stress Analysis

The image below shows the derivation and the calculated solution for finding the height. The reasoning and logic we apply to solving for the height or the thickness of the feature is that it provides the greatest impact when reducing deflection and stress within a structure. As the 2nd Area Moment of Inertia is found within the denominators of both calculations. With the other geometric values such as base and length being determined primarily by the motor's dimensions itself, it leaves us to solve for the geometry's height. 

You can observe that all of the initially grabbed equations are found on the left; taking these equations and plugging them into each other we receive the product where the blue arrows meet. The next step was to isolate for the height h. Following the red arrows, we begin to simplify values and variables until we are able to have the height squared on the right. Square rooting both sides, we now have our algebraic equation to solve for height. The green arrows follow the plugging in of our known values to receive our result with 8.47 mm of height required to satisfy the stress constraint.

remind: image of feature 1 stress height calc (the one with the green arrows)

#### F1 Deflection Analysis

Similarly to the previous logic and reasoning, height was also chosen as the value to solve for due to all other constraints being satisfied by the dimensions of the motor or the material properties selected. Height is the variable that both gives us the most ability to alter the geometry with the most impact on deflection and also isn't satisfied by any other geometric constraint.

You can observe that when solving, we only require the equation for solving deflection max and the 2nd Area Moment of Inertia. Plugging these equations into each other, following the blue arrows. We then begin to isolate the height, following the red arrows. Following the green arrows we begin to plug in our known values to solve for height which is calculated to be 14.58 mm of height required to satisfy the deflection constraints.

remind: image of the feature 1 deflection height calc (the one with green arrow)

#### F1 Governing Height and Cross Sectional Area Calculation 

After completing our calculations, we determined that the height required to satisfy the stress and deflection constraints is 8.47 mm and 14.58 mm, respectively. Under this consideration, the governing height MUST be 14.58 mm, as any value below would violate the maximum allowed deflection. Stress would only become a concern below 8.47 mm, but by then we would have already violated the deflection constraint. With our governing height, we can now calculate the cross-sectional area of feature 1 by multiplying the height by our base of 30 mm, giving 437.4 mm^2.

remind: image of governing height and cross sectional area

### Solving for Feature 2's Height 

T
#### F2 Free Body Diagram



## Decide


## Communicate



https://www.matweb.com/search/DataSheet.aspx?MatGUID=ab96a4c0655c4018a8785ac4031b9278&ckck=1
