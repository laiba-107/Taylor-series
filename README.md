# Taylor-series
This repository contains a Python script for computing and visualizing the Taylor polynomial of a given function. The script prompts the user for a function, the center point of the Taylor series, and the desired degree of the polynomial. It then calculates the Taylor polynomial and plots it alongside the original function for comparison.
# Features
Interactive Input: Users can input any function  𝑓(𝑥), the center c, and the polynomial degree 𝑛 interactively.
Symbolic Computation: Utilizes sympy for symbolic differentiation and polynomial construction.
Numerical Evaluation: Converts symbolic expressions to numerical functions using lambdify.
Visualization: Uses matplotlib to plot the original function and its Taylor polynomial approximation.

# Dependencies
sympy: For symbolic mathematics.
numpy: For numerical operations.
matplotlib: For plotting.

# Usage
Run the script: Execute the script in a Python environment.
Input the function: When prompted, enter the function  f(x) in terms of x.
Enter the center 𝑐
c: Input the center point for the Taylor series.
Specify the degree n: Enter the desired degree of the Taylor polynomial.
View the results: The script will display the Taylor polynomial and plot both the function and its approximation.
Example
Enter the function f(x) in terms of x: sin(x)
Enter the center c of the Taylor series: 0
Enter the degree n of the Taylor polynomial: 4
This example will compute the 4th-degree Taylor polynomial for sin(x) centered at 0 and plot it alongside the original sine function.
