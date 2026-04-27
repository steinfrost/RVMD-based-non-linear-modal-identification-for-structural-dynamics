# RVMD-based-non-linear-modal-identification-for-structural-dynamics

## Abstract

This work presents a MATLAB framework for simulating nonlinear multi-degree-of-freedom (MDOF) systems and analyzing their responses using Reduced Order Variational Mode Decomposition (RVMD). The study investigates whether RVMD can extract physically meaningful modal information under nonlinear dynamics and measurement noise. Results demonstrate consistent modal identification, robustness to noise, and sensitivity to nonlinear effects.

---

## 1. Problem Statement

Structural responses under realistic conditions are influenced by:

* nonlinear behavior,
* measurement noise,
* modal coupling.

These effects limit the applicability of classical modal analysis. This work evaluates RVMD as a **data-driven modal decomposition tool** for such scenarios.

---

## 2. Methodology (Concise)

### Structural Model

A 3-DOF system governed by:

M ẍ + C ẋ + K x + fₙₗ(x) = F(t)

Nonlinearity includes:

* cubic stiffness,
* breathing crack,
* combined effects.

---

### Simulation

* Numerical integration (`ode45`)
* Broadband/chirp excitation
* Additive noise (controlled SNR)
* Steady-state extraction

---

### Analysis Pipeline

1. FFT → baseline frequency content
2. Hilbert transform → instantaneous frequency & amplitude
3. RVMD → modal decomposition
4. Validation → frequency error + MAC
5. Backbone comparison → nonlinear consistency

---

## Results

### Modal Identification
RVMD accurately recovers modal frequencies for both linear and nonlinear systems with errors below **1%**.  
Mode shapes show near-perfect agreement with analytical solutions (**MAC ≈ 1.0**), indicating high-fidelity decomposition.

**Figure 1:** True vs RVMD modal frequencies  
**Figure 2:** Mode shapes comparison (with MAC)  

---

### Nonlinear Behavior
Under nonlinear conditions, RVMD maintains stable performance and captures **effective modal dynamics**.  
Estimated frequencies align closely with **nonlinear backbone predictions** (error < 1%), demonstrating sensitivity to amplitude-dependent effects.

**Figure 3:** PSD comparison (linear vs nonlinear)  
**Figure 4:** Backbone curve (frequency vs amplitude)  

---

### Noise Robustness
RVMD remains stable under noise, with frequency errors typically below **1%** across varying SNR levels.  
Modal estimates are smoother and less sensitive compared to raw signals.

**Figure 5:** Frequency error vs SNR  

---

### Summary
- Accurate modal frequencies (**<1% error**)  
- Near-perfect mode shape recovery (**MAC ≈ 1.0**)  
- Stable under nonlinear dynamics and noise  
- Strong agreement with nonlinear backbone behavior

- 

## 5. Conclusion

This study demonstrates that RVMD is a promising tool for modal analysis in nonlinear structural systems. While not achieving perfect modal disentanglement, it provides consistent and physically meaningful representations under challenging conditions.

---

## 6. Current Status

Ongoing work includes:

* improved damage indicators
* environmental effect modeling
* validation on experimental datasets

---
