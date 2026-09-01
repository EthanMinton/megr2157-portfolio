# A2 – Truss Stress Analysis

## Objective

Design a Truss System geometry using the given parameters below, solving for the applied forces, the stress they create, and the material strengths used to resist the stress. 

## Analyze

### Creating the Truss System

The image below was given as the starting point for this assignment for us to create the Truss system around, with the given values of a, b, and P being 0.4, 0.3, and 25 KN. We were allowed to choose our value of P within a range of 20-30 KN, I decided to choose 25 KN as it sat right in the middle of those values and would allow me to deal with high stress calculations later within the assignment. 

<img width="467" height="301" alt="image" src="https://github.com/user-attachments/assets/69652f21-18dc-4320-84b5-1215811e07e9" />

After analyzing the given constraints provided, I decided to resketch it all within my notetaker to ensure the process continues properly. Once sketched, I decided to get the general outline of the truss system to see how I could attempt to properly balance the forces through it. After which, I then created a new Joint, labeled as Joint E below, to help prevent possible concentration of stresses within the truss system.


Before continuing, I decided to calculate all of the geometry that would be important later on within the system itself to prevent any issues and extra complications once we reach the internal force calculations. Starting by calculating the 2 angles that would impact the angled members within the truss, theta_b was calculated using the ratio (0.3/0.4) and plugging it into arctangent, receiving the angle 36.87 degrees. This angle will be important when calculating the internal forces for members BC and AD. Then theta_c was calculated using the ratio (0.3/0.2); 0.2 was used because Joint E was found to be directly in the middle of the given 0.4 measurement. Once it was plugged into arctangent, the angle given was 56.31 degrees, providing use to the members CE and DE.


Moving toward the lengths of each of the members, I started by calculating the length of members BE and AE. Using the provided geometry, I combined the value of a over itself 3 times and divided it by half, as each member bisected the entire length, giving the length to be 0.6 meters. The members CE and DE were a little more complicated, as they required the use of rearranging the trigonometric ratio in order to solve for the hypotenuse. A considerably simpler way that I could have used was to calculate the hypotenuse of the triangle, which provides the same result of 0.361 meters. The members AD and BC were calculated similarly to the previous 2 members, with the rearranging of the sine trigonometric ratio to solve for the length, which gave 0.5 meters. Due to symmetry, there were only 3 calculations needed over 6.

### Calculating the Forces

#### External Forces

When approaching a truss system with Joint analysis, it is typically recommended to solve for all of the external forces present before continuing to the internal forces. The given constraints have 2 applied forces: 25 KN pushing upward at C and 25 KN pulling downward at D. Joint B is a roller, meaning it only has a force in the y-direction labeled B_y, and the Joint at A is a pin connection, giving it a force in both the x-direction and y-direction labeled A_x and A_y, respectively. Using statics and the equilibrium of F_x, we found that no other force is in the x-direction, resulting in A_x being equal to 0. Finding the moment around B allows us to solve for the force in A_y, giving us 8,333.3 N upward, and finding the resulting forces in the y-direction gives us B_y at 8,333.3 N downward. In this case, I had assumed the direction of B wrong, providing the negative solution. Though these results make sense due to the symmetrical relation of the truss.


## Decide
_Which geometry did you select, and why? This is your first open design choice in the course — defend it._

## Communicate

