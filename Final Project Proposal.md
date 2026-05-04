**Topic: <u>Thermistors as a model for memristor nonlinear dynamics</u>** [1]
## Project Motivation

Systems with memristors relates to history-dependent input-output behaviors, nonlinear hysteresis and internal state changes. As those memristors are introduced abstractly, thermistor with mathematical reliability practically providing a great example of memristive dynamics.

This project would investigate thermistors as nonlinear dynamical systems with memory, focusing on how coupled electrical-thermal feedback produces hysteresis, equilibria, and bifurcations.

## System Description and Model

The thermistor is modelled as a nonlinear resistor which is temperature-dependent, coupled with first-order thermal dynamical equations.

In continuous time, the model can be represented by:
$i(t)=\frac{v(t)}{R(T)}$
$\dot{T}=-\frac{1}{\tau} (T-T_a)+\alpha i^2 R(T)$
where $T$ is the internal temperature state, $v(t)$ is the applied voltage input, and $R(T)$ follows a nonlinear temperature-dependent relationship.

## Research Questions

The project will go through the following nonlinear dynamics problems:
1. Equilibria and Stability
How many thermal equilibria exist under constant excitation?
Under what condition does thermal runaway occur?
2. Bifurcation Behavior
How do equilibria change as input voltage amplitude varies?
Is there a saddle-node or loss of stability bifurcation?
3. Hysteresis and Memory
How does sinusoidal excitation generate pinched hysteresis loops in the $i-v$ plane?
How does loop area depend on excitation frequency and amplitude?

## Methodologies

Continuous-time nonlinear ODE modelling.
Numerical simulation of thermal-electrical dynamics.
Phase-plane and time-domain analysis.
Parameter sweeps to identify bifurcations.
Frequency-dependent hysteresis analysis.

*All analysis would be conducted using MATLAB.*
## Expected Outcomes

Identification of nonlinear equilibria and stability regions
Demonstration of memristive hysteresis arising from internal state dynamics.
Quantitative characterization of bifurcation behavior.
Clear illustration of memory effects in a physically grounded system.
## Proposed Deliverables

Final report with equations, simulations and discussion.
Numerical simulation codes.
Plots illustrating equilibria, hysteresis and bifurcations.

## Reference
[1] : https://ocw.mit.edu/courses/12-006j-nonlinear-dynamics-chaos-fall-2022/pages/final-project/
