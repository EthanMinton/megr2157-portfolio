# A5 – Bracket Design

## Objective 
This assignment tasks us with designing a bracket following the rough construction given below, calculating the requirements of each section based on its ability to handle stress and its stiffness. Using bracket symmetry, these calculations allow us to determine exact values for all dimensions. We are given values such as a factor of safety of 4, a chosen applied load between 500 lbf < F < 800 lbf, and a selection of materials.

<img width="836" height="502" alt="image" src="https://github.com/user-attachments/assets/21de2e87-16fe-419a-9299-bd51d70bae30" />

##  Universal Assumptions 

I chose to use the material of ASTM A36 Steel, sourced directly from SolidWorks, to give me the values of its Modulus of Elasticity of 29,007,547.53 psi along with a Yield strength of 36,259.4 psi.

<img width="523" height="270" alt="image" src="https://github.com/user-attachments/assets/b742e84e-5a91-41fa-9144-11b537f01ade" />

The applied load I selected was 600 lbf, as it sits relatively in the middle of our range while not going completely overboard with our values and their complexities. 

We can assume that no direct failure will be related to shear stress, and that all calculations will be related to stress and deflection analysis.

The given dimensions below are of the rigid body that the bracket is designed to fit into; we must take these into account when solving for each of the parts of the bracket.

<img width="698" height="313" alt="image" src="https://github.com/user-attachments/assets/f606ab45-1ee1-4ee9-bb4d-91f40680ab70" />

##  Analysis 

To preface the analysis section I decided that it would be easiest to solve these features back-to-back, starting with Stress calculations and then moving onto stiff calculations. 

### Feature A - Stress and Stiffness

<img width="1470" height="536" alt="IMG_0092" src="https://github.com/user-attachments/assets/77a87fc8-7f62-4fff-8416-256ac7bd7f55" />


Some of the General Feature A assumptions include considering that no shear failure is applied. The assignment instructions describe the total force applied to the member due to the strap as 2 times the force of p, which in this case will result in a total force of 1200 lbf. Our feature will be considered as a single-surface-supported beam. We were required to make a geometric assumption based on the length of the model; the linked strap that was used within the constraints has a width of 3/4 of an inch. I decided to make our length 1 inch to compensate for any interactions from the other features and to accommodate the full 3/4 of an inch for the entire strap without having to worry about it hanging too close to the ledge. The given equations from the instructions are used below to solve for both the stress and stiffness calculations. Resulting in a Stress radius of 0.438 inches and a Stiffness radius of 0.19 inches. 

<img width="1640" height="1422" alt="IMG_0093" src="https://github.com/user-attachments/assets/39fce4a9-fe64-44b3-8dab-9d97bd990a9f" />

### Feature B - Stress and Stiffness

<img width="1571" height="587" alt="IMG_0090" src="https://github.com/user-attachments/assets/598347ef-d0a8-4df6-adc0-403c1a6afc93" />

Some of the general Feature B assumptions include considering that no shear failure is applied. Due to the fact that our Feature A had 2p of force pulling itself downward, we must assume that the force resulting from that must also be 2p as an internal reaction, giving us the force 1200 lbf. Our feature will be considered as a beam in tension, with the 2p force being axially applied to each of these ends. The rounded end of the feature will be assumed negligible for area calculations due to the support of the rest of feature A. I understand this isn't entirely accurate with the true physics, as stress concentrations are likely to appear at this junction, but for the sake of simplicity, we are able to hand calculation I decided to make this assumption. Based on our previous calculations for Feature A, we decided to keep the model's base width consistent with the diameter. This should give different sizes and scales for each calculation based on Feature A. Another assumption was reducing the length as much as possible to avoid any increase in our deflection; this is why I assumed a length of 1 inch. Once performing our calculations in solving for the thickness of the memeber the stress resulted in 0.151 inches and the stiffness resulted in 0.0217 inches 

<img width="1624" height="1344" alt="IMG_0091 (1)" src="https://github.com/user-attachments/assets/2ee7f3a9-656d-46aa-b40b-8f9c7b81b97c" />


### Feature C - Stress and Stiffness 

<img width="1475" height="532" alt="IMG_0094" src="https://github.com/user-attachments/assets/d82f6fa1-dc43-45c2-acd2-14e825f94a83" />


