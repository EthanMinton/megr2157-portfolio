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

For the three dimensions that interact with the rigid T-beam, I used the fit tolerances determined in the previous assignment rather than the general tolerance block, these were each specific callouts that were directly placed on the model. Dimension A was designed around the 0.498 inch rigid-body dimension and uses an RC7 free-running fit, giving the bracket dimension A a tolerance of +0.0016/-0.0000 inches. Dimension B was based around the 0.9992 inch dimension and uses an RC3 precision running fit, giving a bracket tolerance of +0.0008/-0.0000 inches. Finally, Dimension C was based around the 1.499 inch dimension and uses an RC1 fit because accurate location and minimum play were desired, giving a bracket tolerance of +0.0004/-0.0000 inches. These dimensions were determined by the maximum possible tolerance allowed by each of their fits as described within the Machinery's handbook. I elaborated more in the previous assignment on these tolerances and the tables attributed to how these values were found.

<img width="1610" height="945" alt="A6_Model" src="https://github.com/user-attachments/assets/9f337166-358c-415d-9cf5-da444c2d95c6" />

These tighter tolerances were used specifically on the mating surfaces because they control how the bracket fits onto the rigid T-beam. The remaining non-critical dimensions use the general tolerance block shown on the drawing. They are expected to not be required to be completely perfect, as they won't be interacting in the same way that the sliding fit does. The majority of the non-fit tolerances were left to be found at 2 decimal places, meaning that they should be found with a tolerance value of +- 0.01, which makes sense as our model should be expected to be accurate to the calculations we had made while also considering the time and money it would take to achieve tighter tolerances for minimum benefit.

Note: At first glance, the dimensions found on the model may seem like there are very few found on the page itself; we were specifically warned about overconstraining our drawings, so I took a deliberate practice to avoid having repetitive dimensions that were previously defined by other dimensions combining. If any text or details are difficult to read, please refer to the drawing model linked at the bottom. 

## Lessons Learned 

One of the main things I learned from this assignment was how to connect the calculations from the previous assignment directly to the parametric CAD model. For example, the stress equation used for Feature A was used to determine the required diameter of the member. Instead of calculating the value separately and simply typing the final dimension into CAD, I connected the dimension to the appropriate parameter/equation in the CAD model. As previously mentioned, the equation used within the parameters was "= 2 * ( ( 4 * "SAFETY_FAC" * "LOAD" * "LENGTH_A" ) / ( PI * "STRENGTH" ) ) ^ ( 1 / 3 )", giving us an output of the diameter. This allowed the dimension to update when the input values were changed. If the calculated value changed, the linked dimension updated with it, while the rest of the model responded to the change through the existing parametric relationships rather than requiring the entire model to be rebuilt. I specifically chose to highlight this equation because the determination of the diameter of feature A directly echoes through the calculations of feature B thickness. We find that within its equation, "= ( "LOAD" * 8 ) / ( "STRENGTH" * "DIAMETER_A" )", the thickness is inversely proportional to the diameter calculation: the larger the diameter, the smaller the thickness; the smaller the diameter, the larger the thickness. This is the core reason we parametrically design so that alterations ripple throughout the design without major issues. It allows us to directly observe the effects that take place if we just change a singular value. Thankfully, my calculations gave me realistic scenarios for handling Steel as a material, it has a considerably large Modulus of Elasticity compared to its yield strength, providing the reasoning for why, in all of our equations, the governing behavior belongs to Stress and not the strain calculations.



Another lesson I learned was to select tolerances based on a dimension's function. Throughout the assignment of A5, we were tasked with taking the given constraints of our model and producing equations to output values that were determined based on those values. In a couple of situations, we were required to make a couple of assumptions for given dimensions that I would consider more arbitrary to the process than some of the other constraints. Take, for example, the thickness of the primary model was defined by me at 2 inches; I chose this value mainly because I wanted a thick beam section that would contact much of the T-beam. However, setting it to 2 inches was not as critical for accuracy as most of the other dimensions. This is why I assigned it to a single decimal place of +-0.02 inches, as the impact of this is not deep enough to where a variation of length by 0.02 inches could considerably affect any load capacities that are not consumed entirely by our safety factor of 4. It is important to understand the manufacturing that takes place behind the scenes of every design. I can make every single dimension to the accuracy of 3 decimal places at +-0.005 but at the end of the day, the cost would be extremely high for constraints of what is considered not critical in needing that type of accuracy. I decided that each of the more arbitrary assumptions for dimensioning should be based around a lighter tolerance handle.

