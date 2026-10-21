# A7 – FEA on Bracket

## Objective

The purpose of this Assignment is to take our previously designed bracket using rough stress and displacement equations and apply an FEA through parametric modeling software such as SolidWorks. Create meshes with different scales to assess analysis accuracy, then iterate the design to optimize it for weight, stress handling, and displacement handling.

## Preprocessing 

Before conducting the FEA, we must establish the given constraints that we must abide by. The previous assignment gives merit to all of these values we should observe. We selected ASTM A36 steel from SolidWorks, with a Yield Strength of 36,259.4 psi and a safety factor of 4, giving a strength limit of 9,064.85 psi. Our given maximum limiting deflection is 0.005 inches. The selected applied force is 600 lbf. 

<img width="523" height="270" alt="image" src="https://github.com/user-attachments/assets/6dcc4c66-e9ea-45f1-aa24-b1cb723a891f" />

Here I apply the listed material, ASTM A36 steel, to our bracket for the design.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/41b7a4fb-93f0-41aa-aa63-64967507e7d5" />

I then started by creating a new study and titling it D1, for design 1 of the model.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/8e4b0970-352b-4e7b-b33b-65052fccaad1" />

Then I went to the fixtures tab and clicked on "Fixed Geometry," and selected all of the faces found on the interior of the bracket. These faces were selected based on the pre-given prompt that these faces are the placement of attachments to the given beam. 

<img width="1916" height="981" alt="image" src="https://github.com/user-attachments/assets/2cbea864-0f3d-4dd4-9961-207aed8eb3a4" />

I then selected to apply an external load to the cylinder that would pull downward at 600 lbf. 

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/96fce5d0-6353-44c6-9970-46ec935caf3f" />

## Finite Element Analysis 

### Design 1 
#### Mesh #1: Coarse Mesh

I started with a coarse mesh of the model as viewed below. With 1696 total elements within the mesh.

<img width="1907" height="983" alt="image" src="https://github.com/user-attachments/assets/22363fec-58d9-42a3-9ad0-fb6ffcd359de" />


##### Stress Results 
The Course Mesh calculated a Max Stress value of roughly 80,850 psi of stress being applied to the neck feature; this will easily fail under this load with our strength being only 36,259.4psi. This will require design iteration to fix the design.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/1fdf3b5b-f5d2-487a-8bcd-26ac54c244be" />

With the concentration of stress at feature B, we will be required to focus our iteration efforts most on this part of the design, likely making a larger thickness for the design itself thicker in order to compensate.

<img width="1917" height="971" alt="image" src="https://github.com/user-attachments/assets/3b384808-6f66-4178-8ef1-feea00493bd9" />

##### Displacement Results 
The Course mesh calculated a Max Displacement value of roughly 0.03552 inches of displacement; this fails for what we are asked for with 0.005 inches of deflection, by an order of magnitude of 7 times. 

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

The stress results found a max stress value of 86,050 psi which similar to the coarse mesh, was well outside of our yield strength and factor of safety. 

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/7fabe78d-cdcf-4094-947b-96082eeeeea5" />

I also want to preface that, due to the sheer number of percent difference calculations required for the assignment I felt that it would be best to automate the process by creating a simple Excel function that could automatically and clearly produce a result for each of the values inputted; the setup is shown below.

<img width="516" height="75" alt="image" src="https://github.com/user-attachments/assets/8f7acd05-8cbe-4648-bac5-ecf9084048f4" />

Using our Excel function, we found that the percent difference between the Course Mesh and the Medium mesh was around 6.23%, which is below the 7% accuracy threshold. 

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

From our collected data, I decided to first iterate on the main points of contention of the design with Feature A and Feature B, attempting to find a solution that works best and knocks out 2 birds with one stone I decided to try and form a sort of bridge between Feature A and 2 Feature B. This would help to prevent any concentration of stress in the design by distributing it to 2 features/bodies; it would also help with reducing concentrations of deflections at the tip of Feature A by removing a tip and only having a bridge.

I started first by creating a copy of the model and setting the extrusion of Feature A to the same variable "PRIMARY_THICKNESS" at a value of 2 inches.

<img width="1916" height="977" alt="image" src="https://github.com/user-attachments/assets/2afde315-c7ee-4c33-b015-e3faf9323c61" />