Some of the general Feature C assumptions include considering that no shear failure is applied. Due to the location of which our force 2p, 1200 lbf, is applied, it generates a moment about the feature that would require moment calculation for stress and deflection. For simplicity, the assignment asks us to assume that the feature is a simply supported structure with a concentrated load in its center. The major geometric assumption is the assumption of the length, as it must be based on the T-structure that the bracket is designed to fit on. Here we must consider its dimensions and the descriptor given by the instructions. A is considered 'intention for use where accuracy is not essential,' which falls right into the category of RC7 free-running fits. With a given dimension of 0.498 inches, we can assume a tolerance for the gap of 0.5 inches to allow for the fit. But we also need to consider dimension B, valued at 0.9992 inches, which was described as 'about the closest fits that can be expected to run freely," which falls under RC3 Precision Running, with a much tighter tolerance required; I decided to make the value 1 inch. The total length for the fit is 2.5 inches to accommodate both the RC7 and the RC3. The other geometric assumption was the width at 2 inches. I chose this value primarily because it allows a higher surface area of contact between the T-beam and the bracket itself. Solving for the height of the feature, we find that the stress height is at 0.498 inches and the stiffness height is 0.253 inches.

<img width="1461" height="1119" alt="IMG_0095" src="https://github.com/user-attachments/assets/39eb383c-b4a2-4abd-86e7-e4a7d00ff517" />

### Feature D - Stress and Stiffness

<img width="1488" height="543" alt="IMG_0096" src="https://github.com/user-attachments/assets/df3e509f-e46b-4a0e-b239-552d20068b8d" />

Some of the general Feature D assumptions include considering that no shear failure is applied. Due to the location of the force initially being applied it generates a moment that causes our beam to bend, requiring bending calculations for stress and stiffness. The moment is assumed to be generated at the distance of the initial force applied, at around 1.25 inches. Similar to the previous feature, there was another Geometric assumption that had to be based on a given tolerance for C, at 1.499 inches, being described as "where accurate location and minimum play is desired." Fitting the definition of RC1, we are able to assume a hole dimension tolerance of 1.5 inches, giving enough room for assembly without giving too much for perceivable play. To solve for the length of the beam the calculations are much more complex, resulting in a stress value of 0.814 inches and a strain value of 0.382 inches. 

<img width="1569" height="1327" alt="IMG_0097" src="https://github.com/user-attachments/assets/18536882-0906-4214-9b11-88e54fd63571" />


### Feature E - Stress and Stiffness

<img width="1357" height="502" alt="IMG_0098" src="https://github.com/user-attachments/assets/82dd19de-2c52-4706-9fcf-2dc4ef255a20" />

Some of the general Feature E assumptions include considering that no shear failure is applied. That the beam is a single surface support cantileverlever beam with a distributed load applied upward, with an assumption for a total concentrated load found within the middle of it at 600 lbf, not 12oo lbf, due to the symmetry of the bracket design. Referencing back to Feature C, we must take into consideration the width of dimension B again and our tolerances with the RC3 fit. Similar to what I previously explained, I chose 1 inch as our tolerance to allow it to run freely at the bare minimum. Once solving for our height value, we found that stress produced a height of 0.315 inches and stiffness produced h= 0.025 inches.

<img width="1376" height="1045" alt="IMG_0099" src="https://github.com/user-attachments/assets/e1461007-76d0-43bf-929e-2aedb48ef645" />

## Multi-View Sketches

Below are the created multi-view sketches. To note I attempted to make these as proportional as possible based on the surrounding dimensions to hopefully visualize how each value is different from the others and to perceive the different shapes created. The isometric views are a little rough mainly due to the difficulty of hand-drawing them without a direct real reference.

<img width="1640" height="1244" alt="IMG_0101" src="https://github.com/user-attachments/assets/28af971a-d536-49c7-ac2a-b941175d89f9" />

<img width="1640" height="1127" alt="IMG_0102" src="https://github.com/user-attachments/assets/05288786-9032-4e44-91e3-a43774e6d3b9" />

## Lessons Learned 

### Governing Failure Mode 

I want to say that for every single calculation, I found that the strength dimensions always cleared well over the stiffness dimension

## Communicate

