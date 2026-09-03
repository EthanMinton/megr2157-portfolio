# A2 – Truss Stress Analysis

## Objective

Design a Truss System geometry using the given parameters below, solving for the applied forces, the stress they create, and the material strengths used to resist the stress. 

## Analyze

### Creating the Truss System

The image below was given as the starting point for this assignment for us to create the Truss system around, with the given values of a, b, and P being 0.4, 0.3, and 25 KN. We were allowed to choose our value of P within a range of 20-30 KN, I decided to choose 25 KN as it sat right in the middle of those values and would allow me to deal with high stress calculations later within the assignment. 

<img width="467" height="301" alt="image" src="https://github.com/user-attachments/assets/69652f21-18dc-4320-84b5-1215811e07e9" />

## Decide

After analyzing the given constraints provided, I decided to resketch it all within my notetaker to ensure the process continues properly. Once sketched, I decided to get the general outline of the truss system to see how I could attempt to properly balance the forces through it. After which, I then created a new Joint, labeled as Joint E below, to help prevent possible concentration of stresses within the truss system.

<img width="1640" height="1952" alt="IMG_0012" src="https://github.com/user-attachments/assets/a498752f-fdaa-4635-a3f9-80d9ae3531a9" />

Before continuing, I decided to calculate all of the geometry that would be important later on within the system itself to prevent any issues and extra complications once we reach the internal force calculations. Starting by calculating the 2 angles that would impact the angled members within the truss, theta_b was calculated using the ratio (0.3/0.4) and plugging it into arctangent, resulting in an angle of 36.87 degrees. This angle will be important when calculating the internal forces for members BC and AD. Then theta_c was calculated using the ratio (0.3/0.2); 0.2 was used because Joint E was found to be directly in the middle of the given 0.4 measurement. Once it was plugged into arctangent, the angle given was 56.31 degrees, providing use to the members CE and DE.

<img width="1640" height="1601" alt="IMG_0018" src="https://github.com/user-attachments/assets/c81600dd-22b9-4f45-a452-a058868948ba" />


Moving toward the lengths of each of the members, I started by calculating the length of members BE and AE. Using the provided geometry, I combined the value of a over itself 3 times and divided it by half, as each member bisected the entire length, giving the length to be 0.6 meters. The members CE and DE were a little more complicated, as they required the use of rearranging the trigonometric ratio in order to solve for the hypotenuse. A considerably simpler way that I could have used was to calculate the hypotenuse of the triangle, which provides the same result of 0.361 meters. The members AD and BC were calculated similarly to the previous 2 members, with the rearranging of the sine trigonometric ratio to solve for the length, which gave 0.5 meters. Due to symmetry, there were only 3 calculations needed over 6.

<img width="1640" height="1738" alt="IMG_0019" src="https://github.com/user-attachments/assets/2bf4ef7b-8476-4ebd-870b-3c50ef42967f" />


### Calculating the Forces

#### External Forces

When approaching a truss system with Joint analysis, it is typically recommended to solve for all of the external forces present before continuing to the internal forces. The given constraints have 2 applied forces: 25 KN pushing upward at C and 25 KN pulling downward at D. Joint B is a roller, meaning it only has a force in the y-direction labeled B_y, and the Joint at A is a pin connection, giving it a force in both the x-direction and y-direction labeled A_x and A_y, respectively. Using statics and the equilibrium of F_x, we found that no other force is in the x-direction, resulting in A_x being equal to 0. Finding the moment about B allows us to solve for the force in A_y, giving us 8,333.3 N upward, and the resulting forces in the y-direction give us B_y at 8,333.3 N downward. In this case, I had assumed the direction of B was wrong, resulting in the negative solution. These results make sense due to the symmetrical relation of the truss.

<img width="820" height="400" alt="Math Scratch Paper (1)" src="https://github.com/user-attachments/assets/59012c28-7740-4280-9423-308b0ab43f54" />

#### Internal Forces 

To prevent bloat within the explanation of each joint, I will go into detail on my solution for Joint B, with a walkthrough of the rest of the joints reporting any important findings that could be significant.

Joint B was the first joint that I started with mainly because of the fact Joint B has 1 known external force and only 2 internal members to solve for. It acts as a simple start. With our known value for B_y, I solved for the equilibrium equation of the forces in the y direction. Isolating BC by adding B_y to the other side and dividing by the previously calculated Sine of theta_B. Plugging in our values gives us BC = 13,888.8 N compression. Now, with member BC's load, I can solve for the equilibrium equation in the x direction by adding BC times Cosine of theta_B to the other side and plugging in all known values. Answering 11,111.03 N of tension in member BE.

