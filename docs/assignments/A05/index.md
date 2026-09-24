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

Some of the General Feature A assumptions include considering that no shear failure is applied. The assignment instructions describe the total force applied to the member due to the strap as 2 times the force of p, which in this case will result in a total force of 1200 lbf. Our feature will be considered as a single-surface-supported beam. We were required to make a geometric assumption based on the length of the model; the linked strap that was used within the constraints has a width of 3/4 of an inch. I decided to make our length 1 inch to compensate for any interactions from the other features and to accommodate the full 3/4 of an inch for the entire strap without having to worry about it hanging too close to the ledge. The given equations from the instructions are used below to solve for both the stress and stiffness calculations. Resulting in a Stress radius of 0.438 inches and a Stiffness radius of 0.19 inches. 


### Feature B - Stress and Stiffness

Some of the general Feature B assumptions include considering that no shear failure is applied. Due to the fact that our Feature A had 2p of force pulling itself downward, we must assume that the force resulting from that must also be 2p as an internal reaction, giving us the force 1200 lbf. Our feature will be considered as a beam in tension, with the 2p force being axially applied to each of these ends. The rounded end of the feature will be assumed negligible for area calculations due to the support of the rest of feature A. I understand this isn't entirely accurate with the true physics, as stress concentrations are likely to appear at this junction, but for the sake of simplicity, we are able to hand calculation I decided to make this assumption. Based on our previous calculations for Feature A, we are able to decide the base width of the model will be kept consistent with the diameter. This should give different sizes and scales based on Feature A for each calculation. Another assumption was reducing the length as much as possible to avoid any increase in our deflection; this is why I assumed a length of 1 inch. Once performing our calculations in solving for the thickness of the memeber the stress resulted in 0.151 inches and the stiffness resulted in 0.0217 inches 

[Math Scratch Paper (41).pdf](https://github.com/user-attachments/files/32604529/Math.Scratch.Paper.41.pdf)

### Feature C - Stress and Stiffness 


## Analyze


## Decide


## Communicate

