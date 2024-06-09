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

# code
from sympy import symbols, diff, factorial, sympify, lambdify
import numpy as np
import matplotlib.pyplot as plt

def taylor_polynomial_and_graph():
    f_x = input("Enter the function f(x) in terms of x: ")
    c = float(input("Enter the center c of the Taylor series: "))
    n = int(input("Enter the degree n of the Taylor polynomial: "))
    
    x = symbols('x')
    f = sympify(f_x)
    
    P_n = 0  
    
    for i in range(n+1):
        f_i = diff(f, x, i).subs(x, c)
        P_n += f_i/factorial(i) * (x-c)**i
        
    print(f"P_{n}(x) about c = {c}:", P_n)
    
    f_lambdified = lambdify(x, f, modules=['numpy'])
    P_n_lambdified = lambdify(x, P_n, modules=['numpy'])
    
    x_vals = np.linspace(c - 5, c + 5, 400)
    f_vals = f_lambdified(x_vals)
    P_n_vals = P_n_lambdified(x_vals)
    
    plt.figure(figsize=(10, 6))
    plt.plot(x_vals, f_vals, label=f'f(x) = {f_x}')
    plt.plot(x_vals, P_n_vals, label=f'P_{n}(x) Taylor Polynomial', linestyle='--')
    plt.legend()
    plt.xlabel('x')
    plt.ylabel('y')
    plt.title(f'Function vs. Taylor Polynomial Approximation around c = {c}')
    plt.grid(True)
    plt.show()

taylor_polynomial_and_graph()
