Below is a revised version formatted as a GitHub README. In this version the equations and descriptions have been refined to reflect common graduate‐level treatments found in modern engineering literature. (Note that native GitHub Markdown does not render LaTeX by default—if you require rendered mathematics you may consider using a GitHub Pages site with MathJax or another converter.)

---

# Graduate-Level Engineering Equations

This document summarizes a set of core equations and gain models frequently encountered in graduate-level engineering. The content has been updated for clarity and accuracy based on standard texts in the field.

## Table of Core Equations

| **Equation Name** | **Formula** | **Description / Context** |
|-------------------|-------------|---------------------------|
| **1. Poisson Equation** | $\(\nabla^2 \phi = -\frac{\rho}{\epsilon_0}\)$ | Governs the electrostatic potential \(\phi\) (or gravitational potential by analogy). Here, \(\rho\) is the charge density and \(\epsilon_0\) is the permittivity of free space. <br>**Ref:** Jackson, *Classical Electrodynamics* |
| **2. Poisson-Boltzmann Equation** | $\(\nabla^2 \psi = \kappa^2 \sinh(\psi)\)$ | A nonlinear equation that appears in the statistical mechanics of electrolytes and colloidal systems. \(\kappa\) is the inverse Debye length and \(\psi\) is a dimensionless potential. <br>**Ref:** Debye–Hückel; Gouy–Chapman theory |
| **3. Conductivity Equation** | $\(\mathbf{J} = \sigma \mathbf{E}\)$ | Differential form of Ohm’s law relating the current density \(\mathbf{J}\) to the electric field \(\mathbf{E}\) through the conductivity \(\sigma\). <br>**Ref:** Standard continuum electrodynamics texts |
| **4. Bragg’s Law** | $\(n\lambda = 2d\sin(\theta)\)$ | Describes diffraction from crystal planes (spacing \(d\)); \(n\) is an integer, \(\lambda\) is the wavelength, and \(\theta\) is the diffraction angle. <br>**Ref:** Kittel, *Introduction to Solid State Physics* |
| **5. Fick’s First Law** | $\(J = -D \nabla c\)$ | Relates the diffusive flux \(J\) to the concentration gradient \(\nabla c\), where \(D\) is the diffusion coefficient. <br>**Ref:** Bird, Stewart, \& Lightfoot, *Transport Phenomena* |
| **6. Fick’s Second Law** | $\(\frac{\partial c}{\partial t} = D \nabla^2 c\)$ | Governs the time evolution of concentration \(c\); derived from Fick’s first law and conservation of mass. |
| **7. Optical Gain Equation** | $\(g(N) \approx \sigma \, [N - N_\mathrm{tr}]\)$ | A linearized model for optical gain in laser media; \(\sigma\) is the gain cross section, \(N\) is the carrier (inversion) density, and \(N_\mathrm{tr}\) is the transparency density. <br>**Ref:** Svelto, *Principles of Lasers* |
| **8. Resonance Frequency** | $\( \omega_0 = \sqrt{\frac{k}{m}} \)$ (mechanical) <br> $\(\omega_0 = \frac{1}{\sqrt{LC}}\)$ (electrical) | The natural frequency of a harmonic oscillator. The mechanical version uses the spring constant \(k\) and mass \(m\); the electrical version applies to LC circuits. |
| **9. Tunneling Probability** | $\(T(E) \approx e^{-2\kappa a}, \quad \kappa = \frac{\sqrt{2m\,(V_0 - E)}}{\hbar}\)$ | Approximate transmission probability (WKB approximation) for a particle of energy \(E\) through a potential barrier of width \(a\) and height \(V_0\). <br>**Ref:** Griffiths, *Introduction to Quantum Mechanics* |
| **10. Efficiency Equation** | $\(\eta = \frac{P_\mathrm{out}}{P_\mathrm{in}}\)$ | A generic definition of efficiency as the ratio of output power to input power. <br>**Ref:** Standard thermodynamics/engineering texts |
| **11. Mean Free Path** | $\(\ell = \frac{1}{n\,\sigma_\mathrm{sc}}\)$ | The average distance \(\ell\) a particle travels between collisions; \(n\) is the number density of scatterers and \(\sigma_\mathrm{sc}\) is the scattering cross section. <br>**Ref:** Ashcroft \& Mermin, *Solid State Physics* |
| **12. Quality Factor** | $\(Q = \frac{\omega_0}{\Delta \omega}\)$ | A dimensionless measure of the sharpness of a resonance, with \(\omega_0\) the resonant frequency and \(\Delta \omega\) the bandwidth. |
| **13. Scattering Parameters** | $\mathbf{b}$ = $S$\, $\mathbf{a}$ For 2-port networks: $\begin{pmatrix}b_1\\b_2\end{pmatrix}$ = $\begin{pmatrix}S_{11}&S_{12}\\S_{21}&S_{22}\end{pmatrix}$ $\begin{pmatrix}a_1\\a_2\end{pmatrix}$ | Used in RF/microwave engineering to characterize reflection and transmission through networks. <br>**Ref:** Pozar, *Microwave Engineering* |
| **14. Transfer (ABCD) Parameters** | $\(\begin{pmatrix}V_1\\I_1\end{pmatrix}=\begin{pmatrix}A\&B\\C\&D\end{pmatrix}\begin{pmatrix}V_2\\-I_2\end{pmatrix}\)$ | Characterizes two-port networks by relating input and output voltages/currents. |
| **15. Harmonic Oscillator** | $\(\frac{d^2 x}{dt^2} + \omega_0^2 x = 0\)$ | The classical equation of motion for a mass–spring system (or its analogs). |
| **16. Anharmonic Oscillator** | $\(\frac{d^2 x}{dt^2} + \omega_0^2 x + \alpha x^3 = 0\)$ | A model incorporating a nonlinear (e.g., cubic) correction to the harmonic oscillator, capturing deviations seen in real systems. <br>**Ref:** Landau \& Lifshitz, *Mechanics* |
| **17. Quantum Harmonic Oscillator** | $\(\hat{H}\psi = \Bigl[-\frac{\hbar^2}{2m}\frac{d^2}{dx^2} + \frac{1}{2} m\,\omega^2 x^2\Bigr]\psi = E\psi\)$ | A solvable model in quantum mechanics with energy levels \(E_n = \hbar\omega \left(n+\tfrac{1}{2}\right)\). <br>**Refs:** Sakurai; Griffiths |
| **18. Quantum Anharmonic Oscillator** | $\(\hat{H}\psi = \Bigl[-\frac{\hbar^2}{2m}\frac{d^2}{dx^2} + \frac{1}{2} m\,\omega^2 x^2 + \lambda x^n \Bigr]\psi = E\psi\)$ | Extends the harmonic oscillator with a nonlinear potential term, typically analyzed via perturbation or numerical methods. |
| **19. Heat Equation** | $\(\frac{\partial u}{\partial t} = \alpha \nabla^2 u\)$ | Describes heat (or mass) diffusion with \(\alpha\) as the thermal diffusivity. <br>**Ref:** Evans, *Partial Differential Equations* |
| **20. Time-Dependent Schrödinger Equation** | $\(i \hbar \frac{\partial \Psi(\mathbf{r},t)}{\partial t} = \hat{H}\Psi(\mathbf{r},t)\)$ | Fundamental equation governing the time evolution of quantum systems. |
| **21. Dirac Equation** | $\(\bigl(i\gamma^\mu \partial_\mu - m \bigr)\psi = 0\)$ | A relativistic wave equation for spin-\(\tfrac{1}{2}\) particles; \(\gamma^\mu\) are the gamma matrices. <br>**Refs:** Peskin \& Schroeder; Bjorken \& Drell |
| **22. Shot Noise Limit** | $\(\Delta I = \sqrt{2q I\,\Delta f}\)$ | Describes the quantum (statistical) noise in an electrical current, where \(q\) is the elementary charge and \(\Delta f\) is the measurement bandwidth. |
| **23. Heisenberg Limit** | $\(\Delta \phi \sim \frac{1}{N}\)$ | In interferometry, the phase uncertainty scales as \(1/N\) for \(N\) particles, representing the ultimate sensitivity limit. <br>**Ref:** Quantum metrology literature (e.g., Caves, *Phys. Rev. D*, 1981) |
| **24. Standard Quantum Limit (SQL)** | $\(\Delta x_{\text{SQL}}(\omega) \sim \sqrt{\frac{\hbar}{2m\omega}}\)$ | Represents a measurement limit that balances measurement backaction and quantum noise. <br>**Ref:** Braginsky \& Khalili, *Quantum Measurement* |
| **25. LLG Equation** (Landau–Lifshitz–Gilbert) | $\(\frac{d\mathbf{M}}{dt} = -\gamma\,\mathbf{M}\times \mathbf{H}_\mathrm{eff} + \frac{\alpha}{M_s}\,\mathbf{M}\times \frac{d\mathbf{M}}{dt}\)$ | Describes the dynamics of magnetization \(\mathbf{M}\) in ferromagnets; \(\gamma\) is the gyromagnetic ratio and \(\alpha\) the damping constant. <br>**Refs:** Landau \& Lifshitz; Gilbert (1955) |
| **26. LLGS Equation** (Landau–Lifshitz–Gilbert–Slonczewski) | $\(\frac{d\mathbf{M}}{dt} = -\gamma\,\mathbf{M}\times \mathbf{H}_\mathrm{eff} + \frac{\alpha}{M_s}\,\mathbf{M}\times \frac{d\mathbf{M}}{dt} + \boldsymbol{\tau}_\mathrm{STT}\)$ | Extends the LLG model to include spin-transfer torque \(\boldsymbol{\tau}_\mathrm{STT}\) effects. <br>**Ref:** Slonczewski, *J. Magn. Magn. Mater.* (1996) |
| **27. Effective Field (for LLGS)** | $\(\mathbf{H}_\mathrm{eff} = -\frac{1}{\mu_0 M_s}\frac{\partial F}{\partial \mathbf{M}} + \mathbf{H}_\mathrm{applied} + \dots\)$ | The net effective magnetic field including contributions from anisotropy, exchange, demagnetization, and externally applied fields. <br>**Ref:** Stiles \& Miltat, *Topics in Applied Physics* (2006) |
| **28. Maxwell’s Equations** | <pre> 
∇·E = ρ/ε₀  
∇·B = 0  
∇×E = -∂B/∂t  
∇×B = μ₀J + μ₀ε₀ ∂E/∂t  
</pre> | The four differential equations governing classical electromagnetism. <br>**Ref:** Jackson, *Classical Electrodynamics* |
| **29. Fourier Transform** | $\(\hat{f}(k) = \int_{-\infty}^{\infty} f(x)e^{-2\pi i k x}\,dx\)$ | Decomposes a function \(f(x)\) into its constituent frequency components. (Note: Various normalization conventions exist.) <br>**Ref:** Arfken \& Weber, *Mathematical Methods* |
| **30. Green’s Function** | $\(L\,G(\mathbf{r}, \mathbf{r}') = \delta(\mathbf{r}-\mathbf{r}')\)$ | Represents the impulse response for a linear differential operator \(L\) and is widely used to solve partial differential equations. <br>**Ref:** Morse \& Feshbach, *Methods of Theoretical Physics* |
| **31. Geometric Algebra Identities** | - **Geometric Product:** $\(\mathbf{a}\,\mathbf{b} = \mathbf{a}\cdot\mathbf{b} + \mathbf{a}\wedge\mathbf{b}\)$ <br> - **Basis Vectors:** $\(e_i e_j + e_j e_i = 2\delta_{ij}\)$ | Fundamental identities in geometric (Clifford) algebra, which unifies various algebraic systems and is useful in advanced physics formulations. <br>**Refs:** Hestenes, *New Foundations for Classical Mechanics*; Doran \& Lasenby, *Geometric Algebra* |