<img width="820" height="548" alt="Math Scratch Paper (2)" src="https://github.com/user-attachments/assets/2c481a1d-8ca9-4017-a67d-1db33dde5adf" />

After Joint B, I moved on to Joint C, where I found a significant piece of information that impacts my overall truss geometry. When you break down the equilibrium equation to solve for member CD, there is little to no force actually being applied to the member itself. It was a complete oversight in my original sketch that the member wouldn't take on any internal force and would just act as dead weight for the design. I opted to remove it from the final geometry. Otherwise, every calculation went as expected, outside of the minor incorrect assumption of member CE's force being in tension or compression. The highest internal force was calculated to be 20,030.8 N.

<img width="3750" height="3580" alt="Math_Scratch_Paper_10_original" src="https://github.com/user-attachments/assets/014bfe1e-2ff4-44d4-b1e2-f02acc947c0a" />


#### Cross-Sectional Area of the Members 

Taking the highest internal force within the truss, we can calculate the minimum area that is required for it to function without failure. To solve for area immediately, we have to combine 2 equations. These equations involve stress_allow being equal to stress_yield / Factor of Safety, and Stress_allow also being equal to maximum internal force / minimum area. Plugging these equations into each other allows for us to isolate the minimum area and solve for it. Giving us an area of 288.4 mm^2. Square rooting this value gives us 16.7 mm, the width of the beams and the amount the beam will be extruded.

<img width="820" height="567" alt="Math Scratch Paper (7)" src="https://github.com/user-attachments/assets/effeaa9b-cbb4-43bc-bb3e-fbc9888f93df" />

#### Weight of the Truss 

Calculating the weight of the entire truss requires a collection of values previously grabbed, such as a summation of all of the lengths of each of the truss members being multiplied by our now found cross sectional giving us the volume of the truss. Afterwards, you multiply the volume by the density to get the mass of the truss, which you can then multiply by gravity to obtain the given weight of 63.09 N.

<img width="820" height="397" alt="Math Scratch Paper (8)" src="https://github.com/user-attachments/assets/eadffd27-249c-4bb3-b115-5d5030ca2de8" />

Outside of calculations being relatively straightforward to set up and solve, a couple of assumptions about the nuances had to be made. Due to Creo, the CAD software I am using, lacking a standard material for A500 Steel, I was instructed to use another material with a similar density and properties. I decided to use SolidWorks ASTM A36 Steel as it had the same density as A500, with 7,850 Kg/m^3. Another assumption made is the nuance you have to take with how much detail you choose to go into. Do you include the holes from the pins in the area calculation? What about the possible overlap in the CAD modeling that will affect its weight calculations? There are so many intricate details you could consider with each of these calculations; I decided to keep it simple as the general goal here is to get it within earshot of what the CAD model itself computes.

<img width="484" height="556" alt="Screenshot 2026-09-02 204554" src="https://github.com/user-attachments/assets/1139d665-8050-4dfe-9960-22b70878d840" />


#### Shear Force on the Pins

NOTE: To preface this section, I want to mention the fact that I initially solved the shear stress wrong by making an incorrect assumption that the shear force was  just the highest load applied to the joint, which had completely thrown off my calculations for the pins' area and diameter. Thankfully, I noticed the document on the assignment itself that helped break down how to actually calculate the shear load applied to the pin. The image below is my original incorrect calculations.

<img width="820" height="711" alt="Math Scratch Paper (9)" src="https://github.com/user-attachments/assets/12c61f1a-8e68-4098-817d-bd1e35fd29e9" />

Correcting my work, I began by converting the given constraint values of hardened tool steel from the assignment from imperial to metric for the sake of consistency with the rest of the document. The yield shear stress of 170 ksi was roughly 1.172 GPa, and the density was converted from 0.278 lb/in^3 to 7.695 x 10^-6 kg/mm^3. To properly calculate an accurate shear force, we must break down the joint into the highest possible components within the x direction and y direction. Choosing Joint C, we break down the component forces of members CE and BC using the angles we calculated previously. We find that after combining like directions, we have a y force of 25,000 N acting in compression and an x force of 11,111 N acting in compression. We take both of these values and calculate the magnitude of the shear force vector, computing it to be 27,357.9 N.

<img width="1640" height="707" alt="IMG_0028 (2)" src="https://github.com/user-attachments/assets/b9fb22a2-9229-4e9b-8a80-44bf8bc5d7b3" />

<img width="820" height="856" alt="Math Scratch Paper (11)" src="https://github.com/user-attachments/assets/a204020a-3f1f-4314-a5fd-28c8571e9976" />

#### Cross Sectional Area of the Pin