<img width="1467" height="650" alt="image" src="https://github.com/user-attachments/assets/aad68303-0732-4b74-b13c-971a834d803a" />

But when considering a tighter tolerance, the vast majority that get to the +-0.005 range are personally changed by me, as they had extenuating circumstances that determined their values. Take, for example, our height for the bracket of 1.5 inches; based on our previous investigation, we understand that it falls under the constraint of RC1 tolerances, one of the tightest requirements defined by "where accurate location and minimum play is desired." Based on our Machinery's Handbook, Table 8a on page 654 of the 32nd edition, it specifically mentions that the hole for the RC1 class is in the range of 1.19 - 1.97 inches, which gives us a tolerance of just +0.4 tho, -0.0 tho. This is what you find in our drawing itself; if we were to model the T-beam, it would constrain the shaft tolerances within the same section. Due to the nature of the fit required, a lot more attention to machining is expected here; the cost and time are worth it to produce an accurate and usable product. 

<img width="4032" height="3024" alt="658041089-81084e86-7a46-4257-a036-6e034bc67243" src="https://github.com/user-attachments/assets/0498a706-70c7-42a7-b6a0-1dba7a8ba23a" />

<img width="967" height="635" alt="image" src="https://github.com/user-attachments/assets/d6e65fd2-af37-41e9-8399-b2379e8b8b3c" />

Outside of that, the biggest issue/mistake I encountered during the parametric modeling process was determining which dimensions actually needed to be controlled by parameters. Initially, I considered adding variables for nearly every dimension, but this would have added unnecessary complexity to the model. I instead focused the parameters on dimensions that were directly determined by the stress calculations, fit requirements, or other dimensions that needed to update when the model changed. For example, the height of Feature B was entered directly because it was an assumed dimension and did not affect the stress calculation. This helped keep the model parametric where it was functionally important without unnecessarily increasing the number of equations.

Time Taken: 9 Hours 45 Minutes


## 2157 - Link Design

When designing the link, I decided that the best course of action would be to start by constraining all of the parameters within the parametric design. Starting with some of the same basic variables with "LOAD" being 600 lbf, the assumed "LENGTH" and "WIDTH" being at 3 inches and 2 inches respectively, "STRENGTH" of A36 Steel being at 36,259.4 psi, the previously calculated "DIAMETER_A" at 0.876 inches, and the given "DIAMETER_1" at 1 inch. To find the thinnest cross sectional area, we divide our width with the largest diameter of 1 inch and plug it into the variable "DIFFERENCE" giving a value of 1 inch. With these variables we can calculate the Stress thickness, similar to the Bracket the stress was the governing equation, using "= ( "LOAD" * "SAFETY_FAC" ) / ( "DIFFERENCE" * "STRENGTH" )" assigned to "LINK_THICK" with a value roughly 0.07 inches.

<img width="1212" height="231" alt="image" src="https://github.com/user-attachments/assets/bd919d6c-021d-4b6c-aa8b-880911c6443e" />

### Parametric Design
To preface the parametric design, I wanted to note that the flat rectangular design was adopted for a couple of reasons; one is that it allows for our calculations to remain relatively simple,  with the cross-sectional area not being interrupted by any rounded corners or chamfers. This gives our calculations a higher degree of accuracy and prevents any large assumptions that can lead to failure. Along with accounting best for assumptions, the design also makes it relatively easy to manufacture and produce on a large scale utilizing Metal Stamping to create the general shape of the part, as needed extremely accurate tolerances aren't required for this part, we are able to use methods that can run quickly and accurately enough. The hole tolerances are a different story that would requiere more accurate milling machine that can compensate for the tolerances of the fits that are required.


