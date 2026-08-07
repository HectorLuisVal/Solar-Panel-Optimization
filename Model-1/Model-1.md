# Model 1: Fixed Constraints

The purpose of this model was to provide a way of finding the Maximum Energy Output given fixed environmental constraints

### Instructions
##### Detailed Instructions on HOW TO CODE are in [Model-1 Report](reports/SolarPanel_Final_Model1.pdf)

#### Step 1: Implement Optimization Problem 
In order to get the same results as Model 1, the environmental **constraints have to be fixed** at the correct values. These constraints are based off the [MathWorks GitHub Classroom Challenge Projects](https://github.com/mathworks/MATLAB-Simulink-Challenge-Project-Hub/tree/main/Classroom%20Challenge%20Projects/Projects/Maximizing%20Solar%20Panel%20Output%20for%20a%20Fixed%20Area) description. 
- Constraint for Tilt Angle: 0° ≤ θ ≤ 90°
- Constraint for Aspect Ratio: 0.5 ≤ r ≤ 4

Setting up the upper and lower bounds correctly for the optimization variables is crucial for receiving the correct maximum energy output as the optimization solver searches within the upper and lower bounds

#### Step 2: Defining the Objective Function
Using the Energy Production Formula given above; begin defining the variables in terms of θ & r. 

Important to note that the solver uses radian values instead of degrees. Multiplying inside the cosine function with pi/180 convert the theta values from degrees to radians.

After creating the objective function and defining it, a initial guess value must be given. For Model-1 use values within the constraints to get the correct maximum energy output. 
- initial_guess.theta = 45 
- initial_guess.r = 2

Store the solution to the optimization problem 

#### Step 3: Output the Results
- Create Grid Values for Tilt Angle and Aspect Ratio using meshgrid 
- Generate energy grid values that are dependent on θ & r. 
- Create the Surface Plot using the surf function
- Add shading that illustrate the gradual change in energy output using shading and colorbar functions 
-  Set Axis limits for the plot (they can be equal to or greater then constraints)
-  Label the plots
-  Plot the optimal point on the surface plot
-  Print Results

### Project Files
- [Model-1 Report](Model-1/SolarPanel_Final_Model1.pdf)
- [Model-1 MATLAB LiveScript](Model-1/SolarPanel_Final_Model1.mlx)
   
## Results

Following the Instruction/MATLAB LiveScript and using the given constraints should provide the following results: 
- Optimal tilt angle: 37.50°
- Optimal aspect ratio: 1.00
- Maximum energy output: 1965.93 W/m^2

![](Images/Surf-Plot-Model1.png)