Deriving the equation to solve for the cross-sectional area of the pin was similar to the member's calculation; we took tau_allow, which is equal to tau_yield / factor of safety, and tau_allow = shear force / minimum area. Combining these 2 equations, we can isolate area to equal the shear stress multiplied by the factor of safety, all divided by tau_yield. Plugging in our known values provides a pin area of 93.37 mm^2.

Within this set of calculations, I went out of my way to also calculate the diameter, as it would provide use when modeling the truss within CAD.

<img width="820" height="846" alt="Math Scratch Paper (13)" src="https://github.com/user-attachments/assets/ae678385-3d02-4343-9074-ff56e883f525" />

#### Weight of the Pins

To calculate the weight of the pins, we need to assume how we define their length. Generally, when designing a truss structure, the pins must stick out on the surface edge to ensure fasteners can be attached. I created a simple function that essentially calculates a pin length that is able to stick out through 2 members but also contains extra length that will allow for fasteners to be applied. The math you find below results in a length of around 40.08 mm. 

Now that we have all of our variables, we are able to calculate the weight of all 5 of the pins similarly to how we calculated the truss's weight. Taking our converted density of hardened tool steel, our pin cross-sectional area, the recently calculated pin length, gravity, and the number of pins we find that the entire truss roughly weighs about 1.412 N.

<img width="820" height="715" alt="Math Scratch Paper (12)" src="https://github.com/user-attachments/assets/2848650b-503d-4523-961b-0b8bd562c35b" />

### CAD Model using CREO

#### The Truss CAD

Opening the CAD file, I decided to start by establishing the position of the joints as a starting point, constraining them with the given initial geometry from the very beginning. Using the symmetry constraint to maintain true symmetry. 

<img width="1917" height="1006" alt="Screenshot 2026-08-31 191333" src="https://github.com/user-attachments/assets/571c1dc9-9efc-42e6-969d-d5a92018d585" />

Originally, I was tinkering with how I could CAD the model itself but kept running into issues with overlapping geometry that would impede my work, so I decided that the best course of action was to utilize the Construction lines. Beginning the sketch, I started by utilizing the diagonal rectangle shape, aligning it to the end of the joints previously placed. I then angled the bottom side of the beam to 36.87 degrees off the base, giving it a length of 0.5 meters and a width of 0.0167 meters.

<img width="1919" height="1008" alt="Screenshot 2026-08-31 191917" src="https://github.com/user-attachments/assets/72cae830-b79b-4d60-a173-082a9d874cb7" />

After completing member BC, I moved on to member AD. It is the symmetrical member to BC. I was able to utilize the equal constraint to maintain simplicity with the design and constraints. 

<img width="1919" height="1005" alt="Screenshot 2026-08-31 192959" src="https://github.com/user-attachments/assets/0bb9580d-c8c8-46f9-87d3-72cb71ba9727" />

Then I began to work on member CE, aligning the midpoint of the rectangle directly to joint C and angling it 56.31 degrees from the base. I then gave it a length of 0.361 meters. Using the equal constrain I then equalized it with the original member.

<img width="1919" height="1008" alt="Screenshot 2026-08-31 193705" src="https://github.com/user-attachments/assets/cfd6fd75-f54d-4f42-868d-6cf3d6d5d0ee" />

Similar to the previous set of members, I was able to create member DE utilizing the equation constraint and using member CE as a base to work off of, giving it the same angle, length, and width. Complete BE and AE members were relatively simple as I combined them as one long member, using 1.2 meters as our length and then the equal constraint for our width. After completing all the members, I then moved on to the pin holes and adjustments that had to be made to maintain the cross-sectional area. To elaborate, I calculated the area of what the pins would subtract from the entire member system and found the area of a circle that would compensate. That is the larger circle around the pin holes in this context.

<img width="820" height="647" alt="Math Scratch Paper (14)" src="https://github.com/user-attachments/assets/61b718cd-42b7-4cd8-9a90-af840972e8e5" />

I began by creating the first outline of the pin hole using the circle constraint, giving it a diameter of 0.0109 meters.

<img width="1919" height="1004" alt="Screenshot 2026-09-02 190449" src="https://github.com/user-attachments/assets/2a4d378a-ed41-49a0-b115-708c5162ca67" />

Then creating the second outline for the pinhole compensation, giving it a diameter of 0.02181 meters.

<img width="1919" height="1003" alt="Screenshot 2026-09-02 190633" src="https://github.com/user-attachments/assets/e1a80f82-338c-4530-8e18-6b56da7db577" />

After creating the initial circles, I used the equal constraint through the entire truss system to create the pin and pin compensation holes.

