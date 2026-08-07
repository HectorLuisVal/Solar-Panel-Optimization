# Model 1: Fixed Constraints

The purpose of this model was to provide a way of finding the Maximum Energy Output given fixed environmental constraints

## Instructions
### HOW TO CODE are in [Model-1 Report](SolarPanel_Final_Model1.pdf)

#### Step 1: Defining the Objective Function
The **Energy function** E(θ,r) is the objective function for this optimization problem. It calculates how much energy a solar panel produces based on its **Tilt Angle (theta)** and **Aspect Ratio (r)**

 ![](../Images/Equation_SolarPanel.png)
 
Note: The function "cosd" calculates values in degrees instead of radians 

#### Step 2: Implement the Optimization Problem 
The [optimization problem](https://www.mathworks.com/help/releases/R2026a/optim/ug/problem-based-workflow.html) solves for the **Maximum Energy Output**. 

By defining the optimization variables Tilt Angle (theta) and Aspect Ratio (r), the solver finds the highest energy output given the fixed constraints of Tilt Angle and Aspect Ratio. 

In Model 1, the environmental Constraints are Fixed, based off a theoretical assumption given in the [MathWorks GitHub Classroom Challenge Projects](https://github.com/mathworks/MATLAB-Simulink-Challenge-Project-Hub/tree/main/Classroom%20Challenge%20Projects/Projects/Maximizing%20Solar%20Panel%20Output%20for%20a%20Fixed%20Area).
- Constraint for Tilt Angle: 0° ≤ θ ≤ 90°
- Constraint for Aspect Ratio: 0.5 ≤ r ≤ 4

Setting up the upper and lower bounds correctly for the optimization variables is crucial for receiving the correct maximum energy output as the optimization solver searches within the upper and lower bounds

After creating the objective function and defining it, a initial guess value must be given. For Model-1 use values within the constraints to get the correct maximum energy output. 
- initial_guess.theta = 45 
- initial_guess.r = 2

Store the solution to the optimization problem 


#### Step 3: Output the Results
**Plot E(θ, r)** to visualize the energy as a surface plot using *meshgrid* and [surf](https://www.mathworks.com/help/matlab/ref/surf.html). Plot the optimal tilt angle and aspect ratio, and corresponding energy output onto the grid; the absolute maximum of the surface plot should align with the optimal point. Finally, print the optimal tilt angle and aspect ratio, and the Maximum energy output.

Checklist: 
- Create Grid Values for Tilt Angle and Aspect Ratio using meshgrid 
- Generate energy grid values that are dependent on θ & r. 
- Create the Surface Plot using the surf function
- Add shading that illustrate the gradual change in energy output using shading and colorbar functions 
-  Set Axis limits for the plot (they can be equal to or greater then constraints)
-  Label the plots
-  Plot the optimal point on the surface plot
-  Print Results

### Project Files
- [Model-1 Report](SolarPanel_Final_Model1.pdf)
- [Model-1 MATLAB LiveScript](SolarPanel_Final_Model1.mlx)
   
## Results
Through MATLAB's Optimization Toolbox™, Model 1 produced values consist of the maximum energy output. This can be seen through the optimal point plot aligning with the highest part of the surface plot representing the function  within the fixed constraints. 

Following the Instructions/MATLAB LiveScript and using the given constraints should provide the following results: 
- Optimal tilt angle: 37.50°
- Optimal aspect ratio: 1.00
- Maximum energy output: 1965.93 W/m^2

![](../Images/Surf-Plot-Model1.png)

This demonstrates Model 1's ability to create a surf plot that represents all possible values within the given constraints, and also, find the optimal Tilt Angle and Aspect Ratio to deliver the maximum energy output for a solar panel with a fixed area of 2m².

However, Model 1 is limited because of it's fixed constraints. It cannot be applied efficiently to a variety of situation where the constraints are not the given values. Additionally it does not account for the possibility of multiple local maximums that could provide misleading results based off its initial guess. 

To improve on Model 1, a varying scale can be implemented that provides a more efficient and flexible program. This has more practical applications to commercial usage. Moreover, to account for the possibility of multiple local maximums, this new program must contain multiple initial guesses and also be able to sort through contradicting maximum values and provide the optimal Tilt Angle & Aspect Ratio for the highest maximum energy output. 

