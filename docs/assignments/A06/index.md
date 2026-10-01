# A6 – Bracket Drawing

## Objective

Our objective for A6 is to design the Bracket we had optimized using the Stress and Strain equations through the previous assignment. This Design must be modeled using CAD Parametric Design to prove that our previous calcualtions are correct and properly follow through. Once completely modeled we then take the model and produce a drawing of the design following the standards listed.

## Parametric Design

### Established Parameters

Before actively modeling, I decided that the best course of action would be to translate over my previous work and calculations applied previously. When comparing the calculated values for the Stress dimensions needed to the Strain dimensions needed in every single instance between all of the features, the governing dimension was the Stress calculation. To minimize the bloat within the equations, I decided that all of the variables included would be dealing with each of the calculations specifically.

<img width="1811" height="321" alt="image" src="https://github.com/user-attachments/assets/03c07631-5a83-413b-ae0f-468c32bb6ec8" />

The first 4 variables listed at the top of the image are the 4 variables required to solve for the Length of Feature A and will be used throughout each of the other equations. The first "SAFETY_FAC" which was a given safety factor value of 4, this will be used in all of our equations as we deal with stress. The next was "LOAD"; this was a value that we selected at 600 lbfs, this will be integral to all equations and calculations. "LENGTH_A" is the next variable that was selected and set to 1 inch, this was a chosen value that was determined by the strap applied to our bracket, as it had a width of 3/4 of an inch I decided that 1 inch would be good general tolerence for a proper fit. The last of these 4 is "STRENGTH" set at 36259.4 psi, which was collected previously from SolidWorks for A36 Steel.

<img width="523" height="270" alt="image" src="https://github.com/user-attachments/assets/e6d94e8c-4e3c-4ddc-a403-ff10658b0b48" />

With these 4 variables, we can calculate the Diameter of A, "DIAMETER_A" by taking our variables and the function used in A5, and creating the function "= 2 * ( ( 4 * "SAFETY_FAC" * "LOAD" * "LENGTH_A" ) / ( PI * "STRENGTH" ) ) ^ ( 1 / 3 )", the only major difference being the 2 multiplier on the front that translates the calculated radius to diameter. I decided this would be easiest when modeling and carrying the value forward. Just like my hand calculations, this was found to be roughly 0.88 inches. 

Using the now-found diameter, we can use it to define our feature B, "THICKNESS_B" with the function of "= ( "LOAD" * 8 ) / ( "STRENGTH" * "DIAMETER_A" )", solving for a value of 0.15 inches. 

To solve for the height of C, we must create 2 new variables with "LENGTH_C" at 2.5 inches; this value was previously described in A5 as being determined using the tolerances of the given T-beam. Similarly, "HEIGHT_D" was determined as the height of the T-beam. "LENGTH_E" was determined similarly using the needed distance from the T-beam. The next was the "PRIMARY_THICKNESS," set at 2 inches. This was an assumed value that I decided to set at 2; I wanted to ensure that the contact surface between the Bracket and the T-beam was good. 

Using the values we find our "HEIGHT_C" using "= ( ( 3 * "LOAD" * "LENGTH_C" * "SAFETY_FAC" ) / ( "PRIMARY_THICKNESS" * "STRENGTH" ) ) ^ ( 1 / 2 )" giving us 0.5 inches, "LENGTH_D" using "= ( ( 12 * "LOAD" * "LOAD_DISTANCE_D" * "SAFETY_FAC" ) / ( "HEIGHT_D" * "STRENGTH" ) ) ^ ( 1 / 2 )" giving 0.81 inches, and "HEIGHT_E" using "= ( ( 3 * "LENGTH_E" * "LOAD" * "SAFETY_FAC" ) / ( "PRIMARY_THICKNESS" * "STRENGTH" ) ) ^ ( 1 / 2 )" giving 0.32 inches.

If interested in further discussion of these values and derivation of the equations, please refer to the previous Assignment A5. It goes into a lot more detail about the tolerances used for the T-beam and the explanations for the results.

### CAD Model 

I decided that the best way to go about this was to attempt to individually sketch and extrude each feature as an independent sketch and extrusion. Beginning with Feature A I dimensioned the diameter to be assigned to the previously calculated value of roughly 0.88 inches.

<img width="1645" height="986" alt="image" src="https://github.com/user-attachments/assets/8f2723ff-b2e3-43eb-b786-1d2e6ca80e58" />

