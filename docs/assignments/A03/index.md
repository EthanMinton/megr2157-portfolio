# A3 – Parametric and FEA

## 1.0 Objective

The core objective of the A3 assignment is to design a cylindrical cross-section aluminum beam using parametric CAD software, then simulate the impacts of a direct tensile force applied to one end using Finite Element Analysis (FEA).

## 2.0 Parametric Design

### 2.1 Establishing Global Variables 

To preface, I am using the software "SOLIDWORKS Design" for both the CAD modeling and the FEA. After opening a new file, I immediately navigated to the left sidebar of the screen to access the "Equations" by right-clicking and then the "Manage Equations" tab.
<img width="272" height="175" alt="Screenshot 2026-09-08 154240" src="https://github.com/user-attachments/assets/541db855-210d-41b7-857e-57b3f229d2e3" />

After accessing the equations, I began to input each value to their assigned variable. Beginning with force, assigned to "F", I set it to 400 lbf, as it sits in the middle of the given range. The Young's Modulus for Aluminium, assigned to "E", was 10,000,000 psi (10^7 psi), as it also sat in the middle of the given range of values. Also, note that most Aluminum alloys' Young's modulus sits around this value (shown later). The value given for deflection was 0.009 inches; this was assigned to "defl". Next were the geometric variables: the outer diameter of the cylinder, assigned "do", is 0.5 inches, and the inner diameter, assigned "di", is 0.25 inches. Taking those values, we can calculate the cross-sectional area of the model, assigned "A",  using the equation "(pi/4) * ("do"^2 - "di"^2)", giving us a value of around 0.147 inches^2. Taking all of our variables and using "("defl" * "A" * "E") / "F"", we can calculate the length of our model, giving us 33.08 inches, assigned to "L"

<img width="1110" height="430" alt="Screenshot 2026-09-09 143412" src="https://github.com/user-attachments/assets/225042a9-875b-4e76-b4ff-080d066c0454" />

<img width="820" height="278" alt="Math Scratch Paper (18)" src="https://github.com/user-attachments/assets/728aa930-d33e-4163-bdc9-3d8d4fdcfac0" />

### 2.2 Parametric Modeling

After exiting the Sketch, we then move on to modeling, sketching off of the "Right Plane" view.
<img width="1917" height="1137" alt="Screenshot 2026-09-08 160017" src="https://github.com/user-attachments/assets/6ac4d78f-d609-4ef7-a14c-8915f7766da5" />
<img width="1917" height="1137" alt="Screenshot 2026-09-08 160100" src="https://github.com/user-attachments/assets/e1b93023-bc97-4f38-b13c-e62dc49ed968" />

I began by creating 2 Circles overlapping each other, with their centers being directly aligned with each other. I started by constraining the outer circle with the previously set global variable "do" (value of 0.5 inches) and then setting the inner circle to "di" (value of 0.25 inches). This is to ensure that when changing the global variables, almost all possible alterations are carried throughout the entire file.

NOTE: A major mistake was made here with the implementation of the global variables. For more explanation on how to properly implement them, refer to the Lesson Learned Section at the very bottom.

<img width="972" height="640" alt="Screenshot 2026-09-08 160236" src="https://github.com/user-attachments/assets/8732bbe2-fe79-42ad-a1b6-55a0c2469b6e" />
<img width="1055" height="603" alt="Screenshot 2026-09-09 143931" src="https://github.com/user-attachments/assets/ad815d84-dd0e-40b5-90c5-3a1165b716d7" />

After establishing the diameter values, I moved on to extrude the sketch using the calculated global variable "L" (value of 33.08 inches) within the left sidebar.

<img width="475" height="541" alt="Screenshot 2026-09-09 144124" src="https://github.com/user-attachments/assets/02a72b7b-2335-4bdd-a337-f22ac6468cc8" />
<img width="1632" height="908" alt="Screenshot 2026-09-09 144204" src="https://github.com/user-attachments/assets/58fac47d-0608-41b0-8390-e54692a61e39" />

### 2.3 Finite Element Analysis
#### 2.31 Setup

