# Gradient Descent

given some data, the gradient descent will provide a line that helps explain thedata

PREDICTED Y = INTERCEPT x SLOPE(x)

## Gradient Descent Optimization For Single Variable
We know slope

1. Plug in the **least squares estimate** for the slope
	- for each point (x,y), calculate x<sup>2</sup> and xy
	- find ∑x, ∑y, ∑x<sup>2</sup>, and ∑xy
	- slope = m = (NUMBER OF POINTS (∑xy) - (∑x∑y)) / (NUMBER OF POINTS (∑x<sup>2</sup>) - (∑x)<sup>2</sup>)

2. Pick a random number as the INTERCEPT

3. Find SUM OF SQUARED RESIDUALS = ∑(OBSERVED - PREDICTED)<sup>2</sup> = ∑(OBSERVED - (INTERCEPT + SLOPE(X)))<sup>2</sup>

	- STEPS 2 AND 3 WILL END UP GIVING A FORMULA THAT ALLOWS USER TO PLUG N ANY VALUE FOR THE INTERCEPT AND GET THE SUM OF SQUARED RESIDUALS

4. Find the (d/dINTERCEPT)(SUM OF SQUARED RESIDUALS)

5. Start plugging in value for INTERCEPT to get as close to 0 for slope of tangent line
	- remember we are using the derived version of the SUM OF SQUARED RESIDUALS
	- size of step relates to the slope

6. Multiply the guessed intercept tangent line slope by a "learning rate" to get the step size

7. NEW INTERCEPT = OLD INTERCEP - STEP SIZE

8. Plug in NEW INTERCEPT into the equation

9. Keep going until STEP SIZE < 0.001
	- or more than 1000 steps 

## Gradient Descent Optimization For Two Variables
We don't know slope

1. Use SUM OF SQUARED RESIDUALS as the loss function

2. Find the (d/dINTERCEPT)(SUM OF SQUARED RESIDUALS)

3. Find the (d/dSLOPE)(SUM OF SQUARED RESIDUALS)

4. Pick a random number for INTECEPT and SLOPE

5. Plug numbers into both formulas

6. Find STEP SIZE = INTERCEPT x LEARNING RATE

7. Find STEP SIZE = SLOPE x LEARNING RATE

8. NEW INTERCEPT = OLD INTERCEPT - STEP SIZE

9. NEW SLOPE = OLD SLOPE - STEP SIZE

10. Keep going until max step size or step size very small

## Gradient Descent Optimization For More Than Two Variables

Basically do the same thing as two variable, but we would be deriving more since we would have more unknowns

## Summary
Basic steps to finding the graident descent for optimization

1. Take the derivative of the LOSS FUNCTION / SUM OF SQUARED RESIDUALS for each parameter in it
	- take the gradient of the loss function

2. Pick random values for the parameters

3. Plug the parameter values into the derivatives

4. Find the STEP SIZE = PARAMETER x LEARNING RATE 

5. Find the NEW PARAMETER = OLD PARAMETER - STEP SIZE

6. Repeat 3->5 until u reach limit