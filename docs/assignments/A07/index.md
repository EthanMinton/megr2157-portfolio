# A7 – FEA on Bracket

## Objective

The purpose of this assignment is to take our previously designed bracket using rough stress and displacement equations and apply an FEA through parametric modeling software such as SolidWorks. Create meshes with different scales to assess analysis accuracy, then iterate the design to optimize it for weight, stress handling, and displacement handling.

## Preprocessing 

Before conducting the FEA, we must establish the given constraints that we must abide by. The previous assignment gives merit to all of these values we should observe. We selected ASTM A36 steel from SolidWorks, with a Yield Strength of 36,259.4 psi and a safety factor of 4, giving a strength limit of 9,064.85 psi. Our given maximum limiting deflection is 0.005 inches. The selected applied force is 600 lbf.

<img width="523" height="270" alt="image" src="https://github.com/user-attachments/assets/6dcc4c66-e9ea-45f1-aa24-b1cb723a891f" />

Here I apply the listed material, ASTM A36 steel, to our bracket for the design.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/41b7a4fb-93f0-41aa-aa63-64967507e7d5" />

I then started by creating a new study and titling it D1, for design 1 of the model.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/8e4b0970-352b-4e7b-b33b-65052fccaad1" />

Then I went to the fixtures tab and clicked on "Fixed Geometry," and selected all of the faces found on the interior of the bracket. These faces were selected based on the pre-given prompt that these faces are the placement of attachments to the given beam. This assumption is the one that I would consider the most variable with the different kinds of surfaces you can choose with different kinds of fixed geometries. It'll truly greatly affect the given outcome based on this selection. I chose to make all the surfaces shown as fixed geometry because they are all a part of the given constraints that are listed to have a much tighter fit to the given T-beam. If I were given the time, I do believe that going into the different details would be very interesting to determine how the geometry and bracket could actually behave.

<img width="1916" height="981" alt="image" src="https://github.com/user-attachments/assets/2cbea864-0f3d-4dd4-9961-207aed8eb3a4" />

I then selected to apply an external load to the cylinder that would pull downward at 600 lbf. 

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/96fce5d0-6353-44c6-9970-46ec935caf3f" />

## Finite Element Analysis Bracket

### Design 1 
#### Mesh #1: Coarse Mesh

I started with a coarse mesh of the model as viewed below. With 1696 total elements within the mesh.

<img width="1907" height="983" alt="image" src="https://github.com/user-attachments/assets/22363fec-58d9-42a3-9ad0-fb6ffcd359de" />


##### Stress Results 
The Coarse Mesh calculated a Max Stress value of roughly 80,850 psi of stress being applied to the neck feature; this will easily fail under this load with our strength limit being only 9,064.85 psi (yield strength 36,259.4 psi). This will require design iteration to fix the design.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/1fdf3b5b-f5d2-487a-8bcd-26ac54c244be" />

With the concentration of stress at feature B, we will be required to focus our iteration efforts most on this part of the design, likely making a larger thickness for the design itself in order to compensate.

<img width="1917" height="971" alt="image" src="https://github.com/user-attachments/assets/3b384808-6f66-4178-8ef1-feea00493bd9" />

##### Displacement Results 

The Coarse mesh calculated a Max Displacement value of roughly 0.03552 inches of displacement; this fails for what we are asked for with 0.005 inches of deflection, by an order of magnitude of 7 times.

<img width="1916" height="976" alt="image" src="https://github.com/user-attachments/assets/98513b2e-6007-4e42-8680-03efd5f2b879" />

With the concentration of the displacement found at feature A, we will be required to also focus some of our iteration efforts to the cylinder part of this design. Likely requiring us to redesign the bottom section of the design entirely to ensure deflection is reduced. I will elaborate more when I initiate design 2.

<img width="1917" height="977" alt="image" src="https://github.com/user-attachments/assets/751376fe-726f-4cd9-8baf-dba7df654549" />

##### Factor of Safety Results 

The design reported a minimal Factor of Safety Result of around 0.45, which is well below the asked for value of 4, meaning we are required to make design iterations in order to achieve our asked for value.

<img width="1917" height="975" alt="image" src="https://github.com/user-attachments/assets/3223bb16-0616-41c2-a30f-f631e0f7a4f8" />

##### Mass Results 

Our estimated mass for the design was found to be 3.39 pounds, which, from the look of our plots and data, we can remove from the thickness of the latter features of our design.

<img width="473" height="192" alt="image" src="https://github.com/user-attachments/assets/3670a9e4-adb8-4e6f-9daf-107565653ff4" />

#### Mesh #2: Medium Mesh

Once I finished the Course Mesh, I then created a medium-based mesh with a projected 7364 elements found on the surface. 

<img width="1916" height="980" alt="image" src="https://github.com/user-attachments/assets/7e4e0d3d-4765-4077-bdda-e6ea31eeb672" />

##### Stress Results 

The stress results found a max stress value of 86,050 psi which, similar to the coarse mesh, was well outside of our yield strength and factor of safety. 

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/7fabe78d-cdcf-4094-947b-96082eeeeea5" />

