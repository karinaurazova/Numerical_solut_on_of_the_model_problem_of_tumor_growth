# Tumor Growth Dynamics Modeling with Substance Concentration

This repository contains a numerical solution to a system of differential equations describing tumor growth dynamics in relation to regulating substance concentration.

## System of Equations

The model is described by the following system:

```
dy₁/dt = (-λ₁ + β₁ * y₂^(2/3) * (1 - y₁/c) / (1 + y₁)) * y₁
dy₂/dt = λ₂ * y₂ - β₂ * y₂² / (1 + y₁)
```

where:
- y₁(t) - tumor size at time t
- y₂(t) - regulating substance concentration
- λ₁, λ₂, β₁, β₂, c - model parameters

## Code Implementation

The code implements:
1. Numerical solution using 4th-order Runge-Kutta method
2. Phase portraits and time dependence visualizations
3. Integration step error analysis
4. Step size optimization for given precision

### Main Functions:
- `f(t, y, beta2)` - computes the right-hand side of the system
- `runge_kutta_4()` - 4th-order Runge-Kutta implementation
- `calculate_errors()` - parallel error computation for different step sizes

### Dependencies:
- `numpy` - numerical computations
- `matplotlib` - results visualization
- `numba` - JIT compilation for performance

## Installation and Execution

```bash
pip install numba numpy matplotlib
python Numerical_solut_on_of_the_model_problem_of_tumor_growth.ipynb
```

## Results

The program generates:
1. System phase portraits for different β₂ parameters
2. Time dependence plots of y₁(t) and y₂(t)
3. Integration error vs step size dependence
4. Optimal step sizes for given precision levels

Example of optimal step output:
```
β₂      ε=1e-3      ε=1e-4      ε=1e-6
3.0     1.00e-3     3.16e-4     3.16e-5
3.48    1.00e-3     3.16e-4     3.16e-5
5.0     1.00e-3     3.16e-4     3.16e-5
```

## License

MIT License