---

## Table of Gain Equations

| **Type of Gain** | **Definition (Linear Scale)** | **Definition (dB Scale)** | **Notes / Context** |
|------------------|-------------------------------|---------------------------|---------------------|
| **Power Gain (RF/Microwave)** | $\(G_p = \frac{P_\mathrm{out}}{P_\mathrm{in}}\)$ | $\(G_{p,\mathrm{dB}} = 10\log_{10}\Bigl(\frac{P_\mathrm{out}}{P_\mathrm{in}}\Bigr)\)$ | Widely used in RF/microwave systems with matched impedances (e.g., 50 Ω). The factor 10 is used because power is proportional to voltage squared. |
| **Voltage Gain (Low-Frequency/General Amplifier)** | $\(G_v = \frac{V_\mathrm{out}}{V_\mathrm{in}}\)$ | $\(G_{v,\mathrm{dB}} = 20\log_{10}\Bigl(\frac{V_\mathrm{out}}{V_\mathrm{in}}\Bigr)\)$ | Common in audio and instrumentation where voltage is the primary measure. The factor 20 arises since power scales with the square of voltage. |
| **Current Gain** | $\(G_i = \frac{I_\mathrm{out}}{I_\mathrm{in}}\)$ | $\(G_{i,\mathrm{dB}} = 20\log_{10}\Bigl(\frac{I_\mathrm{out}}{I_\mathrm{in}}\Bigr)\)$ | Relevant for devices like transimpedance amplifiers where current amplification is key. |
| **Transimpedance Gain** | $\(Z_t = \frac{V_\mathrm{out}}{I_\mathrm{in}}\)$ | $\(Z_{t,\mathrm{dB}} = 20\log_{10}\Bigl(\frac{V_\mathrm{out}}{I_\mathrm{in}}\Bigr)\)$ | Often used for photodiode amplifiers and sensor front-ends converting current to voltage. |