I also want to preface that, due to the sheer number of percent difference calculations required for the assignment, I felt that it would be best to automate the process by creating a simple Excel function that could automatically and clearly produce a result for each of the values inputted; the setup is shown below.

<img width="516" height="75" alt="image" src="https://github.com/user-attachments/assets/8f7acd05-8cbe-4648-bac5-ecf9084048f4" />

Using our Excel function, we found that the percent difference between the Coarse Mesh and the Medium mesh was around 6.23%, which is below the 7% accuracy threshold.

<img width="347" height="76" alt="image" src="https://github.com/user-attachments/assets/2b5929d4-19a2-465b-bfd7-096adc49f1e9" />

##### Displacement Results

The displacement result was found to have a max displacement of around 0.03809 inches, similar to the course; this is still above the 0.005 inches required safety.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/3c5fd5a7-8814-4078-8ce3-534265f49573" />

Calculating the percent difference, we found that the difference between the 2 diplacement results was about 6.98%, just below the asked-for 7% threshold.

<img width="353" height="75" alt="image" src="https://github.com/user-attachments/assets/ed49032b-1c23-4b6e-a10c-371e0e674822" />

##### Factor of Safety Results

Our Factor of Safety was found to be 0.42, which is similar to the course mesh but still well below the requested safety factor of 4.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/1eeddd33-4171-4350-af42-2e0a26847099" />

Calculating the percent difference, we found that our value was roughly 6.9% different, just below the asked for threshold of 7%.

<img width="356" height="72" alt="image" src="https://github.com/user-attachments/assets/c2f53958-680c-4406-89a2-e68b8b4e0df4" />

##### Mass Results
Our estimated mass for the design was found to be 3.39 pounds; this is the same as the previous mesh, as it shouldn't have any effect on the true mass calculations.

<img width="473" height="192" alt="image" src="https://github.com/user-attachments/assets/3670a9e4-adb8-4e6f-9daf-107565653ff4" />

##### Final Results 

From our collected data from the first Design Test, we found that the 2 biggest issues with the design are the Stress concentrations found in the connection of feature A and feature B, and the deflection concentrations at the tip of feature A. This was observed in both the Coarse and the Medium meshes performed in similar capacities. This is where we will prioritize our design modification for Design 2.

| Mesh Type | Coarse Mesh | Medium Mesh | Fine Mesh |
| --- | --- | --- | --- |
| Max Stress (psi) | 80,850 | 86,050 | NA |
| Max Displacement (in) | 0.03552 | 0.03809 | NA |
| Factor of Safety | 0.45 | 0.42 | NA |
| Mass (lbs) | 3.39 | 3.39 | NA |
| Element Count | 1696 | 7364 | NA |


### Design 2

From our collected data, I decided to first iterate on the main points of contention of the design with Feature A and Feature B. Attempting to find a solution that works best and knocks out two birds with one stone, I decided to try and form a sort of bridge between Feature A and 2 Feature Bs. This would help to prevent any concentration of stress in the design by distributing it across two features/bodies; it would also help with reducing concentrations of deflections at the tip of Feature A by removing a floating tip and forming a connected bridge instead.

I started first by creating a copy of the model and setting the extrusion of Feature A to the same variable "PRIMARY_THICKNESS" at a value of 2 inches.

<img width="1916" height="977" alt="image" src="https://github.com/user-attachments/assets/2afde315-c7ee-4c33-b015-e3faf9323c61" />

I then created a rectangle aligned and constrained directly to the opposing Feature B, allowing it to be parametrically modeled.

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/9b87a398-91da-4b25-9857-94fdeea7f981" />

It was then extruded by the same parametric variable "THICKNESS_B" at 0.15 inches.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/d59c9099-8129-4796-8af3-3192c9434d3c" />

I then added a 0.20-inch fillet to the corners where Feature B meets the bottom of Feature C to help reduce stress concentrations further.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/1f976c42-2eff-4927-87ef-d67d5b0ea26d" />

In an attempt to reduce the weight, I also divided all of my parametric equations used to calculate the different dimensions by a factor of 2. I did this to reduce the overall weight of the design, as I had observed that in the FEA, the areas of Features C, D, and E all have very few issues or stress concentrations. If this is an overcorrection or an undercorrection, these values will be independently altered.

<img width="1902" height="431" alt="image" src="https://github.com/user-attachments/assets/b5972e07-ad60-40fc-b5de-2d03296ad36c" />

All of these alterations leave us with a design looking like the model below.

<img width="1911" height="982" alt="image" src="https://github.com/user-attachments/assets/bdede94f-4c27-42e5-85e9-87c3219880af" />

#### Mesh #1: Coarse Mesh 

Reutilizing the previous study from Design #1, we are able to avoid having to preprocess the model all over again as it all transferred without issue, although I am now required to create a new Coarse mesh to accommodate all of the alterations. The new coarse mesh has 2274 elements.

<img width="1917" height="1137" alt="image" src="https://github.com/user-attachments/assets/4141bd54-30a9-4e59-a965-cf47d8a1a5d0" />

##### Stress Results 

The Coarse mesh calculated a maximum stress of 4,065 psi, well below our maximum allowed stress value of 9,064.85 psi. This means that our second design is currently meeting the requirements for strength against stress.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/cc3e92a3-eaa4-4656-8d0a-4a61bd31b92d" />

