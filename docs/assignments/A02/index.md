# A2 – Truss Stress Analysis

## Objective

Design a Truss System geometry using the given parameters below, solving for the applied forces, the stress they create, and the material strengths used to resist the stress. 

## Analyze

### Creating the Truss System

The image below was given as the starting point for this assignment for us to create the Truss system around, with the given values of a, b, and P being 0.4, 0.3, and 25 KN. We were allowed to choose our value of P within a range of 20-30 KN, I decided to choose 25 KN as it sat right in the middle of those values and would allow me to deal with high stress calculations later within the assignment. 

<img width="467" height="301" alt="image" src="https://github.com/user-attachments/assets/69652f21-18dc-4320-84b5-1215811e07e9" />

After analyzing the given constraints provided, I decided to resketch it all within my notetaker to ensure the process continues properly. Once sketched, I decided to get the general outline of the truss system to see how I could attempt to properly balance the forces through it. After which, I then created a new Joint, labeled as Joint E below, to help prevent possible concentration of stresses within the truss system.

<img width="1640" height="1952" alt="IMG_0012" src="https://github.com/user-attachments/assets/a498752f-fdaa-4635-a3f9-80d9ae3531a9" />

Before continuing, I decided to calculate all of the geometry that would be important later on within the system itself to prevent any issues and extra complications once we reach the internal force calculations. Starting by calculating the 2 angles that would impact the angled members within the truss, theta_b was calculated using the ratio (0.3/0.4) and plugging it into arctangent, resulting in an angle of 36.87 degrees. This angle will be important when calculating the internal forces for members BC and AD. Then theta_c was calculated using the ratio (0.3/0.2); 0.2 was used because Joint E was found to be directly in the middle of the given 0.4 measurement. Once it was plugged into arctangent, the angle given was 56.31 degrees, providing use to the members CE and DE.

<img width="467" height="301" alt="image" src="https://github.com/user-attachments/assets/5a0276e2-ad1f-4755-89d9-4ee1af69e771" />


Moving toward the lengths of each of the members, I started by calculating the length of members BE and AE. Using the provided geometry, I combined the value of a over itself 3 times and divided it by half, as each member bisected the entire length, giving the length to be 0.6 meters. The members CE and DE were a little more complicated, as they required the use of rearranging the trigonometric ratio in order to solve for the hypotenuse. A considerably simpler way that I could have used was to calculate the hypotenuse of the triangle, which provides the same result of 0.361 meters. The members AD and BC were calculated similarly to the previous 2 members, with the rearranging of the sine trigonometric ratio to solve for the length, which gave 0.5 meters. Due to symmetry, there were only 3 calculations needed over 6.

### Calculating the Forces

#### External Forces

When approaching a truss system with Joint analysis, it is typically recommended to solve for all of the external forces present before continuing to the internal forces. The given constraints have 2 applied forces: 25 KN pushing upward at C and 25 KN pulling downward at D. Joint B is a roller, meaning it only has a force in the y-direction labeled B_y, and the Joint at A is a pin connection, giving it a force in both the x-direction and y-direction labeled A_x and A_y, respectively. Using statics and the equilibrium of F_x, we found that no other force is in the x-direction, resulting in A_x being equal to 0. Finding the moment about B allows us to solve for the force in A_y, giving us 8,333.3 N upward, and the resulting forces in the y-direction give us B_y at 8,333.3 N downward. In this case, I had assumed the direction of B was wrong, resulting in the negative solution. These results make sense due to the symmetrical relation of the truss.

#### Internal Forces 

To prevent bloat within the explanation of each joint, I will go into detail on my solution for Joint B, with a walkthrough of the rest of the joints reporting any important findings that could be significant.

Joint B was the first joint that I started with mainly because of the fact Joint B has 1 known external force and only 2 internal members to solve for. It acts as a simple start. With our known value for B_y, I solved for the equilibrium equation of the forces in the y direction. Isolating BC by adding B_y to the other side and dividing by the previously calculated Sine of theta_B. Plugging in our values gives us BC = 13,888.8 N compression. Now, with member BC's load, I can solve for the equilibrium equation in the x direction by adding BC times Cosine of theta_B to the other side and plugging in all known values. Answering 11,111.03 N of tension in member BE.


