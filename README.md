# Scientific Calculator via Numerical Methods on Arduino

This project implements a fully functional scientific calculator on an Arduino UNO. While most embedded calculators rely on pre-compiled standard math libraries, this project takes a first-principles approach: **computing complex transcendental functions (trigonometric, logarithmic, exponential) from scratch using the Runge-Kutta 4th Order (RK4) numerical method.**

## Project Overview
The goal of this project was to bridge the gap between numerical analysis and resource-constrained embedded systems. By treating mathematical functions as solutions to Ordinary Differential Equations (ODEs), the microcontroller evaluates complex equations step-by-step using numerical integration.

Along with advanced math, the calculator features a custom expression parser (following BODMAS), a multiplexed UI using Shift/Alpha states, and standard memory operations.

## Key Features
* **Custom Mathematical Core:** Uses RK4 and Newton's Method instead of standard library calls.
* **Expression Parser:** Evaluates complex strings following the BODMAS rule.
* **Multiplexed User Interface:** Utilizes a standard keypad with 'Shift' and 'Alpha' modes to access over 20+ functions.
* **Memory Management:** Full support for M+, M-, MR, and MC operations.

## The Mathematics (Under the Hood)
Instead of using lookup tables or standard libraries, this calculator solves ODEs to find function values. 

* **Trigonometry ($\sin(x), \cos(x)$):** Solved as a system of coupled ODEs.
* **Logarithms ($\ln(x)$):** Computed by solving $rac{dy}{dx} = rac{1}{x}$.
* **Exponentials ($e^x$):** Computed by solving $rac{dy}{dx} = y$.
* **Square Roots ($\sqrt{x}$):** Computed by solving $rac{dy}{dx} = rac{1}{2y}$.
* **Cube Roots ($\sqrt[3]{x}$):** Solved using Newton-Raphson iterations.

## Hardware Requirements
* Arduino UNO Microcontroller
* LCD Display (16x2 or 20x4)
* Matrix Keypad

## Interface & Usage
The keypad is multiplexed to allow a compact layout:
* **Default Mode:** Basic numbers (0-9) and arithmetic (+, -, *, /).
* **Shift Mode:** Access to $\sin$, $\cos$, $	an$, $\log$, $\ln$, memory operations, and roots.
* **Alpha Mode:** Access to mathematical constants ($\pi$, $e$), factorials, and variable manipulation.

---
*Developed as part of the course EE1003 - Scientific Programming for EE .*
