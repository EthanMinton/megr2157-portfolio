# A6 – Bracket Drawing

## Objective

Our objective for A6 is to design the Bracket we had optimized using the Stress and Strain equations through the previous assignment. This Design must be modeled using CAD Parametric Design to prove that our previous calcualtions are correct and properly follow through. Once completely modeled we then take the model and produce a drawing of the design following the standards listed.

## Parametric Design

### Established Parameters

Before actively modeling, I decided that the best course of action would be to translate over my previous work and calculations applied previously. When comparing the calculated values for the Stress dimensions needed to the Strain dimensions needed in every single instance between all of the features, the governing dimension was the Stress calculation. To minimize the bloat within the equations, I decided that all of the variables included would be dealing with each of the calculations specifically.

<img width="1811" height="321" alt="image" src="https://github.com/user-attachments/assets/03c07631-5a83-413b-ae0f-468c32bb6ec8" />

The first 4 variables listed at the top of the image are the 4 variables required to solve for the Length of Feature A and will be used throughout each of the other equations. The first "SAFETY_FAC" which was a given safety factor value of 4, this will be used in all of our equations as we deal with stress. The next was "LOAD"; this was a value that we selected at 600 lbfs, this will be integral to all equations and calculations. "LENGTH_A" is the next variable that was selected and set to 1 inch, this was a chosen value that was determined by the strap applied to our bracket, as it had a width of 3/4 of an inch I decided that 1 inch would be good general tolerence for a proper fit. The last of these 4 is "STRENGTH" set at 36259.4 psi, which was collected previously from SolidWorks.

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

Once the sketch was completed, I then extruded the sketch using our Primary thickness variable, which was set to 2 inches. 

<img width="1917" height="986" alt="image" src="https://github.com/user-attachments/assets/df6fa4a0-d82c-4b44-aae9-b6ee25ea1637" />


## Analyze


## Decide


## Communicate

