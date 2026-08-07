# Model 2: Scalable Constraints 
The purpose of this model is to find the maximum energy output when constraints can be varied. This allows for greater flexibility and practicality. 

## Instructions 
### Detailed Instructions on HOW TO CODE are in [Model-2 Report](SolarPanel3_Final_Model2.pdf)

#### Step 1: Implement the Optimization Problem w/ *Sliders*
The [optimization](https://www.mathworks.com/help/releases/R2026a/optim/ug/problem-based-workflow.html?searchPort=57359) problem solves for the Maximum Energy Output. 

By defining the optimization variables Tilt Angle (theta) and Aspect Ratio (r), the solver finds the highest energy output given the varying constraints of Tilt Angle and Aspect Ratio. 

In Model 2, the environmental **Constraints are Scalable**. This provides a more practical usage of how to optimize for Maximum Energy Output. 

Utilizing the [control panel](https://www.mathworks.com/help/matlab/matlab_prog/add-interactive-controls-to-a-live-script.html), sliders will be used to set the upper and lower bounds of each optimization variable. 

- Absolute Min & Max limit for Tilt Angle () using slider: 0° ≤ θ ≤ 180 ° (this can be changed by right clicking on the slider and pressing 'Configure Control')
- Absolute Min & Max limit of Aspect Ratio (r) using slider: 0 ≤ r ≤ 10  (can be changed the same way as above)

Where to find the Control Panel:
![](../Images/Control_Panel.png)

Note: The Upperbound Slider value cannot be lower then the Lowerbound slider value otherwise the **Code Will Not Run**

#### Step 2: Define the Objective Function
The **Energy function** E(0,r), is the objective function for this optimization problem. It calculates how much energy a solar panel produces based on its **Tilt Angle (theta)** and **Aspect Ratio (r)**.
  
In Model 2, "A" (the fixed panel area) also has a slider. However, unlike "theta" or "r", "A" has a positive linear proportionality to the Energy function therefore it does not need to be optimized. 

The purpose of giving "A" a slider was to calculate the **Total Energy Production** of an array of solar panels with the same Tilt Angle and Aspect Ratio in a given area.

Example Image of solar panel array:

![](../Images/StockPhoto_SolarPanel.png)

Note: The solver uses radian values instead of degrees. Multiplying inside the cosine function with pi/180 convert the theta values from degrees to radians.

#### Step 3: Solve for Optimal Aspect Ratio and Tilt Angle 
In Model 1, for the **Initial Guess** the values were chosen because they were within the constraints. 

However, this does not work for Model 2. For the solve command, the optimization solvers searches for the nearest local Maximum based off the initial guess. As shown in the example surf plot, this method does not work when there are multiple local Maximums. 

Example surf plot using Model 1: 

![](../Images/Problem-Surf-Plot-Model2.png)

To solve this problem, the approach was to set up **Two Initial Guesses** around each peak and keep the larger value. To identify whether there is more than one peak use the surf plot built in Objective 4. 

Note: This section of code can be improved by increasing and automating the amount of Initial Guesses to account for more local maximums when expanding and varying the constraints. 

Step 4: Output the Results
**Plot E(θ, r)** to visualize the energy as a surface plot using *meshgrid* and [surf](https://www.mathworks.com/help/matlab/ref/surf.html). Plot the optimal tilt angle and aspect ratio, and corresponding energy output onto the grid; the absolute maximum of the surface plot should align with the optimal point. Finally, print the optimal tilt angle and aspect ratio, and the Maximum energy output.


### Project Files
- [Model-2 Report](SolarPanel3_Final_Model2.pdf)
- [Model-2 MATLAB LiveScript](SolarPanel3_Final_Model2.mlx)

## Results