<img width="1919" height="1007" alt="Screenshot 2026-09-02 190750" src="https://github.com/user-attachments/assets/1e1e47c8-7560-4852-9460-954119dc0b3e" />
<img width="1919" height="1004" alt="Screenshot 2026-09-02 190737" src="https://github.com/user-attachments/assets/b4834dea-dd94-4002-a27c-c91266caf042" />

Finishing up all of the construction lines allows me to overlay the true lines to outline the true shape of the truss.

<img width="1919" height="1004" alt="Screenshot 2026-09-02 190913" src="https://github.com/user-attachments/assets/4decaba4-a6b0-41bc-a1a3-755d04bfb092" />
<img width="1919" height="1006" alt="Screenshot 2026-09-02 191107" src="https://github.com/user-attachments/assets/f04d7397-9c30-42ea-9f12-6020673aa958" />
<img width="1919" height="1005" alt="Screenshot 2026-09-02 191230" src="https://github.com/user-attachments/assets/5d7b4ed7-089e-4029-a6c0-dd475086b368" />

After confirming the true sketch, I then symmetrically extruded the model by 0.0167 meters, giving it the proper cross-sectional area that I had calculated.

<img width="1919" height="1003" alt="Screenshot 2026-08-31 200941" src="https://github.com/user-attachments/assets/911aa802-9c01-40e1-b9e1-7711784ca6bb" />

#### The Pins CAD
Moving on to creating the pin, I began by creating a circle sketch with a diameter of 0.0109 meters, and then extruding it 0.04008 meters.

<img width="1919" height="1008" alt="Screenshot 2026-09-02 193821" src="https://github.com/user-attachments/assets/6ee0b4f8-239b-48d1-b84e-1496f269f5b4" />
<img width="1916" height="1007" alt="Screenshot 2026-09-02 192030" src="https://github.com/user-attachments/assets/bdfa8e72-9a15-4781-8a9a-e39c9cc9a5ab" />
<img width="1917" height="1007" alt="Screenshot 2026-09-02 192744" src="https://github.com/user-attachments/assets/f9f79e30-3c39-4224-8a41-0caa579c8aa4" />

#### The Assembly CAD

After completing both the truss and the pins, I then began to assemble it all into a single assembly, adding the truss first. 

<img width="1919" height="1009" alt="Screenshot 2026-09-02 193146" src="https://github.com/user-attachments/assets/723ab447-4b1c-4ccc-b94a-c2e3caf97a05" />

I then added the pin and constrained it circumfrience to the inner circumference of the truss.

<img width="1919" height="1003" alt="Screenshot 2026-09-02 193332" src="https://github.com/user-attachments/assets/ac27e750-2056-4694-91c1-d21779240070" />

After that, I constrained its central dataplane to the truss central dataplane to ensure that the pin sits right in the middle.

<img width="1919" height="1005" alt="Screenshot 2026-09-02 193258" src="https://github.com/user-attachments/assets/a0f0f0ba-b595-46d2-892f-09b58e5def04" />

Performing this one by one for each of the pins created the final result you see below.

<img width="1919" height="1009" alt="Screenshot 2026-09-02 193349" src="https://github.com/user-attachments/assets/1ee993d1-92c6-41cd-bcdd-62fa7f2488ce" />
<img width="1919" height="1004" alt="Screenshot 2026-09-02 194914" src="https://github.com/user-attachments/assets/391cb492-2472-498e-91ba-d75356a4afb8" />

Using the material properties from SolidWorks and plugging them into Creo's material properties, we were able to find the approximate weights of 61.72 N for the truss and 1.29 N for the pins combined. This is extremely close to my calculated values of 63.09 N and 1.412 N.

<img width="820" height="647" alt="Math Scratch Paper (16)" src="https://github.com/user-attachments/assets/712f7eda-4bf1-408c-9171-7a4e09ef927a" />

## Communicate

### Lessons Learned 

The general lesson that I am continuing to learn is to learn how to balance what is asked of me and what I should provide within these assignments; as an engineer, it is a very rigorous degree that you have to pursue. The course load at times can take entire days to complete, and this assignment is no different. I roughly spent at least 34 hours on this assignment, with most of the time going to checking answers and documenting everything. Trying to make everything as clear as possible is not a simple task. To be an engineer, you need to be thorough with the answers and work you provide, but to what extent are you overexplaining or documenting every detail to the point where it can become overwhelming to a reader? I believe it would be a great help to whoever is grading this portfolio to provide me with an understanding of what is wanted from me and what I am doing too much of. 

