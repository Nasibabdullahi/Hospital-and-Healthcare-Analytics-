# BIT 2118: Scientific Computing Project Portfolio

**Student Name:** NASIB ABDULLAHI
**Admission Number:** BSCCS252600467
**Course Code & Title:** BIT2118 Scientific Computing  
**Institution:** Mount Kenya University  
**tittle:** Hospital and Healthcare Analytics  

---

## Overview

This repository contains the complete individual implementation of 19 scientific computing tasks (Tasks A through S / Tasks 02 through 20) for **BIT2118 Scientific Computing**. All tasks are modeled around a unified real-world domain: **Hospital and Healthcare Analytics**, demonstrating how numerical algorithms solve clinical, operational, financial, and physiological problems in a modern medical institution.

---

## Repository File Structure

| Task | Topic / Mathematical Focus | Python Script File |
| :--- | :--- | :--- |
| **Task A** | NumPy Arrays & Vectorized Calculations | `02_hospital_births.py` |
| **Task B** | Array Speed-Up & Vectorization | `03_delivery_durations.py` |
| **Task C** | Floating-Point Precision & Stability | `04_neonatal_precision.py` |
| **Task D** | Matrix Transformations & Determinants | `05_maternity_ward_matrices.py` |
| **Task E** | Systems of Linear Equations ($Ax = b$) | `06_hospital_linear_systems.py` |
| **Task F** | LU Decomposition & Shift Optimization | `07_hospital_lu.py` |
| **Task G** | Iterative Linear Solvers (Jacobi & Gauss-Seidel) | `08_nicu_thermal_iterative.py` |
| **Task H** | Eigenvalues & Infection Network Centrality | `09_hospital_infection_network.py` |
| **Task I** | Root Finding (Bisection & Fixed-Point) | `10_drug_equilibrium.py` |
| **Task J** | Root Finding (Newton-Raphson & Secant) | `11_mri_investment.py` |
| **Task K** | Systems of Nonlinear Equations | `12_chemo_optimization.py` |
| **Task L** | Interpolation (Cubic Splines) | `13_oxygen_interpolation.py` |
| **Task M** | Curve Fitting & Outbreak Forecasting | `14_epidemic_curve.py` |
| **Task N** | Numerical Differentiation | `15_tumor_growth_rate.py` |
| **Task O** | Numerical Integration (Simpson's Rule) | `16_iv_fluid_integration.py` |
| **Task P** | Ordinary Differential Equations (Euler Method) | `Task_17_drug_decay_euler.py` |
| **Task Q** | Numerical ODE Solvers (`solve_ivp`) | `18_epidemic_ode_scipy.py` |
| **Task R** | Constrained Optimization | `19_staffing_optimization.py` |
| **Task S** | Monte Carlo Simulation & Risk Analysis | `20_er_monte_carlo.py` |

---

## Detailed Task Documentation

### Task A: NumPy Arrays and Basic Numerical Computation
* **Script:** `02_hospital_births.py`
* **Scenario & Assumptions:** A maternity hospital records delivery counts per hour over 24 hours. Staffing hours follow a linear model ($y = 1.5x + 2.0$).
* **Input Data:** 24 hourly birth records across a single day.
* **Interpretation:** Mean births ($2.21\text{ births/hr}$) establish baseline capacity. Peak hours ($6\text{ births}$) determine maximum emergency staffing needs.

---

### Task B: Mathematical Functions and Vectorization
* **Script:** `03_delivery_durations.py`
* **Scenario & Assumptions:** Processing 1,000,000 maternal health delivery durations (in minutes) converted to hours and squared for variance modeling.
* **Input Data:** Array of $1,000,000$ delivery duration logs.
* **Interpretation:** Demonstrates C-level NumPy vectorization running $>50\times$ faster than standard Python `for` loops on large health datasets.

---

### Task C: Floating-Point Arithmetic and Numerical Errors
* **Script:** `04_neonatal_precision.py`
* **Scenario & Assumptions:** Neonatal ICU heart rate variability monitoring under tiny time steps ($10^{-4}$ to $10^{-12}$).
* **Input Data:** Micro-scale time step delta values ($x$).
* **Interpretation:** Illustrates catastrophic cancellation during direct subtraction and proves how rationalized formulas preserve precision down to 12 decimal places.

---

### Task D: Matrix Algebra and Matrix Operations
* **Script:** `05_maternity_ward_matrices.py`
* **Scenario & Assumptions:** Updating workload allocation across 4 maternity wards combining shift rotation ($30^\circ$) and scaling ($1.2\times$ capacity, $0.9\times$ staff).
* **Input Data:** $4 \times 2$ ward metrics matrix and $2 \times 2$ composite transformation matrix.
* **Interpretation:** Multiplies matrices to update all ward metrics simultaneously. A non-zero determinant ($1.08$) proves invertibility.

---

### Task E: Solution of Systems of Linear Equations
* **Script:** `06_hospital_linear_systems.py`
* **Scenario & Assumptions:** Allocating ICU and HDU patient blocks given total bed (20) and ventilator (72) equipment limits.
* **Input Data:** Coefficient matrix $A$ (resource rates per block) and vector $b = [20, 72]^T$.
* **Interpretation:** `np.linalg.solve` yields exact block counts ($3$ ICU, $4$ HDU) with a zero residual norm ($\|r\| = 0.0$).

---

### Task F: Gaussian Elimination and LU Decomposition
* **Script:** `07_hospital_lu.py`
* **Scenario & Assumptions:** Allocating maternity resources across Morning, Evening, and Night shifts using a fixed ward relationship matrix.
* **Input Data:** Fixed structural matrix $A$ and shift resource vectors $b_1, b_2, b_3$.
* **Interpretation:** LU Decomposition factors matrix $A$ once (`lu_factor`), enabling fast repeated solves (`lu_solve`) for each shift.

---

### Task G: Iterative Methods for Linear Systems
* **Script:** `08_nicu_thermal_iterative.py`
* **Scenario & Assumptions:** Modeling 1D steady-state heat distribution across 5 NICU incubator sensors between a $37^\circ\text{C}$ heater and $22^\circ\text{C}$ room wall.
* **Input Data:** $5 \times 5$ tridiagonal thermal matrix $A$ and boundary vector $b$.
* **Interpretation:** Both Jacobi and Gauss-Seidel converge on exact interior temperatures, with Gauss-Seidel reaching tolerance in fewer iterations.

---

### Task H: Eigenvalues and Eigenvectors
* **Script:** `09_hospital_infection_network.py`
* **Scenario & Assumptions:** Infection transmission modeling across 4 hospital wards based on staff movement adjacency.
* **Input Data:** $4 \times 4$ ward connection adjacency matrix.
* **Interpretation:** The dominant eigenvector identifies the ICU and Surgery wards as high-centrality transmission hubs requiring targeted sterilization.

---

### Task I: Root Finding: Bisection and Fixed-Point Methods
* **Script:** `10_drug_equilibrium.py`
* **Scenario & Assumptions:** Finding the IV drug infusion dose where drug inflow balances biological clearance.
* **Input Data:** Nonlinear clearance balance function $f(D) = D - 25 - 10e^{-D/20}$.
* **Interpretation:** Bisection and fixed-point methods converge to the exact equilibrium dose ($\approx 27.6\text{ mg}$).

---

### Task J: Root Finding: Newton-Raphson and Secant Methods
* **Script:** `11_mri_investment.py`
* **Scenario & Assumptions:** Financial appraisal of a \$1,000,000 MRI equipment acquisition via Internal Rate of Return (IRR).
* **Input Data:** Cash flow vector across 4 operating years.
* **Interpretation:** Newton-Raphson computes the exact discount rate where Net Present Value (NPV) equals zero to evaluate capital investment viability.

---

### Task K: Polynomial and Nonlinear Equation Solving
* **Script:** `12_chemo_optimization.py`
* **Scenario & Assumptions:** Finding joint dosage for two chemotherapy agents under overlapping toxicity and efficacy boundaries.
* **Input Data:** System of 2 nonlinear equations representing circular safety and parabolic efficacy.
* **Interpretation:** `scipy.optimize.root` locates the optimal dosage point ($x, y$) satisfying both clinical constraints.

---

### Task L: Interpolation
* **Script:** `13_oxygen_interpolation.py`
* **Scenario & Assumptions:** Estimating unmeasured intermediate blood oxygen ($SpO_2$) values between 4-hour nurse checks.
* **Input Data:** Discrete time hours $[0, 4, 8, 12, 16, 20, 24]$ and measured $SpO_2$ percentages.
* **Interpretation:** Cubic Spline interpolation generates a smooth, physiologically accurate curve between recorded readings.

---

### Task M: Curve Fitting and Approximation
* **Script:** `14_epidemic_curve.py`
* **Scenario & Assumptions:** Forecasting hospital bed demand on Day 10 during an emerging local viral outbreak.
* **Input Data:** 7 daily cumulative case counts.
* **Interpretation:** Quadratic curve fitting (`curve_fit`) extrapolates outbreak trajectory to predict future bed capacity requirements.

---

### Task N: Numerical Differentiation
* **Script:** `15_tumor_growth_rate.py`
* **Scenario & Assumptions:** Calculating instantaneous growth velocity ($\text{cm}^3/\text{week}$) of a tumor from weekly MRI measurements.
* **Input Data:** Weekly tumor volume series over 6 weeks.
* **Interpretation:** Central difference approximation shows declining growth rates, verifying positive therapeutic response.

---

### Task O: Numerical Integration
* **Script:** `16_iv_fluid_integration.py`
* **Scenario & Assumptions:** Integrating IV pump flow rate ($\text{ml/hr}$) over 12 hours to determine total fluid volume administered.
* **Input Data:** Flow rate measurements taken every 2 hours.
* **Interpretation:** Simpson's rule integration computes the exact total accumulated fluid volume ($\text{ml}$) to prevent hydration errors.

---

### Task P: Ordinary Differential Equations - Euler Method
* **Script:** `17_drug_decay_euler.py`
* **Scenario & Assumptions:** Modeling first-order elimination decay of an IV antibiotic in the bloodstream over 30 hours ($dC/dt = -k \cdot C$).
* **Input Data:** Initial concentration $C_0 = 90\text{ mg/L}$, elimination constant $k = 0.12$.
* **Interpretation:** Step-by-step Euler integration tracks concentration decay to determine optimal re-dosing times.

---

### Task Q: Numerical Solution of ODEs Using SciPy
* **Script:** `18_epidemic_ode_scipy.py`
* **Scenario & Assumptions:** Simulating infectious disease spread dynamics within a hospital ward.
* **Input Data:** Initial susceptible population proportion $S_0 = 1.0$ over 5 days.
* **Interpretation:** SciPy's adaptive `solve_ivp` solver accurately models population decay under contagion exposure.

---

### Task R: Numerical Optimization
* **Script:** `19_staffing_optimization.py`
* **Scenario & Assumptions:** Minimizing shift staffing costs between Registered Nurses (\$300) and Nursing Assistants (\$150) under a 100-care-unit minimum constraint.
* **Input Data:** Cost vector and linear inequality care unit constraint.
* **Interpretation:** `scipy.optimize.minimize` calculates the optimal staff mix that fulfills legal safety requirements at minimum expense.

---

### Task S: Random Numbers and Monte Carlo Methods
* **Script:** `Task_20_er_monte_carlo.py`
* **Scenario & Assumptions:** Simulating 100,000 daily Emergency Room patient arrival scenarios to assess overflow risk against a 50-bed limit.
* **Input Data:** Normal arrival distribution ($\mu = 40$, $\sigma = 8$).
* **Interpretation:** Monte Carlo simulation quantifies the exact overflow probability to support proactive bed expansion planning.

---

## Author Verification

* **Student:** nasib abdullahi
* **Admission No:** BSCCS252600467
* **Course:** BIT2118 Scientific Computing