After Joint B, I moved on to Joint C, where I found a significant piece of information that impacts my overall truss geometry. When you break down the equilibrium equation to solve for member CD, there is little to no force actually being applied to the member itself. It was a complete oversight in my original sketch that the member wouldn't take on any internal force and would just act as dead weight for the design. I opted to remove it from the final geometry. Otherwise, every calculation went as expected, outside of the minor incorrect assumption of member CE's force being in tension or compression. The highest internal force was calculated to be 20,030.8 N.


#### Cross Sectional Area of the Members 

Taking the highest internal force within the truss, we can calculate the minimum area that is required for it to function without failure. To solve for area immediately, we have to combine 2 equations. These equations involve stress_allow being equal to stress_yield / Factor of Safety, and Stress_allow also being equal to maximum internal force / minimum area. Plugging these equations into each other allows for us to isolate the minimum area and solve for it. Giving us an area of 288.4 mm^2. Square rooting this value gives us 16.7 mm, the width of the beams and the amount the beam will be extruded.


#### Weight of the Truss 

Calculating the weight of the entire truss requires a collection of values previously grabbed, such as a summation of all of the lengths of each of the truss being multiplied by our now found cross sectional giving us the volume of the truss. Afterwards, you multiply the volume by the density to get the mass of the truss, which you can then multiply by gravity to obtain the given weight of 63.09 N.

Outside of calculations being relatively straightforward to set up and solve, a couple of assumptions about the nuances had to be made. Due to Creo, the CAD software I am using, lacking a standard material for A500 Steel, I was instructed to use another material with a similar density and properties. I decided to use SolidWorks ASTM A36 Steel as it had the same density as A500, with 7,850 Kg/m^3. Another assumption made is the nuance you have to take with how much detail you choose to go into. Do you include the holes from the pins in the area calculation? What about the possible overlap in the CAD modeling that will affect its weight calculations? There are so many intricate details you could consider with each of these calculations; I decided to keep it simple as the general goal here is to get it within earshot of what the CAD model itself computes.

Image of solidworks ASTM A35 Steel info
Image of weight calc

#### Shear Force on the Pins

NOTE: To preface this section, I want to mention the fact that I initially solved the shear stress wrong by making an incorrect assumption that the shear force was  just the highest load applied to the joint, which had completely thrown off my calculations for the pins' area and diameter. Thankfully, I noticed the document on the assignment itself that helped break down how to actually calculate the shear load applied to the pin. The image below is my original incorrect calculations.

Correcting my work, I began by converting the given constraint values of hardened tool steel from the assignment from imperial to metric for the sake of consistency with the rest of the document. The yield shear stress of 170 ksi was roughly 1.172 GPa, and the density was converted from 0.278 lb/in^3 to 7.695 x 10^-6 kg/mm^3. To properly calculate an accurate shear force, we must break down the joint into the highest possible components within the x direction and y direction. Choosing Joint C, we break down the component forces of members CE and BC using the angles we calculated previously. We find that after combining like directions, we have a y force of 25,000 N acting in compression and an x force of 11,111 N acting in compression. We take both of these values and calculate the magnitude of the shear force vector, computing it to be 27,357.9 N.

#### Cross Sectional Area of the Pin

Deriving the equation to solve for the cross-sectional area of the pin was similar to the member's calculation; we took tau_allow, which is equal to tau_yield / factor of safety, and tau_allow = shear force / minimum area. Combining these 2 equations, we can isolate area to equal the shear stress multiplied by the factor of safety, all divided by tau_yield. Plugging in our known values provides a pin area of 93.37 mm^2.

Within this set of calculations, I went out of my way to also calculate the diameter, as it would provide use when modeling the truss within CAD.

#### Weight of the Pins

To calculate the weight of the pins, it requires us to assume how we define their length. Generally, when designing a truss structure, the pins must stick out on the surface edge to ensure fasteners can be attached. I created a simple function that takes into account the width of the members by multiplying by 2 and then by 20% more to allow the pins to stick out. 


## Decide
_Which geometry did you select, and why? This is your first open design choice in the course — defend it._

## Communicate