Moving towards the materials on the left sidebar, I began to search for an aluminum alloy that had the most similar Young's Modulus to the chosen value of 10,000,000 psi (10^7 psi). I eventually settled on the SolidWorks preset of "6061-T6 (SS)," an aluminum alloy with a Young's Modulus of "10,007,604 psi," mainly due to the proximity it has to the selected value. 

<img width="267" height="285" alt="Screenshot 2026-09-08 160546" src="https://github.com/user-attachments/assets/b7b551a8-1c86-4ef8-947f-e97f82c49d9d" />
<img width="943" height="777" alt="Screenshot 2026-09-08 160706" src="https://github.com/user-attachments/assets/551c8a0f-3b45-43ba-8e4a-5994026979b3" />

Once setting our material, I moved on to the simulation, clicking on the "New Study" button found in the top left corner of the page. Opening a tab on the left, I then selected "Static" under "General Simulation," naming the study "Tensile Loading"

<img width="272" height="1078" alt="Screenshot 2026-09-08 160822" src="https://github.com/user-attachments/assets/0dc188b8-06f0-4ca4-b67c-1d5082c8f02c" />
<img width="272" height="407" alt="Screenshot 2026-09-08 160900" src="https://github.com/user-attachments/assets/89c2dc21-8cd2-4341-8dd3-4a95c9384d2f" />

Confirming the Study, I then went to the left sidebar, right-clicked on the "Fixtures" tab, and clicked on the "Fixed Geometry". Going to the initially sketched Right plane, I chose to establish it as our fixed geometry.

<img width="272" height="470" alt="Screenshot 2026-09-08 160948" src="https://github.com/user-attachments/assets/82abfef6-6b3b-42d5-8b10-58cab7685bc5" />
<img width="1671" height="852" alt="Screenshot 2026-09-09 144502" src="https://github.com/user-attachments/assets/a9a8bb23-fedd-43e5-ba97-484d3ba8de06" />

The next step is to right-click on the "External Load" and select the "Force" tab. Going to the opposite end of the model, I selected the face and input the value 400 lbf and reversed the directions of the vectors to ensure the Aluminum is in tension. I would have opted to parametrically use the value of "F" but it seems that the software does not support this, likely due to not being able to rerun the simulation every time the variable is changed.

<img width="287" height="677" alt="Screenshot 2026-09-08 161207" src="https://github.com/user-attachments/assets/77442178-84e1-4cca-8c3f-759f0c4019ce" />
<img width="1861" height="851" alt="Screenshot 2026-09-09 144719" src="https://github.com/user-attachments/assets/c00dde17-b9d8-42ef-bbf5-0121b8b477e4" />

The final step for setting up the Final element analysis is creating the mesh. Going to the "Mesh" tab and selecting "Create Mesh," I was able to create a mesh for the model that came out looking like below. I opted to not touch any of the mesh settings, as the follow-along video avoids touching anything as well. 

<img width="322" height="650" alt="Screenshot 2026-09-08 161507" src="https://github.com/user-attachments/assets/5ce5a409-478c-42e2-9597-49e4fd1bcbc9" />
<img width="270" height="495" alt="Screenshot 2026-09-08 161535" src="https://github.com/user-attachments/assets/fa7b8e85-fb53-4cae-8859-16684810624e" />
<img width="1915" height="1010" alt="Screenshot 2026-09-09 145020" src="https://github.com/user-attachments/assets/eabded8c-ed96-4a21-ae8b-dc3e05041c67" />

Once the mesh is completed, you get to the top of the tab and click on "Run This Study" to achieve your results.

<img width="1033" height="157" alt="Screenshot 2026-09-08 161717" src="https://github.com/user-attachments/assets/0eada21d-8353-4cd3-ba2d-c9a8654085c6" />

#### 2.32 Finite Element Analysis Results

To observe our FEA, we must change the units used to ensure that our data can be easily legible and compared. To do this, we must right-click on the specific Simulation and select "Edit Definition". In the new sidebar on the left, you select the "Unit" and choose the unit you want accordingly. In this case, "psi" was selected for the Von Mises Simulation, and "inches" was selected for the Displacement Simulation.