Thanks to the fillets, the model's stress concentration is found to be much lower in Feature B's body, with it peaking well below our allowed limit.

<img width="1916" height="985" alt="image" src="https://github.com/user-attachments/assets/bbefe2cd-20ad-4b73-b40c-23ec6825c2ea" />

##### Displacement Results

The coarse mesh calculated a max displacement of 0.0001494 inches, which is below our required displacement limit of 0.005 inches. This means that our second design is currently meeting the requirements for rigidity.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/9e48e74f-5024-4fdd-bc64-288d0311ce21" />

This concentration of displacement is found to be in the center of Feature A, which makes sense with both sides of Feature B supporting the feature from each side.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/40ac50bd-b4ae-4de2-92e5-33b956501d53" />

##### Factor of Safety Results

The Found minimum factor of safety in the design was roughly 8.9, which is well above the required factor of safety of 4.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/8adbf76c-ca85-4fa2-8f57-e73c04ffb100" />

##### Mass Results

The reduced mass of the design was 2.06 lbs. This is roughly a 1.3 lbs reduction from the previous design, and with our model now meeting stress and displacement requirements, I can focus much more on reducing the overall weight for the next design iteration.

<img width="451" height="120" alt="image" src="https://github.com/user-attachments/assets/83bf6fd5-8f37-460f-9aa6-fce8251420e1" />

#### Mesh #2: Medium Mesh

The second mesh I created for Design #2 contains 6281 elements within its body.

<img width="1907" height="982" alt="image" src="https://github.com/user-attachments/assets/a8450d23-9f77-451e-9627-7a0e0758cfb2" />

##### Stress Results

For the Medium Mesh, it was found that the maximum stress calculated was 4,168 psi; this is similar to the coarse mesh as it is also well below the maximum allowable stress threshold.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/2240cab3-638b-4821-9c5d-a7ffebc36b14" />

Similar to the coarse mesh, the concentration was found within the same general location within Feature B on both sides.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/84886309-7b67-4f21-a7b2-467c75bee070" />

Using our Excel sheet, we find that the percent difference is an incredibly small 2.5%, which is well below the 7% threshold asked for accuracy.

<img width="343" height="85" alt="image" src="https://github.com/user-attachments/assets/ffa6cddd-c4fb-46d0-a081-9624a4adf8a6" />

##### Displacement Results

For the medium mesh, it was found that the maximum deflection was 0.0001509 inches.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/0d634676-003f-440f-be81-44a03422169a" />

Its concentration is found roughly in the same spot as the coarse mesh predicted, in the center of Feature A.

<img width="1912" height="980" alt="image" src="https://github.com/user-attachments/assets/b901a2bf-2474-4e23-b8d9-228db05c439b" />

Using our percent difference calculator, we find that the difference between the Coarse mesh and the Medium mesh is 0.999%. These are very accurate to each other and are found well below the 7% threshold.

<img width="346" height="90" alt="image" src="https://github.com/user-attachments/assets/be78dcd6-77f4-468d-95a3-40d102e734fd" />

##### Factor of Safety Results

The calculated value for the minimum safety factor for the medium mesh is at 8.7. This is well above the limiting value of 4 given by the assignment.

<img width="1917" height="986" alt="image" src="https://github.com/user-attachments/assets/72c683a3-094e-4ce0-9c1c-13d50408a73e" />

Calculating the percent difference between the 2 found safety factors, we get a value of 2.27% below the 7% threshold.

<img width="350" height="95" alt="image" src="https://github.com/user-attachments/assets/7a31d910-3dde-49dc-9322-41c4bd9e9acc" />

##### Mass Results

The reduced mass of the design was 2.06 lbs. The mesh size does not affect the estimated values within our model.

<img width="451" height="120" alt="image" src="https://github.com/user-attachments/assets/83bf6fd5-8f37-460f-9aa6-fce8251420e1" />


##### Final Results 

From our collected data from the second Design Test, we found that our changes successfully fixed the stress and deflection issues. Both the Coarse and Medium meshes showed similar results that met all requirements. However, with a factor of safety around 8.7, the design is currently stronger than it needs to be. This is where we will prioritize our design modifications for Design 3, focusing on reducing the overall weight.

| Mesh Type | Coarse Mesh | Medium Mesh | Fine Mesh |
| --- | --- | --- | --- |
| Max Stress (psi) | 4,065 | 4,168 | NA |
| Max Displacement (in) | 0.0001494 | 0.0001509 | NA |
| Factor of Safety | 8.9 | 8.7 | NA |
| Mass (lbs) | 2.06 | 2.06 | NA |
| Element Count | 2274 | 6281 | NA |

### Design #3

For design #3, my main priority was to reduce the overall weight of the design while also ensuring that our max stress calculations do not exceed our previously established limits. In order to do this, I went back to the parametric equations and changed the division by a factor of 2 on the "HEIGHT_C" and "LENGTH_D" to a factor of 5. This greatly reduced the size of the non-affecting sides of the bracket.

<img width="1778" height="330" alt="image" src="https://github.com/user-attachments/assets/c7b4d65d-6309-4511-b98a-8d65701da0d2" />