I then created a rectangle aligned and constrained directly to the opposing Feature B, allowing for it to be parametrically modeled.

<img width="1917" height="981" alt="image" src="https://github.com/user-attachments/assets/9b87a398-91da-4b25-9857-94fdeea7f981" />

It was then extruded by the same parametric variable "THICKNESS_B" at 0.15 inches.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/d59c9099-8129-4796-8af3-3192c9434d3c" />

I then added a 0.20-inch fillet to the corners where Feature B meets the bottom of Feature C to help reduce stress concentrations further.

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/1f976c42-2eff-4927-87ef-d67d5b0ea26d" />

In an attempt to reduce the weight, I also divided all of my parametric equations used to calculate the different dimensions by a factor of 2. I did this to reduce the overall weight of the design, as I had observed that in the FEA, the areas of the Features C, D, and E all have very few issues or concentrations. If this is an overcorrection or even an undercorrection these values will be independently altered.

<img width="1902" height="431" alt="image" src="https://github.com/user-attachments/assets/b5972e07-ad60-40fc-b5de-2d03296ad36c" />

All of these alterations leave us with a design looking like the design below.

<img width="1911" height="982" alt="image" src="https://github.com/user-attachments/assets/bdede94f-4c27-42e5-85e9-87c3219880af" />

#### Mesh #1: Coarse Mesh 

Reutilizing the previous study from Design #1, we are able to avoid having to preprocess the model all over again, as it all transferred without issue, although I am now required to create a new Coarse mesh to accommodate all of the alterations. The new coarse mesh has 2274 elements.

<img width="1917" height="1137" alt="image" src="https://github.com/user-attachments/assets/4141bd54-30a9-4e59-a965-cf47d8a1a5d0" />

##### Stress Results 
The Coarse mesh calculated a maximum stress of 4065 psi, well below our maximum allowed stress value of 9,064.85 psi. This means that our second design is currently meeting the requirements for strength against stress.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/cc3e92a3-eaa4-4656-8d0a-4a61bd31b92d" />

Thanks to the fillets, the model's stress concentration is found to be much lower in Feature B's body, with it peaking well below our allowed minimum.

<img width="1916" height="985" alt="image" src="https://github.com/user-attachments/assets/bbefe2cd-20ad-4b73-b40c-23ec6825c2ea" />

##### Displacement Results

The coarse mesh calculated a max displacement of 0.0001494 inches, which is below our required displacement of 0.005 inches. This means that our second design is currently meeting the requirements for rigidity.  

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/9e48e74f-5024-4fdd-bc64-288d0311ce21" />

This concentration of displacement is found to be in the center of Feature A, which makes sense with both of Feature B supporting the feature from each side.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/40ac50bd-b4ae-4de2-92e5-33b956501d53" />

##### Factor of Safety Results

The Found minimum of the factor of safety in the design is was roughly 8.9, which is well above the required factor of safety of 4.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/8adbf76c-ca85-4fa2-8f57-e73c04ffb100" />

##### Mass Results

The reduced mass of the design was 2.06 lbs. This roughly a 1.3 lbs reduction from the previous Design, with our model now meeting stress and displacement requirements I can focus much more into the next design into reducing the overall weight.

<img width="451" height="120" alt="image" src="https://github.com/user-attachments/assets/83bf6fd5-8f37-460f-9aa6-fce8251420e1" />

#### Mesh #2: Medium Mesh

The Second mesh I created for Design #2 contains 6281 elements within its body.

<img width="1907" height="982" alt="image" src="https://github.com/user-attachments/assets/a8450d23-9f77-451e-9627-7a0e0758cfb2" />

##### Stress Results

For Medium Mesh, it was found that the maximum stress calculated was 4168 psi this is similar to the coarse mesh as it is also well below the required threshold of the max allowable stress.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/2240cab3-638b-4821-9c5d-a7ffebc36b14" />

Similarly to the coarse mesh the concentration was found within the same general location within Feature B on both sides.

<img width="1917" height="980" alt="image" src="https://github.com/user-attachments/assets/84886309-7b67-4f21-a7b2-467c75bee070" />

Using our Excel sheet, we find that the percent difference is an incredibly small 2.5% which is well below the 7% threshold asked for accuracy.

<img width="343" height="85" alt="image" src="https://github.com/user-attachments/assets/ffa6cddd-c4fb-46d0-a081-9624a4adf8a6" />