The engineering lessons that I have learned through the course of this assignment are the effort to go from the purely mathematical to designing a real physical system. The original problem that was provided to us was considerably simple, with 4 points of interest and 2 applied forces, asking us to create a truss design that could help diffuse the forces properly throughout the entire system. Starting with the external force calculations, then moving to the internal forces within the members, to stress calculations, applying material properties, and then eventually designing it within CAD. It's not necessarily learning anything new from prior courses that dealt with statics, solids, or CAD, but it takes them and combines them into the actual engineering design process. The entire goal of this course. Yet outside of the overarching goal of the course, the technique required to calculate the shear force applied to the pin was something I would consider entirely new. As I had never encountered it before within solids, which explains why I initially just assumed the force was wrong. These lessons form over time through each assignment, many of which I don't even realize I am forming; it is important to vocalize these lessons as they are learned to reflect upon them.

### Likelihood of Failure Modes in Truss Components

To prevent re-explanations over each of the members and how they react to compression and tension forces, I thought it would be best to place

#### Member BC, Member AE, Member CE

**Identify** : All of the listed members above are found under compression, making elastic buckling the governing failure prior to any possible material yielding or fracture.

**State** : ASTM A36 steel is a ductile material, characterized by high elongation capacity and significant plastic/permanent deformation before fracture. For these members, though, that ductility never really comes into play, since buckling happens before the material gets anywhere near yield.

**Support** : Because member BC is relatively long and slender, its structural capacity is limited by elastic instability rather than pure axial strength. Under compressive loading, the critical buckling load produces a critical stress that is lower than the material's yield strength. Consequently, member BC will buckle laterally before the material ever reaches its yield strength. AE and CE follow the same reasoning, since they share the same slenderness-driven vulnerability.

**Propose** : Introduce lateral bracing; in my Solid Mechanics course, we were taught methods of reducing the likelihood of buckling by adding braces to a column. Within the equation for calculating the critical load for buckling, we find that adding a single lateral brace to a member divides the length by half, causing a quadruple of our critical load. Other methods require changing the actual geometry of the member itself, which would then introduce complications to the structure itself.

#### Member BE, Member AD, Member DE

**Identify:** All of the listed members above are found under tension, making yielding the governing failure in this case. Generally, a member under tension doesn't buckle, and our material properties prevent fracture.

**State:** ASTM A36 steel is a ductile material, characterized by high elongation capacity and significant plastic/permanent deformation before fracture. That ductility is what lets these members give visible warning under tension instead of snapping without notice.

**Support** : When handling ductile materials with intense tension loads, we find that they begin to strain in reaction to the stress applied. The fact that we're handling a ductile material is especially important here, as it's the deciding factor in whether our members fracture or yield. A brittle material has very little capacity for yielding, and once it reaches a critical load, it breaks immediately without much physical wear. Take, for example, two materials with the same ultimate strength and cross-sectional area; the brittle material shows little to no actual signs of strain, while our ductile material begins to noticeably stretch, then neck, and finally fracture.

**Propose** : Unlike buckling, we have less wiggle room to prevent failure due to the axial load applied. Either the force needs to decrease, which we can manage by adding more members to our truss system, or we can increase our area. Adding more members complicates many other systems at play, meaning increasing our cross-sectional area is the better, simpler option. It would help reduce our overall stress despite the load and keep our math relatively simple.

#### The Pins

**Identify**: Often, when it comes to pins, we'd expect shear stress to be the governing mode of failure, but in this case it's more likely bearing stress. That's because even though A36 and tool steel have very different material strengths, bearing stress tends to accumulate faster at the contact surface between the pin and the member than shear does across the pin's cross-section.

**Support** : CHI Engineers, in a model of a compression truss pin connection, showed the pin hole slowly elongating as load increases, a process called ovalization, and found that because pins are made from considerably tougher material, they're often not the governing body of failure in these connections (https://www.chi-engineers.com/post/nonlinear-inelastic-analysis-of-steel-pin-connections). Similarly, a real numeric example from AIAA showed a lug failing due to bearing at 11.25 kip vs. 13.08 kip for tension, with bearing coming in lower and acting as the governing mode of failure (https://www.aiaa-uq4cba.org/ref/calculation_example_simple_model.pdf). When researching, I kept finding that the governing failure mode was unexpectedly bearing in these cases, especially when dealing with a material that has considerably more strength than the members around it.

**Propose** : A design modification that would help reduce the likelihood of failure with both shear stress and bearing stress is to increase the diameter of the pin being used. Bearing stress depends on diameter times length for its cross-sectional area, while shear stress depends on the area of the pin's circular cross-section, so a larger diameter reduces both at once, without needing to change the pin material.

### CAD File Downloads