If I were given the chance to have more time and ability to redesign the bracket, I would attempt to thin the walls even more while simultaneously cutting out full parts, such as an "X" design, to maintain structural stability while also reducing weight even further. My goal with design #3 was to get down to roughly a pound of material while maintaining stability. I would have gone even more extreme if I hadn't feared it would cause the design to fail.

#### Mesh #1: Coarse Mesh

The first mesh I created here was a coarser mesh with an element count of 2352.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/f8c6feea-1a4f-4e97-a6e0-d1589e28a0a9" />

##### Stress Results

The maximum stress value that was calculated by the study was similar to the previous design, at around 4,103 psi. 

<img width="1916" height="980" alt="image" src="https://github.com/user-attachments/assets/01a87b80-07e9-4595-83d8-b89cd5af60b4" />

Its concentration was found at a very similar position in the center of Feature B. This is expected with the previous changes made in design 2 to compensate for the concentrations at the corner; the stress has shifted.

<img width="1916" height="985" alt="image" src="https://github.com/user-attachments/assets/e4622b43-9ad8-41bf-aa54-4f63f5866b95" />


##### Deflection Results

The maximum deflection value that was calculated by the study was similar to the previous design at 0.0001422 inches.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/d5604700-e3b7-4b30-965f-879a8b0694eb" />

Its concentration was found at the center of Feature A, which is similar to the previous design. This makes sense; with Feature B supporting it on either side, it leaves the center the most unsupported and susceptible to deflection.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/5fc57726-b4b6-42e1-b656-6e2e1aecb7dd" />

##### Safety Factor Results 

The minimum factor of safety calculated by the mesh was 8.8, above our given limit of 4.

<img width="1915" height="982" alt="image" src="https://github.com/user-attachments/assets/d10dcf34-dedb-4e52-af5f-e742bc8641d2" />


##### Mass Results

For design #3 in the coarse mesh, our design is estimated to have a weight of 1.04 lbs.

<img width="471" height="168" alt="image" src="https://github.com/user-attachments/assets/d07ccc07-9303-45db-818c-c674e9e3a1f9" />


#### Mesh #1: Medium Mesh

The medium mesh for Design 3 had an element count of 5208 elements.

<img width="1917" height="986" alt="image" src="https://github.com/user-attachments/assets/f6c2a38b-3a95-4fa0-b605-1011ba61f268" />


##### Stress Results

The Medium Mesh projected the Bracket to have a max stress of 4199 psi.

<img width="1917" height="986" alt="image" src="https://github.com/user-attachments/assets/9a232597-16e2-42d0-ad14-313d00a2c15d" />

This maximum stress is similarly located as in the previous test within the center of feature B.

<img width="1917" height="983" alt="image" src="https://github.com/user-attachments/assets/6dcb4a77-689e-4299-bfc5-7cfd75330a24" />

Utilizing our Percent Difference Calculator, we find that our difference was roughly 2.31%, well below the 7% threshold.

<img width="342" height="85" alt="image" src="https://github.com/user-attachments/assets/14de2a37-137d-4d8d-a073-8ba1c72146df" />

##### Deflection Results

The maximum calculated deflection is found to be 0.0001429 inches.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/57b5ffc6-e344-479b-a69a-42dd642bd14f" />

Similar to all other deflections, post design #1: our concentration is found on the center of Feature A.

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/91761713-affc-4057-8c93-b312c5bd3188" />

Comparing 0.0001429 inches from this result and 0.0001422 inches from the coarse mesh, we find a 0.49% difference.

<img width="347" height="80" alt="image" src="https://github.com/user-attachments/assets/bc114841-1090-4171-84e7-4862fa4eb8bb" />


##### Factor of Safety Design 

The minimum listed Factor of Safety from the Medium Mesh is 8.6.

<img width="1916" height="983" alt="image" src="https://github.com/user-attachments/assets/135c444e-5127-4b95-b799-0163de0d8247" />

The calculated percent difference is 2.35% between the Coarse and Medium Mesh.

<img width="336" height="97" alt="image" src="https://github.com/user-attachments/assets/43291f0a-dd5b-450f-b157-8650b2e971dd" />

##### Mass Results

For design #3 in the Medium mesh, our design is estimated to have a weight of 1.04 lbs.

<img width="471" height="168" alt="image" src="https://github.com/user-attachments/assets/d07ccc07-9303-45db-818c-c674e9e3a1f9" />

##### Finalize Results 

Despite attempting to reduce the overall size of the model to decrease the weight, it seemed to have very little impact on our stress and displacement values. Even observing the walls of the brackets, they still were colored a deep blue. I remember specifically when attempting the calculation for the Features in A5's assignment, the thicknesses I initially calculated using a different formula were incredibly thin to the point where they were minute fractions of an inch. If I were to attempt a 4th design, I would reduce the wall thickness even further to test the limit of the walls.

| Mesh Type | Coarse Mesh | Medium Mesh | Fine Mesh |
| --- | --- | --- | --- |
| Max Stress (psi) | 4,103 | 4,199 | NA |
| Max Displacement (in) | 0.0001422 | 0.0001429 | NA |
| Factor of Safety | 8.8 | 8.6 | NA |
| Mass (lbs) | 1.04 | 1.04 | NA |
| Element Count | 2352 | 5208 | NA |