<img width="358" height="225" alt="Screenshot 2026-09-09 151734" src="https://github.com/user-attachments/assets/ee31b868-4831-4d2e-b7ad-10172425d6b8" />
<img width="271" height="307" alt="Screenshot 2026-09-09 152000" src="https://github.com/user-attachments/assets/8024d478-7299-473f-bf48-4c220f458790" />

##### Von Mises Stress Map
<img width="1915" height="962" alt="Screenshot 2026-09-09 152532" src="https://github.com/user-attachments/assets/7d343997-27fd-4779-86b5-f989e1a8385c" />

##### Deflection Map
<img width="1906" height="1012" alt="Screenshot 2026-09-09 152627" src="https://github.com/user-attachments/assets/25224aa2-ee5c-4d9b-86f4-2e469b2ea27f" />

## 3.0 FEA Reflection
### 3.1 Factor of Safety 

Calculating the factor of safety requires us to take the given strength of aluminium, which is 40 ksi, and divide it by the maximum stress observed within the Von Mises Stress Map, which is the value found at the very top of the legend, "2.920e +3" or 2.920 ksi. This gives us a value of around 13.7, rounding it to a safety factor of 14. This is a considerably large safety factor for the designed beam and conveys that the beam is overdesigned for axial tension applied to it. Obnoxious values can be expected here, as the design process prioritized achieving a specific deflection value over a value of stress. If we had prioritized obtaining a specific Factor of safety here, it is likely that the deflection value would be nowhere near the asked-for value. As an engieer often you have to figure out how to achieve both without getting in the way of the other.

<img width="820" height="670" alt="Math Scratch Paper (19)" src="https://github.com/user-attachments/assets/c913bf38-55c0-47ff-99d0-cf43379d2646" />

### 3.2 Displacement Difference  

After calculating the percent difference below using 0.009 inches as our given and 0.00899 inches as our CAD-produced, it was found that they were roughly 0.078% different. An extremely small magnitude of difference; they could be considered essentially the same. The reason for this is likely due to the uniform geometry of the beam that prevents any complications within it internally. CAD Finite Element Analysis has the benefit of assuming the lack of stress concentrations due to the absence of geometries such as fillets, holes, or cracks within the structure and, being paired with the simple geometry of the tube, we can assume that the tension applied to the end of the structure should perform nearly exactly as predicted by our hand calculations.

Since these calculations are nearly exact, the choice of which one I trust more is less impactful than if they differed. I would say that personally I trust the Finite Element Analysis just a little bit more, as it is able to take into account more geometric information of the body itself using the mesh. In most real-world situations, values such as these can vary from the theoretical to the real; taking in more details and properties can introduce some of the factors that may not be included within a purely theoretical calculation.

<img width="820" height="450" alt="Math Scratch Paper (20)" src="https://github.com/user-attachments/assets/2e510c11-b85b-43a3-9d9a-6f7066dfd846" />

### 3.3 Pin Hole Stress Concentration Hypothetical

I want to preface this section by noting that, when using the "Machinery's Handbook 32 Edition," pages 207-210 are where the plot and information pertaining to stress concentrations are held. But it seems as if the information that is contained here is limited to situations that are not asked for here. The closest example that it presents is a pinhole within a cylindrical body having a bending moment applied to it. While the assignment specifically asks for us to find the situation of a fairly substantial pinhole within a flat bar in tension. Thankfully, due to some research, I found an accurate calculator that allows us to calculate the "kt" using the equation shown in the work below. This calculator directly sources the given kt equation "Kt = 3.0 - 3.13(d/D) + 3.66(d/D)^2 - 1.53(d/D)^3" from the Peterson's Stress Concentration Charts.