I then used the predetermined Length of A, set at 1 inch, to model the extrusion of feature A.

<img width="1917" height="1007" alt="image" src="https://github.com/user-attachments/assets/1f22fe8b-45d4-4dc1-b527-d82c1c8319b2" />

Starting with Feature B, I then began by creating a rectangular model constraining its bottom edge to the full diameter of Feature A, so that in the instance of Feature A being changed, the result for Feature B will also change. I decided that changing the height using a variable/parameter would be redundant; the height for Feature B was determined through a generalized assumption and had no impact on the stress calculations. To avoid adding bureaucracy, I decided to input the value of 1 inch directly.

<img width="1647" height="978" alt="image" src="https://github.com/user-attachments/assets/9e463dae-52fb-4725-aca4-7c1f974311d9" />

Completing the sketch, I then extruded feature B by the calculated value from our equations. Equating to roughly 0.15 inches.

<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/7d89382f-8876-4e6a-98cb-94e572d0bc52" />

Moving onto Feature C I first began by creating a rectangular sketch with a point added to the center of its bottom side. I then constrained the point to be both midpointed and coincidented to Feature B so that any alteration to the height or dimensions would readjust itself automatically.

<img width="1917" height="1016" alt="image" src="https://github.com/user-attachments/assets/88075881-4a3f-4edb-ac4e-60b8daa7975f" />

I then constrained the length using the assumed parameter for Feature C at 2.5 inches. Then its height to the calculated height for Feature C at 0.5 inches.

<img width="1645" height="986" alt="image" src="https://github.com/user-attachments/assets/52cc0281-ce78-47c5-924f-d565b1f282a8" />

<img width="1647" height="985" alt="image" src="https://github.com/user-attachments/assets/2a407bf4-96c0-4d35-ac4f-f4b2a1a6bed6" />

Once the sketch was completed, I extruded the sketch using our Primary thickness variable, which was set to 2 inches. 

<img width="1917" height="986" alt="image" src="https://github.com/user-attachments/assets/df6fa4a0-d82c-4b44-aae9-b6ee25ea1637" />

The next step was feature D: sketching 2 identical rectangles aligned to be constrained to the bottom of feature C, equalizing the horizontal lines and the vertical lines using the constraints. I was able to dimension over double the model.  Using the T-beam dimensions, I had a height of 1.5 inches using the variable; I was able to constrain both sides with the height of feature D. I then constrained both sides using the calculated length for D, which roughly values to 0.81 inches.

<img width="1648" height="985" alt="image" src="https://github.com/user-attachments/assets/a01fb741-8d36-4631-b991-4952694c5a1a" />

<img width="1647" height="986" alt="image" src="https://github.com/user-attachments/assets/e42cd7d1-fa01-41c1-8d29-5e3a84451473" />

Similar to feature C, I then used our primary thickness value of 2 inches to extrude the feature on both sides. 

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/fd9c1b6f-b80c-47c8-97c8-bbe32f8af6e2" />

For Feature E first started by creating 2 rectangles aligned with the top of the previous feature D, using the equal constraint to set their values of their horizontal lines and vertical lines equal to each other. Constraining the height, I used our calculated height variable for E, which was roughly 0.32 inches.
he
<img width="1646" height="977" alt="image" src="https://github.com/user-attachments/assets/9ffb276b-3e17-478e-a87d-2896f14e2ae6" />

The next constraint I chose was the length for E, this was a given value from the T-beam and its tolerances, roughly 1 inch. 

<img width="1646" height="1011" alt="image" src="https://github.com/user-attachments/assets/9160c6ee-ed36-4658-ba90-ca839d8b55ea" />

Once the sketch had been completed, I then extruded the sketch by the same primary thickness of 2 inches to match the rest of the primary section of the model.

<img width="1917" height="1005" alt="image" src="https://github.com/user-attachments/assets/64c4f369-9991-46dd-8224-202a0f3c2a26" />

Below is the final structure of the model. I want to note that the true dimensions of the tolerances were all rounded to the 2nd decimal place, this isn't entirely accurate, and the drawing below will go into more detail about which tolerances are needed for machining. 

<img width="1917" height="1007" alt="image" src="https://github.com/user-attachments/assets/939345a1-ba83-4884-b924-4a4e0625ee5f" />

## Drawing 

