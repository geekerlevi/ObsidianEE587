###### Topic: Thermistors as a Reduced-Order Model for Memristor-Type Nonlinear Dynamics and Hysteresis

###### Motivation
Memristive systems exhibit nonlinear, state-dependent voltage-current behaviors with hysteresis. 

This project investigates how a thermistor, with temperate-dependent resistance and internal thermal dynamics, can be modelled as a low-order nonlinear dynamical system that reproduces memristive hysteresis behavior.

The objective is to move beyond numerical observation of hysteresis and develop a rigorous analytical understanding of the following:
- The dynamical origin of hysteresis
- Frequency-dependent loop behavior
- Stability and bifurcation
- Hysteresis Approximation 
###### Mathematical Model
Electrical relation: 
$v(t)=R(T)i(t)$

Thermal dynamics: 
$C_{th} \dot{T}=-\frac{T-T_a}{R_{th}}+i^2 R(T)$

For an NTC thermistor:
$R(T)=R_0 e^{(\beta(\frac{1}{T}-\frac{1}{T_0}))}$

After nondimensionalization, the system becomes a nonlinear first-order ODE:
$\dot{\theta}=-\theta+\kappa i^2 e^{\gamma \theta}$

This structure matches the general memristive system framework by Leon Chua.

###### Research Questions
1. Under sinusoidal excitation, when does the system behave pinched hysteresis loops?
2. How does hysteresis area scale with excitation frequency?
3. Does a slow-fast decomposition explain memory behavior?
4. Are there amplitude-induced bifurcation or thermal runaway behaviors?
5. Can the observed hysteresis be approximation by Preisach-type operators?

###### Methodology
1. Nonlinear modeling and nondimensionalization
2. Linearization and local stability analysis
3. Frequency response and small-signal asymptotic
4. Bifurcation analysis wrt input amplitude
5. Numerical analysis (MATLAB)
6. Hysteresis area quantification
7. Approximation via Preisach operation

###### Expected Outcomes
1. Rigorous explanation of hysteresis mechanism
2. Frequency scaling for loop area
3. Bifurcation characterization of thermal nonlinearity
4. Quantitative comparison between physical thermistor dynamics and hysteresis operators