---

## Additional Context on Gain

- **RF Power Gain:**  
  Typically expressed in decibels as  
  \[
    G_{p,\mathrm{dB}} = 10\log_{10}\left(\frac{P_\mathrm{out}}{P_\mathrm{in}}\right)
  \]  
  and is crucial in antenna design and link-budget analyses.

- **Voltage vs. Power Gain:**  
  In low-frequency electronics (e.g., audio systems), voltage gain is more directly relevant. Converting a voltage ratio to decibels uses a factor of 20 since \(P \propto V^2\).

- **Application Considerations:**  
  - Use **power gain** (10 log scale) for systems where power transfer is central and impedances are matched.  
  - Use **voltage gain** (20 log scale) when the emphasis is on voltage levels or when the load impedance is fixed and known.

Understanding these distinctions is critical for accurate design and characterization in electronic amplifier design, signal chain analysis, and communications system engineering.

---

## References

1. **Classical Electrodynamics** – J. D. Jackson  
2. **Introduction to Quantum Mechanics** – D. J. Griffiths  
3. **Modern Quantum Mechanics** – J. J. Sakurai  
4. **Principles of Lasers** – O. Svelto  
5. **Microwave Engineering** – D. Pozar  
6. **Solid State Physics** – N. W. Ashcroft and N. D. Mermin  
7. **Mechanics** – L. D. Landau and E. M. Lifshitz  
8. **Quantum Measurement** – V. B. Braginsky and F. Y. Khalili  
9. Hestenes, *New Foundations for Classical Mechanics*  
10. Caves, *Phys. Rev. D* **23**, 1693 (1981)  
11. Slonczewski, *J. Magn. Magn. Mater.* **159**, L1 (1996)  

---

*Note:* For proper LaTeX rendering on GitHub, consider using tools or workflows that enable MathJax or KaTeX processing on your pages.