## Finite Element Analysis Link

The next step of the assignment is to take the link we have been producing in parallel to the bracket and apply similar constraints to test the stress, Factor of Safety, and deflections.

### Preprocessing 

I first started by creating a Static study for our link, naming it "D2".

<img width="1917" height="985" alt="image" src="https://github.com/user-attachments/assets/7cceb510-3220-41cd-82aa-3545e49bc946" />

I then created a fixed surface on the face that connects to Feature A, which corresponds to the smaller-radius hole.

<img width="1917" height="976" alt="image" src="https://github.com/user-attachments/assets/0e0048ba-53b3-4fbf-8d8a-bec5b6b89f99" />

I then applied a 600 lbf downward force to the second hole, measured at 1 inch.

<img width="1916" height="981" alt="image" src="https://github.com/user-attachments/assets/bc80a07b-3ae2-4c45-9720-8b19d6550974" />

I then set the material to ASTM A36 steel, which is the exact same material type as used on the bracket.

<img width="1915" height="982" alt="image" src="https://github.com/user-attachments/assets/1a0a774a-054d-4066-ab5c-83e8f7a96e36" />


### Design #1

#### Mesh #1: Coarse Mesh

I started with a coarse mesh of the link model, resulting in 2335 total elements within the mesh.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/2043d278-1e11-42b2-8d8b-60aedb4404f6" />

##### Stress Results

The coarse mesh calculated a maximum stress value of 17,210 psi, which is below our material yield strength of 36,259.4 psi.

<img width="1912" height="985" alt="image" src="https://github.com/user-attachments/assets/b9be5a6e-4efa-4efa-b7c2-76fa951c999a" />

Looking at the stress plot, the concentration of stress is found primarily along the left and right interior edges of the force-applied hole.

<img width="1916" height="980" alt="image" src="https://github.com/user-attachments/assets/d7276679-58b5-4050-9d1d-c21c2965a004" />

##### Deflection Results

The coarse mesh calculated a maximum displacement value of 0.0008286 inches, which is well below our maximum allowable deflection limit of 0.005 inches.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/b219e06c-93f4-434e-bf2e-d20f6d58abb4" />

The concentration of displacement was observed mainly at the bottom edge of the hole where the downward force was applied.

<img width="1860" height="900" alt="image" src="https://github.com/user-attachments/assets/d7276679-58b5-4050-9d1d-c21c2965a004" />

##### Factor of Safety Results

The model reported a minimum Factor of Safety result of around 2.1, which fails our target requirement of 4. This means we will need to make design iterations to achieve our required safety factor.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/a5c59fca-81c4-49ff-a326-af20872c9034" />

##### Mass Results

Our estimated mass for the initial link design was found to be 0.09 pounds.

<img width="475" height="162" alt="image" src="https://github.com/user-attachments/assets/0dade6b0-bd82-40ec-b6b7-4fa1cee3e1a0" />

#### Mesh #2: Medium Mesh

Once I finished the coarse mesh study, I created a medium-based mesh with an element count of 6274 elements on the model.

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/1821c2cc-24fc-4291-ac31-b86030583fff" />

##### Stress Result

For the medium mesh, the study found a maximum stress of 17,370 psi.

<img width="1916" height="985" alt="image" src="https://github.com/user-attachments/assets/013d1b01-fffa-48a4-99a9-f6c57746dd1a" />

Similar to the coarse mesh, the stress concentration was found in the exact same location along the left and right edges of the loaded hole.

<img width="1917" height="983" alt="image" src="https://github.com/user-attachments/assets/c4d10f5f-f66d-4a1d-b57c-7b39641e482b" />

Using our Excel function, we calculated the percent difference between the coarse and medium mesh stress results to be roughly 0.93%, which is well below our 7% accuracy threshold.

<img width="362" height="87" alt="image" src="https://github.com/user-attachments/assets/a9b800b8-667e-4c4d-94f8-05a8196d834e" />

##### Displacement Result 

The medium mesh yielded a maximum displacement value of 0.0008291 inches.

<img width="1916" height="978" alt="image" src="https://github.com/user-attachments/assets/8103fc4d-3caf-4824-9ad1-769a2d1ef1bb" />

The deflection was concentrated in the same spot at the bottom of the loaded hole as predicted by the coarse mesh.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/a206d825-1609-4627-a32e-2444503b2d1d" />

Calculating the percent difference, we found that the difference between the two displacement results was about 0.06%, easily satisfying the 7% threshold.

<img width="365" height="90" alt="image" src="https://github.com/user-attachments/assets/0690c87b-e50e-4c1b-8b18-934474f42d2b" />

##### Factor of Safety Results

<img width="1916" height="983" alt="image" src="https://github.com/user-attachments/assets/8cd0da3e-a2de-4caa-9871-799d833d1e28" />

Our calculated minimum Factor of Safety remained at 2.1. Calculating the percent difference, we found a 0% difference between the two meshes, though it still falls well short of our required safety factor of 4.

##### Mass Results

The estimated mass remained identical at 0.09 pounds, as changing the mesh density does not impact the total weight of the design.