##### Displacement Results

For the medium mesh, it was found that the maximum deflection was 0.0001509 inches.

<img width="1916" height="982" alt="image" src="https://github.com/user-attachments/assets/0d634676-003f-440f-be81-44a03422169a" />

Its concentration is found roughly in the same spot as the coarse mesh predicted in the center of Feature A.

<img width="1912" height="980" alt="image" src="https://github.com/user-attachments/assets/b901a2bf-2474-4e23-b8d9-228db05c439b" />

Using our percent difference calculator, we find that the difference between the Coarse mesh and the Medium mesh is 0.999%. These are very accurate to each other and are found well below the 7% threshold.

<img width="346" height="90" alt="image" src="https://github.com/user-attachments/assets/be78dcd6-77f4-468d-95a3-40d102e734fd" />

##### Factor of Safety Results

The calculated value for the minimum safety factor for the medium mesh is at 8.7. This is well above the limiting value of 4 given by the Assignment. 

<img width="1917" height="986" alt="image" src="https://github.com/user-attachments/assets/72c683a3-094e-4ce0-9c1c-13d50408a73e" />

Calculating the percent difference between the 2 found safety factors, we get a value of 2.27% below the 7% threshold.

<img width="350" height="95" alt="image" src="https://github.com/user-attachments/assets/7a31d910-3dde-49dc-9322-41c4bd9e9acc" />

##### Mass Results

The reduced mass of the design was 2.06 lbs. The mesh size does not affect the estimated values for within our model.

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

Its concentration was found at the center of feature A, which is similar to the previous design. This makes sense, with feature B supporting it on either side it leaves the center the most unsupported and susceptible to deflection.

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

The maximum calculated deflection is found to be 0.0001429 inches

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/57b5ffc6-e344-479b-a69a-42dd642bd14f" />

Similar to all other deflections, post design #1: our concentration is found on Feature A.

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


## FEA Link

The step of the assignment is to take the link we have been producing in parallel to the bracket and apply similar constraints to test the stress, Factor of safety, and deflections. 

### Preprocessing 

I first started by creating a Static study for our link, naming it "D2".

<img width="1917" height="985" alt="image" src="https://github.com/user-attachments/assets/7cceb510-3220-41cd-82aa-3545e49bc946" />

I then created a fixed Surface on the surface that connects to Feature A, the smaller-radius hole.

<img width="1917" height="976" alt="image" src="https://github.com/user-attachments/assets/0e0048ba-53b3-4fbf-8d8a-bec5b6b89f99" />

I then applied a 600 lbf downward force to the second hole measured at 1 inch.

<img width="1916" height="981" alt="image" src="https://github.com/user-attachments/assets/bc80a07b-3ae2-4c45-9720-8b19d6550974" />

I then set the Material to ASTM A36 steel, which is the same material type as the bracket.

<img width="1915" height="982" alt="image" src="https://github.com/user-attachments/assets/1a0a774a-054d-4066-ab5c-83e8f7a96e36" />

## FEA

### Design #1

##### Mesh #1: Coarse Mesh

2335 elements 

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/2043d278-1e11-42b2-8d8b-60aedb4404f6" />

##### Stress Results

172100 psi max stress below the yield stress

<img width="1912" height="985" alt="image" src="https://github.com/user-attachments/assets/b9be5a6e-4efa-4efa-b7c2-76fa951c999a" />

Concetration is found at the left and right edges of of the force applied circle.
<img width="1916" height="980" alt="image" src="https://github.com/user-attachments/assets/d7276679-58b5-4050-9d1d-c21c2965a004" />

##### Deflection Results

0.0008286 inch max deflection below 0.005 inches

<img width="1917" height="982" alt="image" src="https://github.com/user-attachments/assets/b219e06c-93f4-434e-bf2e-d20f6d58abb4" />

Concentration at the bottom of the force applied circle.

##### Factor of Safety Results

Minimum 2.1 FOS.

<img width="1917" height="978" alt="image" src="https://github.com/user-attachments/assets/a5c59fca-81c4-49ff-a326-af20872c9034" />

##### Mass Results

Mass is 0.09 lbs

<img width="475" height="162" alt="image" src="https://github.com/user-attachments/assets/0dade6b0-bd82-40ec-b6b7-4fa1cee3e1a0" />