For the engineering drawing, I created a fully dimensioned multi-view drawing of the bracket using third-angle projection. The dimensions were based on the calculations and fit selections from the previous assignment. I also included the required tolerance block of X.X ± 0.02, X.XX ± 0.01, and X.XXX ± 0.005 for the general dimensions of the bracket. 

For the three dimensions that interact with the rigid T-beam, I used the fit tolerances determined in the previous assignment rather than the general tolerance block. Dimension A was designed around the 0.498 inch rigid-body dimension and uses an RC7 free-running fit, giving the bracket dimension a tolerance of +0.0016/-0.0000 inches. Dimension B was based around the 0.9992 inch dimension and uses an RC3 precision running fit, giving a bracket tolerance of +0.0008/-0.0000 inches. Finally, Dimension C was based around the 1.499 inch dimension and uses an RC1 fit because accurate location and minimum play were desired, giving a bracket tolerance of +0.0004/-0.0000 inches. These dimensions were determined by the maximum possible tolerance allowed by each of their fits as described within the Machinery's handbook. I elaborated more in the previous assignment on these tolerances and the tables attributed to how these values were found.

These tighter tolerances were used specifically on the mating surfaces because they control how the bracket fits onto the rigid T-beam. The remaining non-critical dimensions use the general tolerance block shown on the drawing. They are expected to not be required to be completely perfect, as they won't be interacting in the same way that the sliding fit does. The majority of the non-fit tolerances were left to be found at 2 decimal places meaning that they should be found with a tolerance value of +- 0.01 which makes sense as our model should be expected to be accurate to the calculations we had made while also considering the time and money it would take to achieve tighter tolerances for minimum benefit.

## Lessons Learned 

One of the main things I learned from this assignment was how to connect the calculations from the previous assignment directly to the parametric CAD model. For example, the stress equation used for Feature B was used to determine the required thickness of the member. Instead of calculating the value separately and simply typing the final dimension into CAD, I connected the dimension to the appropriate parameter/equation in the CAD model. This allowed the dimension to update when the input values were changed. If the calculated value changed, the linked dimension updated with it, while the rest of the model responded to the change through the existing parametric relationships rather than requiring the entire model to be rebuilt.

Take for example. FINISH LATER

Another lesson I learned was how tolerances should be selected based on the function of a dimension. For example, Dimension B is a mating surface with the rigid T-beam and uses an RC3 precision running fit, so it requires a much tighter tolerance than a non-critical dimension. In contrast, a dimension such as the overall width of the bracket does not control how the bracket fits onto the T-beam, so it can use the looser general tolerance from the drawing tolerance block. Using a tighter tolerance on a non-critical dimension would require more precise manufacturing and could increase manufacturing difficulty and cost without providing a functional benefit. This showed me that tolerances should be based on the purpose of each feature rather than applying the tightest tolerance to every dimension.

Time Taken: 9 Hours 45 Minutes


## 2157 

Equations 
<img width="1212" height="231" alt="image" src="https://github.com/user-attachments/assets/bd919d6c-021d-4b6c-aa8b-880911c6443e" />

Mention the rectangular flat design, easy to mass produce through pressing machine

length dim
<img width="1643" height="982" alt="image" src="https://github.com/user-attachments/assets/9deb1cee-1e91-4db7-873a-33efe2dd782c" />


width dim 
<img width="1642" height="987" alt="image" src="https://github.com/user-attachments/assets/e53c9cd5-e63a-4a50-976d-4b6017b7b64e" />

thickness dim
<img width="1917" height="1010" alt="image" src="https://github.com/user-attachments/assets/afb972b8-7ab9-4141-bcc7-596ea4945706" />


dia a

<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/d092bf05-13cf-4b15-89ca-5f58ec11faf2" />


dia 1
<img width="1647" height="986" alt="image" src="https://github.com/user-attachments/assets/2c9caabb-7466-4eb0-beaf-11949ffe2164" />


circle distance 
<img width="1648" height="986" alt="image" src="https://github.com/user-attachments/assets/3f70234c-672b-4fe8-937a-bff3d20bdd81" />

Extrude
<img width="1917" height="1006" alt="image" src="https://github.com/user-attachments/assets/66360c24-b1d6-4f46-bf50-f733b8cc2396" />


Drawing

The 0.88 hole from our book has tolerance of 0.4 tho + and the 1 hole has tolerance of 0.5 tho +, no negative
## Analyze


## Decide


## Communicate