<img width="473" height="167" alt="image" src="https://github.com/user-attachments/assets/37f7c887-c606-49b5-a471-2f3dc6da7db4" />

##### Finalized Results

From our initial link study, the primary issue was failing to meet the Factor of Safety threshold, resulting in a minimum FOS of 2.1 rather than 4. Stress and deflection concentrations both occurred around the loaded hole, requiring an increase in structural thickness for Design 2.

| Mesh Type | Coarse Mesh | Medium Mesh | Fine Mesh |
| --- | --- | --- | --- |
| Max Stress (psi) | 17,210 | 17,370 | NA |
| Max Displacement (in) | 0.0008286 | 0.0008291 | NA |
| Factor of Safety | 2.1 | 2.1 | NA |
| Mass (lbs) | 0.09 | 0.09 | NA |
| Element Count | 2335 | 6274 | NA |

### Design #2

One of the biggest failures of the first link design was failing to meet the required Factor of Safety of 4, as it resulted in a minimum Factor of Safety of only 2.1. To combat this, I decided to multiply the thickness equation by a factor of 2.5 to compensate for the safety factor and to reduce peak stress levels throughout the component. This will allow the model to withstand stress without failure.

<img width="1667" height="518" alt="image" src="https://github.com/user-attachments/assets/f0945714-be68-499b-98d5-a4566d08d266" />

I then applied a 0.50-inch filleted edge to the four outer corners of the design to remove unnecessary material that contributes very little to overall structural strength.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/2645f28e-06d5-4af0-ae0c-8197c9c098e2" />

#### Mesh #1: Coarse Mesh 

I created a new coarse mesh for Design 2, which resulted in 1950 total elements.

<img width="1916" height="980" alt="image" src="https://github.com/user-attachments/assets/5c1f63ad-dd63-449a-9066-2138779e99c3" />

##### Stress Results 

The coarse mesh calculated a maximum stress of 6,918 psi, which is well below our maximum allowable yield stress.

<img width="1916" height="977" alt="image" src="https://github.com/user-attachments/assets/6bdcef68-4d79-41a8-b9d9-a77502c82b74" />

The concentration was found in the same area as the first stress concentration, located on the left and right sides of the force-applied hole.

<img width="1917" height="977" alt="image" src="https://github.com/user-attachments/assets/7bfb189e-223c-4b1c-917f-d84bd0b75435" />

##### Deflection Results

The maximum displacement calculated by the coarse mesh was 0.0003332 inches, which easily satisfies our 0.005-inch deflection limit.

<img width="1912" height="988" alt="image" src="https://github.com/user-attachments/assets/131ea032-f0bf-440a-a52b-d1d99e11773a" />

The concentration was found in the exact same spot at the bottom edge of the force-applied hole.

<img width="1915" height="982" alt="image" src="https://github.com/user-attachments/assets/8c528647-883a-4830-9008-d717ce660dc1" />

##### Factor of Safety Results 

The calculated minimum Factor of Safety for this design was roughly 5.2, which is well above our target requirement of 4.

<img width="1915" height="986" alt="image" src="https://github.com/user-attachments/assets/1cec05b7-d450-4505-b935-084c21f34dd3" />

##### Mass Results 

The mass for Design 2 increased to 0.21 pounds due to the increased wall thickness.

<img width="478" height="162" alt="image" src="https://github.com/user-attachments/assets/81644bc5-0be9-4fc3-96b0-8f9a888ce237" />

#### Mesh #2: Medium Mesh

I then created a medium mesh for Design 2, which contained 6549 elements within its body.

<img width="1907" height="987" alt="image" src="https://github.com/user-attachments/assets/8cb2fb2f-f9e2-46ab-997b-c8f94e8ca0e2" />

##### Stress Results

For the medium mesh, it was found that the maximum calculated stress was 6,928 psi.

<img width="1916" height="987" alt="image" src="https://github.com/user-attachments/assets/4ff69393-4b40-4928-ab66-456a942ba457" />

The concentration was located in the exact same spot on the left and right edges of the loaded hole.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/c7de4789-caff-4446-ae6f-e91bb03bfe4d" />

Using our Excel sheet, we calculated the percent difference to be roughly 0.144%, which is well below the 7% accuracy threshold.

<img width="362" height="83" alt="image" src="https://github.com/user-attachments/assets/31ed8984-2cac-41e3-b039-d53d8798084b" />

##### Deflection Results

For the medium mesh, the maximum deflection was found to be 0.0003342 inches.

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/3dae207f-26ad-4779-a9cc-4deadcc7e5bd" />

Its concentration was located in the same spot as predicted by the coarse mesh.

<img width="1916" height="980" alt="image" src="https://github.com/user-attachments/assets/eddec99a-96b3-4861-ad80-44176fe0a69f" />

Calculating the percent difference, we found a 0.3% difference between the two meshes, which is well below the 7% threshold.

<img width="360" height="87" alt="image" src="https://github.com/user-attachments/assets/80a7fd03-4bc4-4b0a-9136-0e7d6dd42224" />

##### Factor of Safety Results

The calculated minimum Factor of Safety remained at 5.2.

