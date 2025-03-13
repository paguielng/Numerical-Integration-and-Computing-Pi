# MIT OpenCourseWare - Single Variable Calculus (18.01)
## Lecture 25: Numerical Integration and Computing π

### Introduction

This lecture continues the discussion on numerical methods for integration, focusing on practical examples and applications. The lecture covers:

1. Numerical integration methods (Trapezoidal Rule and Simpson's Rule)
2. A practical example of numerical integration
3. Computing the value of √(π/2)
4. Concluding remarks on the unit

### 1. Numerical Integration Methods

#### 1.1 Example: Integrating 1/x from 1 to 2

The lecture begins with a practical example of numerical integration, using the integral:

$$\int_{1}^{2} \frac{dx}{x}$$

This integral has a known analytical solution:

$$\int_{1}^{2} \frac{dx}{x} = \ln(x) \bigg|_{1}^{2} = \ln(2) - \ln(1) = \ln(2) \approx 0.693147$$

The professor uses this example to demonstrate numerical integration methods because:
- The exact answer is known (for comparison)
- The function 1/x is relatively simple to evaluate

#### 1.2 Trapezoidal Rule

The Trapezoidal Rule approximates the area under a curve by dividing it into trapezoids.

For this example, the interval [1,2] is divided into just 2 sub-intervals (a very coarse approximation), giving 3 points: x = 1, x = 3/2, and x = 2.

The function values at these points are:
- f(1) = 1
- f(3/2) = 2/3
- f(2) = 1/2

The Trapezoidal Rule formula is:

$$\int_{a}^{b} f(x) dx \approx \Delta x \left[ \frac{f(x_0)}{2} + f(x_1) + f(x_2) + ... + f(x_{n-1}) + \frac{f(x_n)}{2} \right]$$

Where:
- Δx = (b-a)/n = (2-1)/2 = 1/2
- The pattern of coefficients is (1/2, 1, 1, ..., 1, 1/2)

Applying the formula:

$$\int_{1}^{2} \frac{dx}{x} \approx \frac{1}{2} \left[ \frac{1}{2} \cdot 1 + \frac{2}{3} + \frac{1}{2} \cdot \frac{1}{2} \right]$$

The professor mentions that this approximation gives about 0.96, which is quite far from the exact value of 0.693147.

#### 1.3 Simpson's Rule

Simpson's Rule provides a more accurate approximation by fitting parabolas through sets of three points.

The Simpson's Rule formula is:

$$\int_{a}^{b} f(x) dx \approx \frac{\Delta x}{3} \left[ f(x_0) + 4f(x_1) + f(x_2) \right]$$

For more points, the pattern of coefficients is (1, 4, 2, 4, 2, ..., 4, 1) for more intervals.

Applying Simpson's Rule to the same example:

$$\int_{1}^{2} \frac{dx}{x} \approx \frac{1}{6} \left[ 1 + 4 \cdot \frac{2}{3} + \frac{1}{2} \right] = \frac{1}{6} \left[ 1 + \frac{8}{3} + \frac{1}{2} \right] \approx 0.6944444$$

This gives approximately 0.6944444, which is remarkably close to the exact value of 0.693147.

#### 1.4 Error Analysis for Simpson's Rule

The professor explains that the error in Simpson's Rule is proportional to (Δx)⁴:

$$|Simpson's - Exact| \approx O((\Delta x)^4)$$

This means:
- If Δx = 0.1 (dividing into 10 intervals), the error would be approximately 10⁻⁴
- This provides about 4 digits of accuracy with a reasonable number of calculations

Simpson's Rule works so well because:
- It gives exact results for polynomials up to degree 3 (constants, lines, parabolas, and cubics)
- This explains the fourth-order accuracy

#### 1.5 Limitations and Cautions

The professor warns about situations where numerical integration methods may fail:
- When the function has singularities (e.g., 1/x near x = 0)
- When the function or its derivatives are not smooth
- When there's a large amount of area concentrated in a small region

#### 1.6 Remembering the Formulas

A useful way to remember the coefficients in these formulas is to check that they give the exact answer for the simplest case: f(x) = 1.

For the Trapezoidal Rule with f(x) = 1:
$$\Delta x \left[ \frac{1}{2} + 1 + 1 + ... + 1 + \frac{1}{2} \right] = \Delta x \left[ \frac{1}{2} + (n-1) + \frac{1}{2} \right] = \Delta x \cdot n = b-a$$

This confirms that the Trapezoidal Rule gives the exact area of a rectangle with base (b-a) and height 1.

### 2. Computing √(π/2)

The second part of the lecture addresses the computation of √(π/2), which the professor describes as "one of the most famous computations in calculus."

#### 2.1 Connection to Previous Work

The professor connects this to previous work on the volume of revolution:

$$V = \int_{0}^{\infty} 2\pi r e^{-r^2} dr = \pi$$

This was calculated using the shell method, where:
- 2πr is the circumference of the shell
- e^(-r²) is the height of the shell
- dr is the thickness of the shell

The calculation proceeds as follows:
$$V = \int_{0}^{\infty} 2\pi r e^{-r^2} dr = 2\pi \int_{0}^{\infty} r e^{-r^2} dr$$

Using the substitution u = r², du = 2r dr:
$$V = 2\pi \int_{0}^{\infty} \frac{1}{2} e^{-u} du = \pi \int_{0}^{\infty} e^{-u} du = \pi [- e^{-u}]_{0}^{\infty} = \pi [0 - (-1)] = \pi$$

#### 2.2 The Bell Curve and Its Area

The professor introduces:

$$Q = \int_{-\infty}^{\infty} e^{-x^2} dx$$

This represents the area under the bell curve (Gaussian function).

The key insight is that:
$$V = Q^2$$

Since we already know V = π, this means:
$$Q^2 = \pi$$
$$Q = \sqrt{\pi}$$

#### 2.3 Connection to Error Function

The professor connects this to the error function discussed earlier:

$$\text{erf}(x) = \frac{2}{\sqrt{\pi}} \int_{0}^{x} e^{-t^2} dt$$

The limit as x approaches infinity:
$$\lim_{x \to \infty} \text{erf}(x) = \frac{2}{\sqrt{\pi}} \cdot \frac{\sqrt{\pi}}{2} = 1$$

This confirms that:
$$\int_{0}^{\infty} e^{-x^2} dx = \frac{\sqrt{\pi}}{2}$$

Therefore:
$$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$$

#### 2.4 Three-Dimensional Visualization

The professor uses a three-dimensional visualization to explain why V = Q².

The approach involves:
- Setting up a coordinate system with x, y, and z axes
- Visualizing e^(-r²) as a "hump" in three dimensions
- Taking slices along different values of y
- Showing how these slices relate to the original integrals

The key insight is to consider the double integral:
$$\iint e^{-(x^2+y^2)} dx dy$$

This can be evaluated as:
$$\left(\int_{-\infty}^{\infty} e^{-x^2} dx\right) \cdot \left(\int_{-\infty}^{\infty} e^{-y^2} dy\right) = Q \cdot Q = Q^2$$

But it can also be evaluated using polar coordinates:
$$\int_{0}^{2\pi} \int_{0}^{\infty} e^{-r^2} r dr d\theta = 2\pi \int_{0}^{\infty} r e^{-r^2} dr = \pi$$

Therefore, Q² = π, which means Q = √π.

### 3. Conclusion

The lecture concludes by tying together the numerical integration methods and the computation of √(π/2), emphasizing the importance of these techniques in calculus and their applications.

The professor mentions that these topics complete the unit on integration techniques, which has covered:
- Basic integration methods
- Integration by parts
- Partial fractions
- Numerical integration
- Applications to volumes and special constants

### Key Takeaways

1. **Numerical Integration Methods**:
   - Trapezoidal Rule: Simple but less accurate
   - Simpson's Rule: More accurate, especially for smooth functions
   - Error in Simpson's Rule is proportional to (Δx)⁴

2. **Important Constants**:
   - The integral of e^(-x²) from -∞ to ∞ equals √π
   - The integral of e^(-x²) from 0 to ∞ equals √(π/2)
   - These values are fundamental in probability theory and statistics

3. **Integration Techniques**:
   - Different methods are appropriate for different types of integrals
   - Understanding the limitations of each method is crucial
   - Numerical methods provide practical approaches when analytical solutions are difficult

### Practice Problems

1. Use the Trapezoidal Rule with n = 4 to approximate ∫₀¹ x² dx.
2. Use Simpson's Rule with n = 4 to approximate the same integral and compare with the exact answer.
3. Estimate the error in each approximation based on the error formulas discussed.
