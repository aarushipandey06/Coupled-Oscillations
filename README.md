# Coupled Oscillations: Numerical Simulation and Analysis

## Overview

This project investigates the motion of two identical masses connected by three identical springs. The equations of motion are solved numerically to study the system's oscillatory behaviour, energy conservation, and normal-mode frequencies.

The numerical results are compared with theoretical predictions to examine the accuracy and limitations of the integration methods.

## Physical Model

The system consists of two equal masses connected by three identical springs.

![Schematic diagram of the coupled oscillation system](Images/coupled_oscillations_schematic.png)

### Simulation Parameters

- Mass of each block: 1.0 kg
- Spring constant: 1.0 N/m
- Initial conditions $(x_1,x_2,v_1,v_2)$: $(0.10,0,0,0)$
- Timestep: 0.001 s

The equations of motion are

$$
\ddot{x}_1 = \frac{-2kx_1+kx_2}{m}
$$

$$
\ddot{x}_2 = \frac{kx_1-2kx_2}{m}
$$

The theoretical normal-mode frequencies are

$$
f_1 = \frac{1}{2\pi}\sqrt{\frac{k}{m}},
\qquad
f_2 = \frac{1}{2\pi}\sqrt{\frac{3k}{m}}.
$$

For the parameters used in this simulation, $m=1.0\,\mathrm{kg}$ and $k=1.0\,\mathrm{N/m}$, the theoretical frequencies are approximately $0.15915\,\mathrm{Hz}$ and $0.27566\,\mathrm{Hz}$.

## Methods

- **Euler integration:** Numerical solution of the coupled equations of motion using the explicit Euler method.
- **Energy analysis:** Calculation of kinetic, potential, and total mechanical energy to investigate energy conservation.
- **Timestep convergence:** Investigation of how timestep size affects numerical energy error.
- **Euler vs RK4:** Comparison of energy stability over a longer simulation.
- **FFT analysis:** Extraction of normal-mode frequencies from simulated displacement data.                                                 
  
## Key Results

- The Euler method exhibits increasing energy drift over time.
- Reducing the timestep decreases the final energy error in the Euler simulation.
- RK4 exhibits substantially better energy stability than Euler for the tested timestep and simulation duration.
- The FFT estimates are close to the theoretical normal-mode frequencies, with discrepancies influenced by finite frequency resolution.

## Tools and Libraries

- Python
- NumPy
- Matplotlib
- SciPy

## How to Run

Open `coupled_oscillations.ipynb` in Google Colab or Jupyter Notebook.

Install the required libraries using:

```bash
pip install -r requirements.txt
```

Run the notebook cells in order to reproduce the simulations, plots, energy analysis, and frequency calculations.

## Conclusion

The simulations demonstrate the behaviour of a coupled oscillator system and illustrate the effects of numerical integration on energy conservation. The comparison between Euler and RK4 highlights the importance of integration method selection, while FFT analysis provides numerical estimates of the system's normal-mode frequencies that can be compared with analytical predictions.