<img width="1916" height="991" alt="image" src="https://github.com/user-attachments/assets/8973e579-fd3d-40f2-b287-3f9bc420ccc6" />

Comparing this to the coarse mesh yields a 0% difference, confirming high convergence accuracy.

##### Mass Results 

The estimated mass remained at 0.21 pounds.

<img width="478" height="162" alt="image" src="https://github.com/user-attachments/assets/81644bc5-0be9-4fc3-96b0-8f9a888ce237" />

##### Finalized Results 

Link Design 2 successfully passed all strength, safety factor, and deflection criteria. However, with an FOS of 5.2 exceeding our goal of 4, the part is slightly overbuilt, giving room for weight reduction in Design 3.

| Mesh Type | Coarse Mesh | Medium Mesh | Fine Mesh |
| --- | --- | --- | --- |
| Max Stress (psi) | 6,918 | 6,928 | NA |
| Max Displacement (in) | 0.0003332 | 0.0003342 | NA |
| Factor of Safety | 5.2 | 5.2 | NA |
| Mass (lbs) | 0.21 | 0.21 | NA |
| Element Count | 1950 | 6549 | NA |

### Design #3

In an attempt to reduce the overall weight of the link while maintaining structural integrity, I decided to reduce the thickness multiplier from 2.5 down to 2.0. This should reduce total mass while ensuring that the component can still safely withstand the applied forces.

<img width="1663" height="513" alt="image" src="https://github.com/user-attachments/assets/98cfecf0-82f5-4bef-b197-c2cc41d2bfc8" />

#### Mesh #1: Coarse Mesh

The coarse mesh created for Design 3 had an element count of 1679 elements.

<img width="1917" height="977" alt="image" src="https://github.com/user-attachments/assets/f5086d8f-5294-4822-9f84-16e7451a1678" />

##### Stress Results

The maximum stress calculated by the coarse mesh was 8,624 psi, which remains well below our allowable yield stress.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/86c7714c-8275-4d69-8638-c0c947353723" />

The stress concentration was located in the exact same place on the left and right sides of the force-applied hole.

<img width="1916" height="977" alt="image" src="https://github.com/user-attachments/assets/25c21926-af82-454a-a361-42fef3329e7f" />

##### Displacement Results

The maximum displacement calculated was 0.0004167 inches, remaining well within the allowable 0.005-inch deflection limit.

<img width="1916" height="976" alt="image" src="https://github.com/user-attachments/assets/a981a10c-e5bc-4809-8646-8d31deac128d" />

The concentration was found at the bottom edge of the force-applied hole.

<img width="1916" height="980" alt="image" src="https://github.com/user-attachments/assets/5bb95a72-aba6-434d-887b-dc62c51daec1" />

##### Factor of Safety Result

The minimum Factor of Safety calculated was 4.2, which successfully meets our given limit of 4.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/9a85acc6-722d-46e0-8cba-7cef39af480a" />

##### Mass Results 

The estimated mass for Design 3 was reduced to 0.17 pounds.

<img width="472" height="126" alt="image" src="https://github.com/user-attachments/assets/d189efdf-5904-4b2c-ba9d-fbfd767e5626" />

#### Mesh #2: Medium Mesh

I then ran a medium mesh study on Design 3, which generated an element count of 7537 elements.

<img width="1910" height="988" alt="image" src="https://github.com/user-attachments/assets/b83285c1-a45a-4cf9-87e4-f5e279576e66" />

##### Stress Results

The medium mesh projected a maximum stress of 8,665 psi. 
<img width="1916" height="985" alt="image" src="https://github.com/user-attachments/assets/191cf349-6458-46cb-b7e9-6d121793f093" />

Similar to the coarse mesh, the stress concentration was located along the left and right interior edges of the loaded hole.

<img width="1916" height="977" alt="image" src="https://github.com/user-attachments/assets/af542b18-bfa6-46bd-962d-f21907d03808" />

Utilizing our percent difference calculator, we found a 0.48% difference between the coarse and medium meshes, easily passing our 7% convergence threshold.
 
<img width="370" height="85" alt="image" src="https://github.com/user-attachments/assets/876a28e1-fbb9-4992-bf23-ab639d6f8b58" />

##### Deflection Results

The maximum calculated deflection was found to be 0.0004175 inches. 
<img width="1916" height="983" alt="image" src="https://github.com/user-attachments/assets/026bd98f-2dc1-46da-adfd-c96f9dce7fb9" />

Concentrated in the same region at the bottom of the loaded hole. 

<img width="1917" height="977" alt="image" src="https://github.com/user-attachments/assets/ba5c4e78-a3c9-4197-b9f5-a6c83b602738" />

Comparing this with the coarse mesh result (0.0004167 inches) gives a percent difference of 0.19%, well below the 7% threshold.

<img width="372" height="85" alt="image" src="https://github.com/user-attachments/assets/3b761afc-0270-427c-8129-afe876915144" />

##### Factor of Safety Results

The minimum listed Factor of Safety from the medium mesh was 4.2

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/b072071b-7921-4038-b1af-8e91c8de3179" />

Calculating the percent difference between the coarse and medium mesh yields a 0% difference, confirming mesh convergence and satisfying the target safety factor.

##### Mass Results 

