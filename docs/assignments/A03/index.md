# A3 – Parametric and FEA

## Objective

The core objective of the A3 assignment is to design a cylindrical cross-section aluminum beam using parametric CAD software, then simulate the impacts of a direct tensile force applied to one end using Finite Element Analysis (FEA).

## Parametric Design

### Establishing Global Variable 

To preface I am using the software "SOLIDWORKS Design" for both the CAD modeling and the FEA. Openning a new file I immmediately navigated to the the left sidebar of the screen access the "Equations" by right clicking and then the "Manage Equations" tab.
<img width="272" height="175" alt="Screenshot 2026-09-08 154240" src="https://github.com/user-attachments/assets/541db855-210d-41b7-857e-57b3f229d2e3" />

After Accessing the Equations I began to input each value to their assigned variables. Beginning with force, assigned to "F", I chose to set force to 400 lbf as it sits in the middle of the given range we could choose. The Young's Modulus for Aluminium, assigned to "E", was 10,000,000 psi (10^7 psi) as it had also sat in the middle of the given range of values. Also to note most Aluminum alloys Young's Modulus sit around this value (shown later). The value given for deflection was 0.009 inches, this was assigned to "defl". Next were the geometric variables with the outer diameter of the cylinder, assigned "do", is 3 inches and the inner diameter, assigned "di", is 2 inches. Taking those values we can calculate the cross sectional area of the model, assigned "A",  using the equation "(pi/4) * ("do"^2 - "di"^2)" giving us a value of around 3.93 inches^2 . Taking all of our variables and using "("defl" * "A" * "E") / "F" " we are able to calculate the length of our model giving us 88.36 inches, assigned to "L"

<img width="1112" height="426" alt="Screenshot 2026-09-08 155951" src="https://github.com/user-attachments/assets/45d3f900-d19f-4672-9058-42d9741949dc" />

NEED TO CALCULATE BY HAND

### Parametric Modeling

After exitting the Sketch we then move on to modeling, sketching off of the "Right Plane" view.
<img width="1917" height="1137" alt="Screenshot 2026-09-08 160017" src="https://github.com/user-attachments/assets/6ac4d78f-d609-4ef7-a14c-8915f7766da5" />
<img width="1917" height="1137" alt="Screenshot 2026-09-08 160100" src="https://github.com/user-attachments/assets/e1b93023-bc97-4f38-b13c-e62dc49ed968" />

I began by creating 2 Circles overlapping each other with theirs centers being directly alligned with each other. I started by constraining the outer circle with the previously set global variable of "do" (value of 3 inches) and then setting the inner circle to "di" (value of 2 inches). This is to ensure that in the situation of changing the global variables almost all possible altercations are carried throughout the entire file.

<img width="972" height="640" alt="Screenshot 2026-09-08 160236" src="https://github.com/user-attachments/assets/8732bbe2-fe79-42ad-a1b6-55a0c2469b6e" />
<img width="1193" height="736" alt="Screenshot 2026-09-08 160251" src="https://github.com/user-attachments/assets/6eb02338-0298-4cd9-b0bd-448eaa3ca9af" />

After establishing the diameter values I moved on to extrude the sketch using the calculated global variable of "L" (value of 88.36 inches) within the left sidebar.

<img width="272" height="563" alt="Screenshot 2026-09-08 160411" src="https://github.com/user-attachments/assets/d263ebeb-4d34-419b-b078-dd64418ed503" />
<img width="1917" height="847" alt="Screenshot 2026-09-08 160432" src="https://github.com/user-attachments/assets/7dd235ff-61bd-4d0e-9c7f-46115b6261e5" />

### Finite Element Analysis Setup

Moving towards the materials on the left sidebar I began to search for a Aluminum Alloy that had the most similar Young's Modulus as the chosen value of 10,000,000 psi (10^7 psi), I eventually settled on the Solidworks preset of "6061-T6 (SS)" an aluminum alloy with a Young Modulus of "10,007,604 psi" mainly due to the proximity it carries with the selected value. 
<img width="267" height="285" alt="Screenshot 2026-09-08 160546" src="https://github.com/user-attachments/assets/b7b551a8-1c86-4ef8-947f-e97f82c49d9d" />
<img width="943" height="777" alt="Screenshot 2026-09-08 160706" src="https://github.com/user-attachments/assets/551c8a0f-3b45-43ba-8e4a-5994026979b3" />

Once setting our material I moved on to the simulation, clicking on the "New Study" button found in the top left corner of the page. Openning a tab on the left I then selected "Static" under "General Simulation" naming the study "Tensile Loading"

<img width="272" height="1078" alt="Screenshot 2026-09-08 160822" src="https://github.com/user-attachments/assets/0dc188b8-06f0-4ca4-b67c-1d5082c8f02c" />
<img width="272" height="407" alt="Screenshot 2026-09-08 160900" src="https://github.com/user-attachments/assets/89c2dc21-8cd2-4341-8dd3-4a95c9384d2f" />

Confirming the Study, I then went to the left sidebar and right clicked on the "Fixtures" tab and clicked on the "Fixed Geometry". Going to the initial sketched Right plane I chose to establish it as our fixed geometry.

<img width="272" height="470" alt="Screenshot 2026-09-08 160948" src="https://github.com/user-attachments/assets/82abfef6-6b3b-42d5-8b10-58cab7685bc5" />
<img width="1910" height="1105" alt="Screenshot 2026-09-08 161121" src="https://github.com/user-attachments/assets/9dd72cab-05b0-4c92-b9e2-8259f2b107d3" />

The next step is to right click on the "External Load" and select the "Force" tab. Going to the opposite end of the model I selected the face and inputed the value 400 lbf and reversed the directions of the vectors to ensure the Aluminum is in tension. I would have opted to parametrically used the value of "F" but it seems that the software does not support this likely due to not being able to rerun the simulation everytime the variable is changed.

<img width="287" height="677" alt="Screenshot 2026-09-08 161207" src="https://github.com/user-attachments/assets/77442178-84e1-4cca-8c3f-759f0c4019ce" />
<img width="1555" height="585" alt="Screenshot 2026-09-08 161412" src="https://github.com/user-attachments/assets/85b3436e-d8d6-4c18-9b05-49f63242d11a" />

The final step for setting up the Final element analysis is creating the mesh. Going to the "Mesh" tab and slecting "Create Mesh" I was able to create a mesh for the model that came out looking like below. I opted to not touch any of the mesh settings as the follow along video avoid touching anything as well. 

<img width="322" height="650" alt="Screenshot 2026-09-08 161507" src="https://github.com/user-attachments/assets/5ce5a409-478c-42e2-9597-49e4fd1bcbc9" />
<img width="270" height="495" alt="Screenshot 2026-09-08 161535" src="https://github.com/user-attachments/assets/fa7b8e85-fb53-4cae-8859-16684810624e" />
<img width="1912" height="812" alt="Screenshot 2026-09-08 161633" src="https://github.com/user-attachments/assets/fc601990-22f6-49e0-95d8-003d6b5c3dae" />

Once the mesh was completed you got the top of the tab and click on the "Run This Study" to achieve your results.

<img width="1033" height="157" alt="Screenshot 2026-09-08 161717" src="https://github.com/user-attachments/assets/0eada21d-8353-4cd3-ba2d-c9a8654085c6" />

### Finite Element Analysis Results