Source: [https://mechsimulator.com/tools/stress-concentration/](https://mechsimulator.com/tools/stress-concentration/)

I began by making the choice of determining our ratio of the diameter of the pin hole to the width of the rectangular beam, the prompt specifically asks for a significant hole within the beam. So I chose the values of 0.5 inches for the width of the beam, paired with 0.2 inches for the diameter of the pin hole. The nominal stress that I will be using is the max stress value obtained through the Finite Element Analysis, 2.92 ksi. Using the equation provided we can solve for our Kt value, which comes out to around 2.236. We can take this value and multiply it to the nominal stress value we mentioned prior to find our maximum stress value of 6.53 ksi. This would definitely fall below the threshold of 40 ksi from the aluminum yield strength, giving us a factor of safety of around 6.13. This sliced our safety factor in half. It comminucates how despite how overdesigned the original beam was a simple pin hole within its structure could significantly affect our factor of safety.


### 3.4 Modify Parameters of FEA (2157)

To preface, the instructions mention altering the "load, thickness, height and width" as if we were handling a different shape like a triangular beam from the previous semester; I assume that the instructions want us to go out of our way to change the primary geometric constraints and axial force being applied to our beam. We were also instructed to keep our values for the material properties and fixtures the same. 

We understand that using the equation "("defl" * "A" * "E") / "F"" we can solve for the total length. I chose to change the values of the outer diameter, "do", to 0.75 inches, the inner diameter, "di", to 0.2 inches, and the force, "F", to 300 lbf. I specifically chose these 3 values to make it easier to predict. A larger outer diameter and smaller inner diameter create a much larger cross-sectional area. Being paired with a smaller force should mean that the produced length should be considerably longer than the initial length with our original values. 

This is because, with the Area being found in the numerator, an increase in area would increase the length. The force is found in the denominator, meaning a small force is going to divide our numerator by a smaller value.

<img width="1116" height="421" alt="Screenshot 2026-09-09 174207" src="https://github.com/user-attachments/assets/caac9268-405f-48e7-843a-a0001ba1fb7d" />
<img width="876" height="602" alt="image" src="https://github.com/user-attachments/assets/7a213b73-adb4-4112-924e-c9d861836585" />
<img width="1821" height="832" alt="image" src="https://github.com/user-attachments/assets/24facb58-9689-43ee-8948-482512c736ef" />

After rebuilding the beam and reconfiguring a new study, we obtained the results shown below. Note that performing the simple calculation of our yield strength of 40,000 psi divided by the max stress of 7.732 e^+2, 773.2 psi. We obtain a  factor of safety of around 51.7 or 52. This is even higher than previously reported.

<img width="1917" height="966" alt="image" src="https://github.com/user-attachments/assets/97e0ecee-785b-45e6-aa75-87d99a214b63" />
<img width="1915" height="981" alt="image" src="https://github.com/user-attachments/assets/27aa0cd8-84af-430f-8716-97e16315b7e0" />

## 4.0 Lessons Learned 

The single greatest mistake that I made in this assignment is the implementation of global variables to create the geometry of the beams. For the sake of documentation, I have left the screenshots of the implementation within the preceding text above, as they don't contradict anything explained throughout the process and still allowed for the needed maps and information to be produced. I will attach the fixed screenshots below as recorded proof that the issue was fixed. The issue stems from the implementation of the global variables in the dimensional constraints, specifically the outer diameter ("do"), the inner diameter ("di"), and the length ("L"). When I initially input the values, I had merely looked up the global variables and selected the value, assuming this meant that the variable was actually being used and not just the value currently attributed to it. This is incorrect; to properly implement the global variable, you must do it by inputting " ="(variable Name)"" a little globe should appear, as well as a summation symbol beside the numerical value beside the constraint. Every time you change the variable, you should rebuild the model to ensure that it updates itself. Thankfully, when attempting the 2157 bonus section, I was able to catch this mistake and fix it. 

<img width="1312" height="856" alt="Screenshot 2026-09-10 061833" src="https://github.com/user-attachments/assets/7683f38d-b0d0-41d2-8af1-faa034146d57" />
<img width="1316" height="876" alt="Screenshot 2026-09-10 061925" src="https://github.com/user-attachments/assets/3157580e-8ced-41a7-b170-10f57a3f37d7" />
<img width="1635" height="556" alt="Screenshot 2026-09-10 062009" src="https://github.com/user-attachments/assets/14a60c87-04c6-4add-ab11-f68acadc011e" />

Otherwise, there was little issue with performing all of the tasks asked of us. It roughly took me 5 hours and 30 minutes, which I expected when trying out SolidWorks in depth for the first time. 

Link to CAD: [A3_Main.SLDPRT](A3_Main.SLDPRT)