The final estimated mass for Design 3 in the medium mesh remained at 0.17 pounds.

<img width="472" height="126" alt="image" src="https://github.com/user-attachments/assets/d189efdf-5904-4b2c-ba9d-fbfd767e5626" />

##### Finalized Results 

By reducing the thickness multiplier to 2.0, Design 3 hit our target Factor of Safety of 4.2 while shaving off unnecessary weight, making it the optimal link configuration.

| Mesh Type | Coarse Mesh | Medium Mesh | Fine Mesh |
| --- | --- | --- | --- |
| Max Stress (psi) | 8,624 | 8,665 | NA |
| Max Displacement (in) | 0.0004167 | 0.0004175 | NA |
| Factor of Safety | 4.2 | 4.2 | NA |
| Mass (lbs) | 0.17 | 0.17 | NA |
| Element Count | 1679 | 7537 | NA |

## Lessons Learned

### Bracket Summary 

| Metric | Design #1 (Converged) | Design #2 (Converged) | Design #3 (Converged) | Limit / Goal |
| :--- | :--- | :--- | :--- | :--- |
| **Max Stress & Location** | 86,050 psi (Neck / Top-Feature B Connection) | 4,168 psi (Center of Feature B Body) | 4,199 psi (Center of Feature B Body) | $\le 9,064.85 \text{ psi}$ |
| **Max Deflection & Location** | 0.03809 in (Tip of Feature A Cylinder) | 0.0001509 in (Center Span of Feature A Bridge) | 0.0001429 in (Center Span of Feature A Bridge) | $\le 0.005 \text{ in}$ |
| **Mass** | 3.39 lbs | 2.06 lbs | 1.04 lbs | Minimize |
| **Safety Factor** | 0.42 | 8.7 | 8.6 | $\ge 4.0$ |
| **Number of Elements** | 7,364 | 6,281 | 5,208 | Convergence $< 7\%$ |

### Link Summary (2157)

| Metric | Design #1 (Converged) | Design #2 (Converged) | Design #3 (Converged) | Limit / Goal |
| :--- | :--- | :--- | :--- | :--- |
| **Max Stress & Location** | 17,370 psi ( Left/Right Sides of Loaded Hole Interior Edges) | 6,928 psi (Left/Right Sides of Loaded Hole Interior Edges) | 8,665 psi (Left/Right Sides of Loaded Hole Interior Edges) | $\le 9,064.85 \text{ psi}$ |
| **Max Deflection & Location** | 0.0008291 in (Bottom Rim of Loaded Hole) | 0.0003342 in (Bottom Rim of Loaded Hole) | 0.0004175 in (Bottom Rim of Loaded Hole) | $\le 0.005 \text{ in}$ |
| **Mass** | 0.09 lbs | 0.21 lbs | 0.17 lbs | Minimize |
| **Safety Factor** | 2.1 | 5.2 | 4.2 | $\ge 4.0$ |
| **Number of Elements** | 6,274 | 6,549 | 7,537 | Convergence $< 7\%$ |

### Lessons

Looking back at this assignment, one of the biggest things I learned was just how different the FEA results were compared to our initial rough hand calculations from A5. I understood that with hand calculations, we used simple formulas that assume the load is spread out evenly across a basic shape, and how much of our assumptions are actually just flat-out incorrect. But when I ran Design #1 through FEA, I was so surprised by how off they were; it showed a massive stress concentration at the neck that jumped to over 80,000 psi. Hand calculations completely missed those stress points because FEA takes into account the full 3D geometry and feature transitions, showing where the stress actually builds up in a real-life scenario.

I also learned a lot about how SolidWorks actually processes the data behind the scenes during a study. Instead of looking at the bracket or link as one solid piece, the software breaks the whole design down into thousands of these tiny elements connected at nodes. When we apply our fixed geometry constraints and the 600 lbf load, it calculates how much each point moves first, and then uses that displacement to figure out the stress in those areas. This showed me why setting up the fixtures correctly during preprocessing is so important, because selecting the wrong face changes how the load travels through the whole part.

Running the inner loop tests showed me how much mesh size changes both our results and the software's performance. The coarse mesh was efficient for running quick tests to see where stress and deflection were concentrated, but because the elements are larger, it can smooth out peak values in tight corners. Switching to a medium mesh added a lot more elements in those tight areas, like around Feature B on the bracket and the interior of the link hole, giving us a much more accurate peak stress value. Using the Excel calculator I made for the percent differences made it easy to verify when our results converged below the 7% threshold, proving our data was accurate without having to waste time running an overly fine mesh.

Overall, seeing where the stress plots stayed deep blue showed me exactly where I could shave off material to get the weight down to 1.04 lbs, while adding fillets and the bridge feature to strengthen the high-stress spots. It made me realize how useful FEA is as a design tool rather than just a final test, helping to guide decisions on where to add or remove material.

### Time Taken
Once the assignment was completed, I spent roughly 12 hours on everything, mostly on organizing and expressing all results, explanations, and documentation. The FEA was simple to carry out, with all of the data being easy to access and understand. I'd say the biggest mistake I made was the technique I utilized in order to copy and explain the data down in the documentation was pretty inefficient until the near end where I was able to accelerate my process.

### CAD Files