Starting with the previously mentioned rectangular sketch of the model we set our length to our previously mentioned variable valued at 3 inches. 
<img width="1643" height="982" alt="image" src="https://github.com/user-attachments/assets/9deb1cee-1e91-4db7-873a-33efe2dd782c" />


Moving on to the width we define it by the "WIDTH" dimension set at 2 inches.
<img width="1642" height="987" alt="image" src="https://github.com/user-attachments/assets/e53c9cd5-e63a-4a50-976d-4b6017b7b64e" />

Once the sketch was complete, using the calculated thickness, it was then extruded roughly by 0.07 inches.
<img width="1917" height="1010" alt="image" src="https://github.com/user-attachments/assets/afb972b8-7ab9-4141-bcc7-596ea4945706" />

Creating a sketch on the surface of the rectangular extrusions I create the circle for the Diameter A defined at 0.867 inches. When defining the sketch it was aligned to the center of the model. 
<img width="1917" height="1012" alt="image" src="https://github.com/user-attachments/assets/d092bf05-13cf-4b15-89ca-5f58ec11faf2" />


Aligning the second circle to the first I create another sketch with the other diameter parameter at a value of 1 inch.
<img width="1647" height="986" alt="image" src="https://github.com/user-attachments/assets/2c9caabb-7466-4eb0-beaf-11949ffe2164" />


Before continuing to extrusion, I parametrically defined the model so that the centers of both circles are found roughly a fourth of the total length away from the vertical edges. Giving enough space for the holes without interacting with either circle or the edges.
<img width="1648" height="986" alt="image" src="https://github.com/user-attachments/assets/3f70234c-672b-4fe8-937a-bff3d20bdd81" />

Once the sketch was completed, it was extruded through the original model to create the double-holed link.
<img width="1917" height="1006" alt="image" src="https://github.com/user-attachments/assets/66360c24-b1d6-4f46-bf50-f733b8cc2396" />

The final model is seen below.
<img width="1917" height="992" alt="image" src="https://github.com/user-attachments/assets/c0e07577-84e6-4903-9e65-b7cb2f8d9c41" />

### Link Drawing

<img width="1610" height="945" alt="A6_LINK" src="https://github.com/user-attachments/assets/a46120d2-530d-4c79-a041-8241c6ada6a0" />

### Link Lessons Learned 

One lesson I learned about ensuring part-to-part compatibility through tolerancing is that it is important to pay attention to the specific type of fit required for each feature. For Feature A, the bracket requires a sliding fit, meaning the tolerance needs to allow the part to move while still maintaining a controlled fit. Feature 1 requires a press fit, which requires a different tolerance because the parts need to fit together more tightly and accurately. These different fit requirements determine the tolerances that are applied to each feature rather than simply using the same general tolerance throughout the entire drawing. Using the appropriate tolerance for each fit helps ensure that the parts will be compatible when they are manufactured and assembled. If we had just left each of the model's tolerances up to the basic table, we could very likely find fits that are not actually compatible with what was asked for, with a sliding fit in the worst case not fitting at all or a press fit being way too loose for any actual pressure.

Another lesson I learned is how dimensioning and tolerancing communicate the design intent and functional requirements of a part. The level of detail in the tolerances can show which features are more important to the function of the design and require more attention, time, and money spent. For example, the sliding fit on Feature A and the press fit on Feature 1 each have their own specific tolerances because they are important to how the parts interact with one another; if we just generalized the tolerances, their behaviors are very likely to not work as intended. In comparison, to the other dimensions, they can use the general tolerance block because they are not as critical to the function of the assembly. This shows that tolerances are not only used to describe how accurately a part should be manufactured, but also communicate which dimensions are most important to the function of the overall design. It is almost like communicating a story to machinists without requiring a real explanation, sort of like environmental storytelling.


## Resources


