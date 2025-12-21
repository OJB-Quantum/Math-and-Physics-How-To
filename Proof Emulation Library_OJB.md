# Onri's Pattern Library - Proof Emulation Handbook

This takes the **Pattern Library** skeleton IDs (P0–P27) and converts them into **repeatable proof/derivation workflows**, per source.

## Pattern Library P0–P27

| ID | Mnemonic | Skeleton recipe |
| --- | --- | --- |
| P0 | DLT | Definitions → Lemma → Theorem → Proof (formal math). |
| P1 | MGSI | Model/assumptions → governing equations → boundary/initial conditions → solve → interpret/sanity-check. |
| P2 | SCALE | Non-dimensionalization → scaling laws → regime map → limiting cases. |
| P3 | SYM | Symmetry → conserved quantities/ selection rules → reduced dynamics. |
| P4 | VAR | Variational principle/ energy functional → extremize → Euler–Lagrange/ stationarity → stability. |
| P5 | EIG | Eigenproblem/ diagonalization → spectrum → mode expansion. |
| P6 | PERT | Perturbation/ approximation hierarchy (small parameter) → corrections → error bounds/checks. |
| P7 | LR | Linear response/ Green’s functions/ Kubo → susceptibilities, conductances, correlation functions. |
| P8 | NOISE | Stochastic processes → spectral density → noise-equivalent quantities → quantum limits. |
| P9 | IO | Input–output/ scattering theory → S-parameters, transfer functions, impedance matching. |
| P10 | CIRC | Circuit modeling → network synthesis → small-signal, impedance/admittance transformations. |
| P11 | DDP | Semiconductor Poisson + continuity + drift–diffusion → depletion/quasi-neutral approximations → I–V laws. |
| P12 | BAND | Band theory (Bloch/Kronig–Penney/effective mass) → density of states → transport coefficients. |
| P13 | SC | Superconductivity (BCS/Bogoliubov–de Gennes/Josephson) → gap, quasiparticles, circuits. |
| P14 | MAG | Micromagnetics (energy terms) + Landau–Lifshitz–Gilbert dynamics → domains, switching. |
| P15 | SPIN | Spin transport/torque (spin Hall, spin–orbit torque) → magnetization dynamics & device metrics. |
| P16 | FORMS | Manifolds + differential forms + Stokes/Gauss → coordinate-free calculus. |
| P17 | GA | Geometric/Clifford algebra → multivectors, rotors → coordinate-free physics. |
| P18 | GAUGE | Gauge theory/topology → connections, curvature, holonomy, Berry phase/topological invariants. |
| P19 | INFO | Entropy/relative entropy → convexity/monotonicity → information inequalities. |
| P20 | CRYPTO | Cryptographic security reductions → hybrid arguments → hardness assumptions. |
| P21 | EXP | Experimental pipeline → calibration → measurement → uncertainty budgeting → inference. |
| P22 | QFI | Fisher/quantum Fisher information → Cramér–Rao bounds → optimal measurements/estimators. |
| P23 | MEAS | Quantum measurement/open systems → density matrices, Kraus maps, master/Lindblad equations. |
| P24 | QFT | Quantum field theory → Lagrangians, path integrals, renormalization, effective field theory. |
| P25 | TM | Transfer matrix/ scattering matrix/ boundary matching in 1D & wave systems. |
| P26 | NUM | Numerical simulation + parameter estimation → finite elements/finite differences, fitting, sensitivity. |
| P27 | STAT | Statistical mechanics → ensembles/partition functions → thermodynamic potentials & fluctuations. |

---

---

---

## Monograph charter

### Scope and identity

This document is, at once, a *pattern library*, a *proof-derivation emulator*, and a *cross-domain technical monograph*.

- It is a **pattern library**, because it provides a stable set of reusable “proof skeletons” P0–P27 that can be recombined.
- It is a **proof-derivation emulator**, because it treats each worked derivation as a workflow: definitions → assumptions → derivation → sanity checks → numerical audit → repair moves.
- It is a **technical monograph**, because it insists on explicit conditions of validity, explicit conventions, and explicit provenance, so that each result is locally auditable and globally composable.

### Audience and prerequisites

High-school level orientation is provided in every pattern section, before the graduate-level formalization. The expected prerequisites vary by chapter:

- P0–P6 assume comfort with algebra, calculus, and linear algebra.
- P7–P10 assume basic differential equations and introductory circuit theory.
- P11–P15 assume semiconductor physics, superconductivity basics, and micromagnetics or spin-transport vocabulary.
- P16–P18 assume vector calculus, differential forms, and geometric or gauge viewpoints.
- P19–P27 assume probability, information theory, numerical methods, and quantum formalism.

### Rigor target

This edition targets **rigor level 5 of 5** as defined in the accompanying assessment rubric:

- every pattern includes a formal statement,
- every pattern makes conditions and conventions explicit,
- and every pattern includes either a quantitative error certificate, or a reproducible computational check, and often both.

---

## Rigor standard

### Intuitive explanation/ framing

In math and physics, rigor mainly means that, because assumptions are stated and steps are shown, a second reader can reproduce the result and can also tell when it stops being valid.

In this monograph, that becomes a disciplined habit:

1. State assumptions and conventions up front.
2. Derive step-by-step, with no hidden algebra.
3. Perform unit checks, limiting cases, and sanity checks.
4. Provide a numerical example with realistic magnitudes.
5. If assumptions fail, describe how to repair them, and how the repaired model changes the identity and name of the object.

### Graduate-level framing

Rigor here is multi-dimensional, because the handbook simultaneously supports:

- formal proof patterns, such as inequalities and convexity arguments,
- physics modeling patterns, such as model → governing equation → boundary and initial conditions,
- asymptotics and approximation patterns, such as scaling and perturbation,
- inference patterns, such as uncertainty propagation and Fisher information,
- and discipline-specific derivation pipelines, such as semiconductors, superconductivity, micromagnetics, and scattering.

Accordingly, “5 of 5” rigor in this genre is not proof-assistant formalization; rather, it is **auditable derivation practice**: explicit domains of validity, explicit conventions, and reproducible computation.

### Rigor scoring rubric 0–5

- **5:** theorem-proof complete and conditions fully stated and error certification or reproducible computation included
- **4:** auditable derivation with explicit assumptions, conventions, sanity checks, and numerics
- **3:** mostly correct and structured, but with proof sketches, implicit steps, or missing quantitative error control
- **2:** heuristic derivation with limited domain control
- **1–0:** informal notes or unsupported claims

### The 5 of 5 gate checklist

A pattern chapter is considered “reference-grade” when it satisfies all items below.

- **Formal statement exists.** The result is stated as a theorem, proposition, lemma, or definition, with explicit quantifiers.
- **Domain is explicit.** Space, field, function class, boundary and initial conditions, and regularity are stated.
- **Conventions are explicit.** Sign, Fourier transform convention, one-sided vs two-sided spectra, inner product linearity, and unit system are stated where relevant.
- **Proof is auditable.** The proof or derivation proceeds in steps, with named lemmas or identities where needed.
- **Error certificate exists.** If an approximation is used, the truncation order and a quantitative error bound or threshold are stated.
- **Reproducibility exists.** A numerical example is reproducible, preferably via a small script.
- **Repair move exists.** If assumptions fail, the repaired model and its new name are given.

---

## Provenance and citation locality rule

A monograph is, before it is anything else, a provenance artifact. Therefore:

- Each pattern includes a short **Primary sources** list with 1–3 load-bearing references.
- Each nontrivial convention, such as a power spectral density convention or a sign convention, is either derived, or it is explicitly pinned to a source.
- References are also collected globally, but “global references only” is treated as insufficient for 5 of 5 rigor.

---

## Standard error certificate clause

When an approximation or linearization appears, the pattern chapter includes, at minimum:

- the **truncation order** or neglected-term class, such as $O(\varepsilon^3)$,
- a **parameter range** that keeps error below a threshold,
- and an estimate of the **dominant neglected term**, so that one can decide whether the approximation remains the same object.

If a pattern is exact in the chosen model class, the error certificate becomes an **engineering tolerance** clause: component tolerances, parameter uncertainty, and measurement bandwidth are propagated into the output.

---

## Reproducibility protocol

To keep computation both portable and auditable:

- Numerical checks are given as short Python code blocks with explicit “control knobs” at the top.
- Each code block prints intermediate values, not only final values, to reduce transcription errors.
- When relevant, checks include assertions that validate inequalities or invariants numerically.

---

## Annotation protocol for proof emulation cards

### Why an annotation protocol matters

The first half of this document, the proof emulation cards, is methodologically structured but inherently more subjective than the derivation half. A reference-grade monograph therefore treats those cards as a small content-analysis ontology.

### Coding rubric for assigning skeleton IDs

A source earns a skeleton ID when its *dominant explanatory move* matches the criteria below.

- **DLT:** the exposition is organized around definitions and lemmas, and culminates in a theorem-proof style derivation.
- **MGSI:** the exposition begins from a model with assumptions, writes governing equations, imposes boundary or initial conditions, solves, and interprets with sanity checks.
- **SCALE:** the exposition introduces nondimensional variables, extracts dimensionless groups, and partitions behavior by regime inequalities.
- **SYM:** the exposition identifies a symmetry, defines the corresponding generator, and derives a conservation law, selection rule, or reduced dynamics.
- **VAR:** the exposition starts from an action or energy functional, extremizes it, and derives Euler–Lagrange or stationarity conditions, often with stability commentary.
- **EIG:** the exposition reduces a problem to an eigenproblem, diagonalization, or spectral decomposition, and then uses mode expansion or orthogonality.
- **PERT:** the exposition introduces a small parameter, builds an approximation hierarchy, and tracks remainder terms or validity bounds.
- **LR:** the exposition defines a Green function or response function, and derives frequency-domain susceptibilities, conductances, or correlation functions.
- **NOISE:** the exposition treats fluctuations as stochastic processes, defines spectral densities, and carries conventions and bandwidth explicitly.
- **IO:** the exposition treats systems as ports and modes, writes scattering or input-output relations, and computes reflection or transmission quantities.
- **CIRC:** the exposition reduces physics into circuits, network parameters, or equivalent ports, and then solves as a network problem.
- **DDP:** the exposition is organized around drift-diffusion and Poisson closure, and then produces device-level constitutive laws.
- **BAND:** the exposition derives density of states or band statistics, and then maps them into carrier densities or observables.
- **SC:** the exposition uses superconducting phase, flux quantization, or Josephson relations to derive circuit-level conversion laws.
- **MAG:** the exposition uses Landau–Lifshitz–Gilbert dynamics, effective fields, and linearization to produce precession and resonance relations.
- **SPIN:** the exposition treats charge-spin conversion, spin accumulation, diffusion, and interface transparency.
- **FORMS:** the exposition uses differential forms and integral theorems as the main organizing proof move.
- **GA:** the exposition uses geometric algebra, multivectors, and rotor actions as primary objects.
- **GAUGE:** the exposition treats gauge fields, connections, curvature, holonomy, and topological invariants.
- **INFO:** the exposition relies on entropy, convexity, monotonicity, and information inequalities.
- **CRYPTO:** the exposition uses security games, hybrids, and reductions to relate a construction’s security to assumptions.
- **EXP:** the exposition treats experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- **QFI:** the exposition uses Fisher information, Cramér–Rao bounds, and optimal measurements or estimators.
- **MEAS:** the exposition uses density matrices, Kraus maps, completely positive trace-preserving maps, and open-system dynamics.
- **QFT:** the exposition uses Lagrangians, Euler–Lagrange fields, and effective descriptions, often with renormalization.
- **TM:** the exposition uses transfer matrices or scattering matrices to compose boundary-matching solutions in layered media.
- **NUM:** the exposition uses discretization, stability analysis, convergence checks, and parameter inference from numerics.
- **STAT:** the exposition uses maximum entropy, ensembles, partition functions, and thermodynamic potentials.

### Decision rules

- If two skeletons are present, assign the one that appears in the *main derivation spine*, and list the other as secondary.
- If the source is a survey or review, prefer the skeleton that is repeatedly used across its examples rather than in its introduction.
- If a source is a “methods” paper, assign based on the proof move that produces the paper’s central result, not on background sections.

### Inter-rater reliability mini-study design

To validate that the coding rubric is falsifiable rather than merely personal:

1. Select a stratified sample of 20–30 sources across domains.
2. Have two annotators independently assign skeleton IDs and expository structure labels.
3. Compute an agreement statistic, such as **Cohen’s kappa** for nominal categories or **Krippendorff’s alpha** for more general settings.
4. Review disagreements, update decision rules, and repeat until agreement stabilizes.

For a practical threshold, a kappa or alpha above roughly 0.7 is often treated as “substantial agreement” in applied methodology, although the correct threshold depends on intended use.

---

## Cross-pattern consistency map

The patterns are designed to be composable. The compositional interfaces are:

- invariants and conserved quantities, such as energies and momenta,
- response functions and spectra, such as susceptibilities and power spectral densities,
- and transfer operators, such as scattering matrices, transfer matrices, or completely positive maps.

A compact mind map that makes those interfaces visible:

```
Proof emulation and rigor graph
├─ Proof structure patterns
│  ├─ P0 DLT inequalities, convexity, definitions
│  ├─ P4 VAR and P3 SYM action, stationarity, Noether currents
│  └─ P5 EIG and P6 PERT spectra and approximation hierarchies
├─ Linear systems backbone
│  ├─ P1 MGSI ODE response and time constants
│  ├─ P7 LR susceptibilities χ(ω) and Green functions
│  ├─ P8 NOISE spectral density conventions, bandwidth, and limits
│  ├─ P9 IO ports, mismatch, and reflection constraints
│  └─ P25 TM composition laws for layered scattering
├─ Device physics pipelines
│  ├─ P11 DDP transport equations → reduced device laws
│  ├─ P12 BAND statistics and degeneracy thresholds
│  ├─ P13 SC phase dynamics → frequency–voltage conversion
│  ├─ P14 MAG LLG → resonance relations
│  └─ P15 SPIN conversion + diffusion + interfaces
└─ Inference and computation
   ├─ P21 EXP uncertainty budgets and covariance propagation
   ├─ P22 QFI Fisher bounds, quantum limits, optimal readout
   ├─ P23 MEAS CPTP maps, Kraus operators, Lindblad limits
   ├─ P26 NUM stability, consistency, convergence
   └─ P27 STAT maximum entropy and ensemble logic, plus maximum caliber extensions
```

---

## Upgrades that can be implemented as needed

Pattern-by-pattern: 
- explicit hypotheses and theorem statements where the prior text was proof-sketch-like,
- a standard error certificate clause generalized from the P6 style,
- per-pattern primary sources for citation locality,
- copyable formulas and redundant plain-text expressions for auditability,
- and executable numerical checks embedded as short scripts.

## Classification Tree by Primary Use

```text
Pattern Library Corpus (Onri) — Classification Tree by Primary Use
└─ Root
   ├─ Mathematics, Geometry, and Algebra (coordinate-free) (11 sources)
   │  ├─ A Covariant Approach to Geometry using Geometric Algebra_Lasenby_Lasenby_Wareham
   │  ├─ Calculus on Manifolds_Spivak
   │  ├─ Introduction to Differential Geometry_Robbin_Salamon
   │  ├─ Abel’s Theorem in Problems and Solutions_Arnold_Alekseev
   │  ├─ Clifford Algebra, Geometric Algebra, and Applications_Lundholm_Svensson
   │  ├─ Clifford Algebras and Spinors_Freedman_Van Proeyen
   │  ├─ Geometric Algebra as a Unifying Language for Physics and Engineering_Lasenby 
   │  ├─ Geometric Algebra for Physicists_Lasenby
   │  ├─ Geometric Algebra for Electrical and Electronic Engineers_Chappell et al.
   │  ├─ Application of Geometric Algebra to Electromagnetic Scattering_Seagar
   │  ├─ Applications of Conformal Geometric Algebra to Transmission Line Theory_Arsenovic
   │
   ├─ Semiconductors and Solid-State Electronic Devices (7 sources)
   │  ├─ Solid-State Devices_Streetman
   │  ├─ Semiconductor Physics and Devices_Neaman
   │  ├─ Semiconductor and Device Physics_Goldsman_Darmody
   │  ├─ Semiconductor Devices_Fiore
   │  ├─ Solid-State Physics_Epifanov
   │  ├─ Electric Circuits, Volume III -- Semiconductors_Kuphaldt
   │  ├─ Quantum Nanostructures_Kumar_Kumar_Mahesh
   │
   ├─ Magnetism and Spintronics (9 sources)
   │  ├─ Introduction to Magnetic Materials_Cullity
   │  ├─ Modern Magnetic Materials_Principles and Applications_O'Handley
   │  ├─ Handbook of Magnetism and Magnetic Materials_Parkin
   │  ├─ Experimental Techniques in Magnetism and Magnetic Materials_Roy
   │  ├─ Magnetic and Spin Devices_Sverdlov_Jutong
   │  ├─ Brandon Zink PhD Thesis
   │  ├─ Tom Peterson PhD Thesis
   │  ├─ Yifei Yang PhD Thesis
   │  ├─ Abhinav Kandala PhD Thesis
   │
   ├─ Superconductivity, Cryogenics, and Superconducting Devices (9 sources)
   │  ├─ Introduction to Superconductivity_Tinkham
   │  ├─ Superconductor Electronics_Hinken
   │  ├─ Cryogenic Engineering_Timmerhaus_Reed
   │  ├─ Heleen Dausy PhD Thesis
   │  ├─ Janka Biznárová PhD Thesis 
   │  ├─ Omid Noroozian PhD Thesis
   │  ├─ Luca Planat PhD Thesis
   │  ├─ Christopher Axline PhD Thesis
   │  ├─ Jiansong Gao PhD Thesis
   │
   ├─ Quantum Mechanics Core (textbooks + problem technique) (8 sources)
   │  ├─ Quantum Mechanics (vol. I, II and III, 2nd ed.)_Cohen-Tannoudji_Diu_Laloë
   │  ├─ Quantum Mechanics Concepts and Applications_Zettili
   │  ├─ Quantum Mechanics for Scientists and Engineers_Miller
   │  ├─ Quantum Mechanics Made Simple_Lecture Notes_Chew
   │  ├─ Quantum Mechanics_An Introduction for Device Physicists and Electrical Engineers_Ferry
   │  ├─ Quantum Mechanics_Shoshany
   │  ├─ Problem Solving in Quantum Mechanics_From Basics to Real-World Applications_Cahay_Bandyopadhyay
   │  ├─ Quantum Mechanical Phase and Time Operator_Susskind_Glogower
   │
   ├─ Circuit Quantum Electrodynamics, Microwave Engineering, and Circuits (6 sources)
   │  ├─ Circuit QED_Superconducting Qubits Coupled to Microwave Photons_Girvin
   │  ├─ David Isaac Schuster PhD Thesis
   │  ├─ Quantum Electrical Circuits_Lecture Notes_Ciani_DiVincenzo
   │  ├─ Planar Microwave Engineering_Lee
   │  ├─ Electric Circuits, Volume I -- DC_Kuphaldt
   │  ├─ Electric Circuits, Volume II -- AC_Kuphaldt
   │
   ├─ Quantum Measurement, Noise, Optomechanics, and Metrology (19 sources)
   │  ├─ Measurements in Quantum Mechanics_Pahlavani
   │  ├─ Quantum Measurement_Braginsky_Khalili
   │  ├─ Quantum Measurement_Theory and Practice_Jordan_Siddiqi
   │  ├─ Quantum Measurement Theory and its Applications_Jacobs
   │  ├─ Introduction to Quantum Noise, Measurement, and Amplification_Clerk_Devoret_Girvin_Marquardt_Schoelkopf
   │  ├─ Quantum Mechanical Noise in an Interferometer_Caves
   │  ├─ Quantum Optomechanics_Bowen_Milburn
   │  ├─ Quantum Noise in Mesoscopic Physics_Nazarov
   │  ├─ Shiyuan Zhao PhD Thesis
   │  ├─ Vivishek Sudhir PhD Thesis 
   │  ├─ Ronald Pagano PhD Thesis
   │  ├─ Roman Schmeissner PhD Thesis
   │  ├─ Applications and Metrology at Nanometer Scale 2_Dahoo_Pougnet_El Hami
   │  ├─ Quantum Interferometry in Phase Space_Suda
   │  ├─ Generalized Measure of Quantum Fisher Information_Sone_Cerezo_Beckey_Coles
   │  ├─ Quantum Fisher Information and its Dynamical Nature_Scandi_Abiuso_Surace_De Santis
   │  ├─ Introduction to Quantum Fisher Information_Petz_Ghinea
   │  ├─ Sub-Quantum Fisher Information_Cerezo_Sone_Beckey_Coles
   │  ├─ Quantum Optics in Phase Space_Schleich
   │
   ├─ Quantum Information, Computation, and Cryptography (9 sources)
   │  ├─ A Mini Introduction to Information Theory_Witten
   │  ├─ A Group Theoretic Approach to Quantum Information_Hayashi
   │  ├─ Quantum Information Theory_Wilde
   │  ├─ Quantum Shannon Theory_Wilde
   │  ├─ Quantum Information Processing_Bergou_Hillery_Saffman
   │  ├─ Quantum Information Science_Manenti_Motta
   │  ├─ Theory of Quantum Computation, Communication, and Cryptography_van Dam_Kendon_Severini
   │  ├─ Post-Quantum Cryptography_Ding_Tillich
   │  ├─ Quantum Computing Architecture and Hardware for Engineers_Wong
   │
   ├─ Quantum Field Theory, Gauge Theory, and Strings (7 sources)
   │  ├─ More On Gauge Theory And Geometric Langlands_Witten
   │  ├─ Algebraic Structures and Differential Geometry in 2D String Theory_Witten_Zwiebach
   │  ├─ Quantum Fields and Strings_Diligne et al.
   │  ├─ The Black Book of Quantum Chromodynamics_Campbell_Huston_Krauss
   │  ├─ Weak Interactions_Georgi
   │  ├─ Quantum Theory from First Principles_D’Ariano_Chiribella_Perinotti
   │  ├─ Quantum Transport_Nazarov_Blanter
   │
   ├─ Foundations (classical physics) (1 sources)
   │  ├─ Fundamentals of Physics_Shankar
```

## Proof Emulation Cards 

### Mathematics, Geometry, and Algebra coordinate-free

#### A Covariant Approach to Geometry using Geometric Algebra

- **Primary use**: Coordinate-free geometry and relativistic covariance via geometric algebra; bridge between tensors and multivectors.
- **Dominant frameworks**: Geometric/Clifford algebra; differential geometry; Lorentz covariance.
- **Repeated proof skeletons (IDs)**: P17 GA, P16 FORMS, P3 SYM, P0 DLT
- **Expository structure**: S-REV/LN (theory-focused notes)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- Define the manifold, forms, and orientation, then compute with exterior derivative and wedge product instead of coordinates.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Calculus on Manifolds

- **Primary use**: Concise, theorem-proof calculus with differential forms; core toolkit for modern physics geometry.
- **Dominant frameworks**: Manifolds; differential forms; exterior calculus; integration on manifolds.
- **Repeated proof skeletons (IDs)**: P16 FORMS, P0 DLT
- **Expository structure**: S-TXT (math textbook, theorem-proof)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define the manifold, forms, and orientation, then compute with exterior derivative and wedge product instead of coordinates.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Introduction to Differential Geometry

- **Primary use**: Introduction to differential geometry (manifolds, tensors/forms, connections) as used in physics.
- **Dominant frameworks**: Manifolds; vector bundles; connections; curvature.
- **Repeated proof skeletons (IDs)**: P16 FORMS, P18 GAUGE, P0 DLT
- **Expository structure**: S-TXT/LN (intro notes)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define the manifold, forms, and orientation, then compute with exterior derivative and wedge product instead of coordinates.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Abel’s Theorem in Problems and Solutions

- **Primary use**: Problem-driven development of Abel’s theorem and related algebraic-geometry techniques.
- **Dominant frameworks**: Complex analysis; Riemann surfaces; divisors; algebraic curves.
- **Repeated proof skeletons (IDs)**: P0 DLT, P16 FORMS
- **Expository structure**: S-PROB (problems + solutions)

What to emulate in your future proofs:
- Use problem-solution cadence: restate givens, choose a method, execute cleanly, then generalize the trick for reuse.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Define the manifold, forms, and orientation, then compute with exterior derivative and wedge product instead of coordinates.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Clifford Algebra, Geometric Algebra, and Applications

- **Primary use**: Survey of Clifford/geometric algebra with applications; algebraic unification of geometry and physics.
- **Dominant frameworks**: Clifford algebras; multivectors; rotors; algebraic geometry of space.
- **Repeated proof skeletons (IDs)**: P17 GA, P0 DLT, P3 SYM
- **Expository structure**: S-REV/TXT (theory survey)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Clifford Algebras and Spinors

- **Primary use**: Spinors and Clifford algebras; representation-theoretic backbone for rotations, Lorentz group, and fermions.
- **Dominant frameworks**: Lie groups; spin representations; Clifford algebra; geometry of spinors.
- **Repeated proof skeletons (IDs)**: P17 GA, P18 GAUGE, P0 DLT, P3 SYM
- **Expository structure**: S-TXT/REV (math-physics monograph)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Geometric Algebra as a Unifying Language for Physics and Engineering

- **Primary use**: Position geometric algebra as unifying language across physics/engineering; conceptual and computational patterns.
- **Dominant frameworks**: Geometric algebra; coordinate-free mechanics/electromagnetism.
- **Repeated proof skeletons (IDs)**: P17 GA, P3 SYM, P1 MGSI
- **Expository structure**: S-REV/LN (conceptual survey)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Declare the model assumptions up front, then write the governing equations, and only then choose solution tactics.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Geometric Algebra for Physicists

- **Primary use**: Comprehensive geometric algebra toolkit for physics (rotations, relativity, electromagnetism, spinors).
- **Dominant frameworks**: Geometric algebra; spacetime algebra; gauge formulations.
- **Repeated proof skeletons (IDs)**: P17 GA, P18 GAUGE, P3 SYM, P16 FORMS
- **Expository structure**: S-TXT (monograph)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Geometric Algebra for Electrical and Electronic Engineers

- **Primary use**: Engineering-oriented geometric algebra for circuits/fields and computational workflows.
- **Dominant frameworks**: Geometric algebra; electromagnetics; circuits.
- **Repeated proof skeletons (IDs)**: P17 GA, P10 CIRC, P9 IO, P1 MGSI
- **Expository structure**: S-TXT/REV (engineering monograph)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.

#### Application of Geometric Algebra to Electromagnetic Scattering

- **Primary use**: Reformulate electromagnetic scattering using geometric algebra; compact boundary matching and invariants.
- **Dominant frameworks**: Maxwell equations; scattering theory; geometric algebra.
- **Repeated proof skeletons (IDs)**: P17 GA, P1 MGSI, P25 TM, P3 SYM
- **Expository structure**: S-REV (applied theory paper/notes)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- Declare the model assumptions up front, then write the governing equations, and only then choose solution tactics.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Applications of Conformal Geometric Algebra to Transmission Line Theory

- **Primary use**: Transmission-line theory expressed with conformal geometric algebra; unifies geometry and network transforms.
- **Dominant frameworks**: Transmission lines; conformal geometric algebra; network theory.
- **Repeated proof skeletons (IDs)**: P17 GA, P10 CIRC, P9 IO, P25 TM
- **Expository structure**: S-REV (applied theory paper/notes)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the geometric product, multivectors, and rotors, then rewrite vector calculus identities in coordinate-free form.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.


### Semiconductors and Solid-State Electronic Devices

#### Solid State Devices

- **Primary use**: Canonical solid-state electronic devices text; from crystal/bands to diodes/transistors and integrated circuits.
- **Dominant frameworks**: Solid-state device physics; carrier statistics; junctions; MOSFET/BJT.
- **Repeated proof skeletons (IDs)**: P12 BAND, P11 DDP, P27 STAT, P10 CIRC, P1 MGSI
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Declare regime assumptions up front (low injection, quasi-neutral regions, depletion approximation).
- Write governing equations (continuity + drift–diffusion + Poisson).
- Solve in regions, then match boundary conditions.
- Take limits explicitly (small/large parameter), and replace special functions with asymptotics.
- Interpret physically (what term is drift vs diffusion, what term is recombination).
- Close by expressing the result as an I–V, C–V, or small-signal parameter, and by checking low/high-bias limits and units.

#### Semiconductor Physics and Devices

- **Primary use**: Semiconductor physics/devices with strong fundamentals and structured chapter previews/summaries/problems.
- **Dominant frameworks**: Crystal structure; quantum bands; carrier transport; device equations.
- **Repeated proof skeletons (IDs)**: P12 BAND, P27 STAT, P11 DDP, P1 MGSI, P2 SCALE
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Organize explanations into “Part I: foundations,” “Part II: device archetypes,” “Part III: applications.”
- Keep an explicit symbol discipline (include a symbol/unit discipline, and keep symbols consistent across sections).
- Treat each model as an abstraction layer: physical partial differential equation model → reduced analytical model → equivalent circuit.
- Use chapter previews/summaries and end-of-section checks to keep the reader oriented.
- When switching approximations (Boltzmann vs Fermi–Dirac, low-field vs high-field), state the criterion explicitly.
- Close by expressing the result as an I–V, C–V, or small-signal parameter, and by checking low/high-bias limits and units.

#### Semiconductor and Device Physics

- **Primary use**: Concise semiconductor/device physics with explicit quantum-mechanics bridge for engineers.
- **Dominant frameworks**: Crystallography; quantum basics; carrier statistics; device models.
- **Repeated proof skeletons (IDs)**: P11 DDP, P12 BAND, P27 STAT, P1 MGSI, P6 PERT
- **Expository structure**: S-TXT (concise textbook)

What to emulate in your future proofs:
- Write the governing equation first (Schrödinger), then define potentials/regions.
- Solve general forms per region.
- Apply boundary conditions as the core “proof move.”
- Extract a measurable (transmission, current, capacitance) by mapping constants back to physical quantities.
- Keep the derivation concise: prefer a small number of reusable templates (well/barrier/step), then recombine them.
- Close by expressing the result as an I–V, C–V, or small-signal parameter, and by checking low/high-bias limits and units.

#### Semiconductor Devices

- **Primary use**: OER (open educational resource) semiconductor devices with circuit-oriented analysis and minimal calculus.
- **Dominant frameworks**: Device models; diode/BJT/FET circuits; small-signal.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P11 DDP, P1 MGSI, P6 PERT, P2 SCALE
- **Expository structure**: S-TXT (OER textbook)

What to emulate in your future proofs:
- For any device-theory explanation, add a second layer: “How would I design around this with tolerances and datasheet variance?”
- Translate physics parameters into circuit knobs (bias points, load lines, small-signal parameters).
- Keep calculus optional: when a derivative appears, also restate the conclusion in algebraic or graphical terms.
- Close proofs with a verification step: “Simulate it, then sanity-check it against expected ranges.”
- Use real device curves, and explicitly flag where ideal models diverge from datasheet behavior.
- Close by expressing the result as an I–V, C–V, or small-signal parameter, and by checking low/high-bias limits and units.

#### Solid-State Physics

- **Primary use**: Qualitative-plus-quantitative solid-state physics survey (bonding, defects, statistics, transport, etc.).
- **Dominant frameworks**: Solid-state physics; statistical physics; materials properties.
- **Repeated proof skeletons (IDs)**: P12 BAND, P27 STAT, P1 MGSI, P2 SCALE
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Start with a physical story and an order-of-magnitude relation.
- Only then decide whether the full partial differential equation derivation is necessary, or whether a reduced model suffices.
- Prefer qualitative relations and sign/scale arguments when they convey the physics with less algebra.
- When mathematics is required, keep it modular: one derivation per phenomenon, with clear physical meaning of each term.
- End with engineering relevance: what knob (material, temperature, geometry) actually changes the effect.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Electric Circuits, Volume III -- Semiconductors

- **Primary use**: Circuits with semiconductor devices: diode/transistor models, biasing, small-signal, amplifiers.
- **Dominant frameworks**: Device models; nonlinear circuits; small-signal linearization.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P11 DDP, P6 PERT, P1 MGSI
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Declare semiconductor regime assumptions (depletion approximation, low injection, quasi-neutral regions) explicitly.
- Choose a perturbation parameter, build a hierarchy of approximations, and track error terms throughout.
- Close by expressing the result as an I–V, C–V, or small-signal parameter, and by checking low/high-bias limits and units.

#### Quantum Nanostructures

- **Primary use**: Quantum confinement, low-dimensional structures, and device-relevant quantum transport/band concepts.
- **Dominant frameworks**: Nanostructure band models; effective mass; tunneling; scattering.
- **Repeated proof skeletons (IDs)**: P12 BAND, P5 EIG, P25 TM, P6 PERT, P7 LR
- **Expository structure**: S-TXT/REV (specialized text)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Begin with band-structure assumptions (Bloch/effective mass), then derive density of states and carrier statistics.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.


### Magnetism and Spintronics

#### Introduction to Magnetic Materials

- **Primary use**: Foundational magnetism text emphasizing definitions, units, experimental methods, and classical/quantum magnetism.
- **Dominant frameworks**: Magnetostatics; susceptibility; domains; measurement instrumentation.
- **Repeated proof skeletons (IDs)**: P14 MAG, P21 EXP, P1 MGSI, P2 SCALE, P27 STAT
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Define observables and units first (especially magnetization M, field H, flux density B, susceptibility χ, permeability μ).
- Tie theory to a measurement method (what instrument, what curve, what extracted parameter).
- Translate extracted parameters into material selection/processing implications.
- Keep careful sign conventions and demagnetizing-field geometry, because they are where real experiments fail.
- Close with a “how you would actually measure it” recipe and a plausibility range.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Modern Magnetic Materials_Principles and Applications

- **Primary use**: Physics-to-application bridge for magnetic materials; emphasizes Maxwell relations, energy, and device contexts.
- **Dominant frameworks**: Magnetostatics; thermodynamics; domains; applications; includes Gauss/Stokes appendices.
- **Repeated proof skeletons (IDs)**: P14 MAG, P1 MGSI, P4 VAR, P16 FORMS, P2 SCALE
- **Expository structure**: S-TXT (monograph)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Write the micromagnetic energy functional (exchange, anisotropy, Zeeman, demagnetization), then derive effective fields.
- Declare the model assumptions up front, then write the governing equations, and only then choose solution tactics.
- Start from an energy, action, or cost functional, then extremize it to derive Euler–Lagrange or stationarity conditions.
- Close by translating the math into device metrics (coercivity, switching current, damping, torque efficiency), and by identifying which material/geometry knob shifts the metric most.

#### Handbook of Magnetism and Magnetic Materials

- **Primary use**: Broad, authoritative reference across magnetism fundamentals, materials classes, methods, and applications.
- **Dominant frameworks**: Micromagnetics; exchange; anisotropy; magnetotransport; thin films; devices.
- **Repeated proof skeletons (IDs)**: P14 MAG, P15 SPIN, P7 LR, P21 EXP, P27 STAT
- **Expository structure**: S-HB (handbook chapters)

What to emulate in your future proofs:
- Write the micromagnetic energy functional (exchange, anisotropy, Zeeman, demagnetization), then derive effective fields.
- Add spin-current and spin–orbit torque terms with symmetry constraints, then derive switching thresholds and efficiencies.
- Define the response function (susceptibility, conductance) and derive it via Green’s functions or Kubo-like formulas.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Experimental Techniques in Magnetism and Magnetic Materials

- **Primary use**: Instrumentation and experimental methods in magnetism, from macroscopic to microscopic probes.
- **Dominant frameworks**: Magnetometry; resonance; scattering; imaging; units and demagnetization.
- **Repeated proof skeletons (IDs)**: P21 EXP, P14 MAG, P1 MGSI, P2 SCALE
- **Expository structure**: S-TXT (methods textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Write the micromagnetic energy functional (exchange, anisotropy, Zeeman, demagnetization), then derive effective fields.
- Declare the model assumptions up front, then write the governing equations, and only then choose solution tactics.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Magnetic and Spin Devices

- **Primary use**: Special-issue collection on magnetic/spin devices; device reliability and spintronic designs.
- **Dominant frameworks**: Spintronics devices; materials reliability; applied magnetism.
- **Repeated proof skeletons (IDs)**: P15 SPIN, P14 MAG, P21 EXP
- **Expository structure**: S-REV (edited collection)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Add spin-current and spin–orbit torque terms with symmetry constraints, then derive switching thresholds and efficiencies.
- Write the micromagnetic energy functional (exchange, anisotropy, Zeeman, demagnetization), then derive effective fields.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Brandon Zink PhD Thesis

- **Primary use**: Magnetic tunnel junctions for conventional/unconventional computing; stochastic switching and multi-physics control.
- **Dominant frameworks**: Spintronics; magnetization dynamics; stochastic processes; device physics.
- **Repeated proof skeletons (IDs)**: P21 EXP, P14 MAG, P15 SPIN, P8 NOISE, P26 NUM
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Write the micromagnetic energy functional (exchange, anisotropy, Zeeman, demagnetization), then derive effective fields.
- Add spin-current and spin–orbit torque terms with symmetry constraints, then derive switching thresholds and efficiencies.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Tom Peterson PhD Thesis

- **Primary use**: Materials research for spin–orbit torque plus voltage-controlled magnetic anisotropy MRAM; growth, characterization, switching.
- **Dominant frameworks**: Spin–orbit torque; anisotropy; thin films; transport measurements.
- **Repeated proof skeletons (IDs)**: P21 EXP, P15 SPIN, P14 MAG, P26 NUM, P7 LR
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Add spin-current and spin–orbit torque terms with symmetry constraints, then derive switching thresholds and efficiencies.
- Write the micromagnetic energy functional (exchange, anisotropy, Zeeman, demagnetization), then derive effective fields.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Yifei Yang PhD Thesis

- **Primary use**: Unconventional spin–orbit torque in low-symmetry materials; experiments plus theory comparisons.
- **Dominant frameworks**: Spintronics; symmetry analysis; materials characterization; transport.
- **Repeated proof skeletons (IDs)**: P21 EXP, P15 SPIN, P14 MAG, P3 SYM, P26 NUM
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Add spin-current and spin–orbit torque terms with symmetry constraints, then derive switching thresholds and efficiencies.
- Write the micromagnetic energy functional (exchange, anisotropy, Zeeman, demagnetization), then derive effective fields.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Abhinav Kandala PhD Thesis

- **Primary use**: Low-temperature magnetotransport in (magnetic) topological-insulator devices; weak anti-localization and interference signatures.
- **Dominant frameworks**: Quantum transport; mesoscopic interference; topological surface states; magnetism interfaces.
- **Repeated proof skeletons (IDs)**: P21 EXP, P7 LR, P18 GAUGE, P26 NUM, P8 NOISE
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Define the response function (susceptibility, conductance) and derive it via Green’s functions or Kubo-like formulas.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.


### Superconductivity, Cryogenics, and Superconducting Devices

#### Introduction to Superconductivity

- **Primary use**: Canonical superconductivity theory and phenomenology (Ginzburg–Landau, BCS, vortices, electrodynamics).
- **Dominant frameworks**: Many-body quantum theory; BCS mean-field and Bogoliubov quasiparticles; superconducting electrodynamics; Ginzburg–Landau theory.
- **Repeated proof skeletons (IDs)**: P13 SC, P5 EIG, P4 VAR, P27 STAT, P6 PERT, P1 MGSI
- **Expository structure**: S-TXT (theory textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- When a microscopic chapter becomes second-quantization-heavy, provide (and use) a “skim path” to the load-bearing sections, and then backfill details only when later chapters demand them.
- State the superconducting model (BCS/Bogoliubov–de Gennes/Josephson), identify the gap and quasiparticles, then derive circuit consequences.
- Start from an energy, action, or cost functional, then extremize it to derive Euler–Lagrange or stationarity conditions.
- Choose the correct ensemble, compute partition functions, and derive averages and fluctuations by differentiation identities.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Superconductor Electronics

- **Primary use**: Engineering and physics of superconducting electronic devices and circuits (Josephson, SQUID, etc.).
- **Dominant frameworks**: Superconductivity; Josephson junction circuits; microwave readout.
- **Repeated proof skeletons (IDs)**: P13 SC, P10 CIRC, P9 IO, P21 EXP, P8 NOISE
- **Expository structure**: S-TXT (engineering text)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- When a microscopic chapter becomes second-quantization-heavy, provide (and use) a “skim path” to the load-bearing sections, and then backfill details only when later chapters demand them.
- State the superconducting model (BCS/Bogoliubov–de Gennes/Josephson), identify the gap and quasiparticles, then derive circuit consequences.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Cryogenic Engineering

- **Primary use**: Engineering treatment of cryogenic systems: heat loads, refrigeration cycles, materials, and measurements.
- **Dominant frameworks**: Thermodynamics; heat transfer; fluid dynamics; low-temperature materials.
- **Repeated proof skeletons (IDs)**: P1 MGSI, P2 SCALE, P27 STAT, P21 EXP
- **Expository structure**: S-TXT (engineering textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Declare the model assumptions up front, then write the governing equations, and only then choose solution tactics.
- Non-dimensionalize early, name the small/large parameters, and draw a regime map that explains which terms survive in each limit.
- Choose the correct ensemble, compute partition functions, and derive averages and fluctuations by differentiation identities.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Heleen Dausy PhD Thesis

- **Primary use**: Superconducting MoGe devices for quantum technology; fabrication and characterization at cryogenic/microwave frequencies.
- **Dominant frameworks**: Superconductivity; thin films; microwave measurements; device fabrication.
- **Repeated proof skeletons (IDs)**: P21 EXP, P13 SC, P10 CIRC, P8 NOISE, P26 NUM
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- State the superconducting model (BCS/Bogoliubov–de Gennes/Josephson), identify the gap and quasiparticles, then derive circuit consequences.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Janka Biznárová PhD Thesis

- **Primary use**: High-coherence superconducting devices; fabrication/materials analysis; two-level-system loss and resonator proxies.
- **Dominant frameworks**: Superconducting qubits/resonators; loss modeling; materials characterization.
- **Repeated proof skeletons (IDs)**: P21 EXP, P13 SC, P8 NOISE, P23 MEAS, P26 NUM, P10 CIRC
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- State the superconducting model (BCS/Bogoliubov–de Gennes/Josephson), identify the gap and quasiparticles, then derive circuit consequences.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Omid Noroozian PhD Thesis

- **Primary use**: Superconducting microwave resonator arrays and kinetic inductance detectors for imaging; device physics and measurements.
- **Dominant frameworks**: Superconducting resonators; quasiparticles; noise; detector arrays.
- **Repeated proof skeletons (IDs)**: P21 EXP, P13 SC, P8 NOISE, P10 CIRC, P26 NUM
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- State the superconducting model (BCS/Bogoliubov–de Gennes/Josephson), identify the gap and quasiparticles, then derive circuit consequences.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.


#### Jiansong Gao PhD Thesis

**Core “Gao-style” move:** Start from a *measurable microwave observable* (complex transmission, resonance frequency shift, internal quality factor, or noise-equivalent power), then back-propagate through a **signal chain**:  
microwave readout → resonator circuit + coupling → effective load impedance → superconducting electrodynamics → quasiparticles / two-level systems (TLS) → materials + geometry design knobs.

**Dominant skeleton blend:** P13 SC + P9 IO + P10 CIRC + P8 NOISE + P21 EXP + P2 SCALE (+ P26 NUM when fitting/calibrating).

**Proof/derivation workflow to emulate (MKID / superconducting resonator):**
1. **Define the figure of merit** (e.g., frequency responsivity δf_r/f_r per optical power, or TLS-limited noise-equivalent power).  
2. **Write the measurement model** in microwave language: S-parameters (t21/S21), resonance circle, homodyne I–Q, internal/coupling Q, and the mapping from circuit parameters → measured I–Q.
3. **Build an equivalent circuit** for the resonator (distributed λ/4 line → parallel RLC; then include coupling capacitance / feedline).  
4. **Linearize small perturbations**: treat δZ_l(t) or δσ(t) as the perturbation source, derive δt21 and δf_r as first-order responses, and explicitly expose the complex coefficient κ (that maps quasiparticle density to complex conductivity/impedance).
5. **Do dynamics in Fourier space**: show the resonator response is a **low-pass filter** with bandwidth f_r/(2Q_r); then carry this filter factor into noise spectral densities and NEP.
6. **Introduce the microscopic mechanism** (TLS or quasiparticle generation–recombination) *only when needed*, and derive temperature/power scaling laws for Q_i(T, P) and δf_r(T).
7. **Close with a design delta**: translate the derived dependence into layout/material/process changes (e.g., interdigitated capacitors, wider gaps, dielectric choice, oxide mitigation), and state what would be measured to validate the fix.

**Control knobs (explicit):**
- Geometry: center strip width s_r, gap g_r, participation ratios (electric-field energy in dielectrics), inductor/capacitor partitioning.
- Coupling: Q_c (coupling Q), matching, over/under/critical coupling.
- Internal loss: Q_i(T, P), TLS loss tangent, quasiparticle density.
- Readout: readout power P_read, internal resonator power P_int, homodyne phase vs amplitude readout.
- Noise budgeting: amplifier noise temperature, TLS frequency noise S_{δf_r}, target background-limited photon (BLIP) regime.

**Verification ritual (to emulate):**
- Fit Q_i(T) and δf_r(T) to TLS + Mattis–Bardeen-inspired forms; fit S21 circles to extract Q_i, Q_c, f_r; propagate uncertainties to NEP; compare NEP curves to BLIP and amplifier limits.

**Common pitfall called out by the style:** You can “win” on responsivity while losing on TLS noise—so always carry both *signal* and *noise* forward to NEP in the same pipeline.

#### Luca Planat PhD Thesis

- **Primary use**: Resonant and traveling-wave parametric amplification near the quantum limit; theory + experiment.
- **Dominant frameworks**: Josephson parametric amplifiers; nonlinearity; quantum noise; microwave engineering.
- **Repeated proof skeletons (IDs)**: P21 EXP, P8 NOISE, P9 IO, P13 SC, P10 CIRC, P26 NUM
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Christopher Axline PhD Thesis

- **Primary use**: Modular circuit-QED hardware; dissipation sources, microwave hygiene, and state transfer via propagating photons.
- **Dominant frameworks**: Superconducting circuits; input–output theory; loss modeling; parametric conversion.
- **Repeated proof skeletons (IDs)**: P21 EXP, P9 IO, P23 MEAS, P8 NOISE, P26 NUM, P10 CIRC
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.


### Quantum Mechanics Core textbooks + problem technique

#### Quantum Mechanics vol. I, II and III, 2nd ed.

- **Primary use**: Comprehensive quantum mechanics with strong mathematical structure and extensive worked derivations/exercises.
- **Dominant frameworks**: Hilbert spaces; operators; scattering; identical particles; perturbation theory.
- **Repeated proof skeletons (IDs)**: P5 EIG, P6 PERT, P3 SYM, P0 DLT, P25 TM, P23 MEAS
- **Expository structure**: S-TXT (multi-volume textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Choose a perturbation parameter, build a hierarchy of approximations, and track error terms throughout.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Quantum Mechanics_Concepts and Applications

- **Primary use**: Structured quantum mechanics with many solved problems and exercises; strong on mathematical tools.
- **Dominant frameworks**: Hilbert space; operators; angular momentum; approximation methods.
- **Repeated proof skeletons (IDs)**: P5 EIG, P6 PERT, P3 SYM, P0 DLT, P25 TM, P23 MEAS
- **Expository structure**: S-TXT (textbook with solved problems)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Choose a perturbation parameter, build a hierarchy of approximations, and track error terms throughout.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Quantum Mechanics for Scientists and Engineers

- **Primary use**: Quantum mechanics with engineering examples (tunneling, periodic potentials) and computational viewpoint.
- **Dominant frameworks**: Schrödinger equation; band structure; scattering; perturbation.
- **Repeated proof skeletons (IDs)**: P5 EIG, P25 TM, P12 BAND, P6 PERT, P1 MGSI
- **Expository structure**: S-TXT (engineering-oriented textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Begin with band-structure assumptions (Bloch/effective mass), then derive density of states and carrier statistics.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Quantum Mechanics Made Simple_Lecture Notes

- **Primary use**: Engineer-friendly quantum mechanics notes; begins from classical Lagrangian/Hamiltonian and builds operator tools.
- **Dominant frameworks**: Classical mechanics (Lagrange/Hamilton); linear algebra; Schrödinger equation.
- **Repeated proof skeletons (IDs)**: P4 VAR, P5 EIG, P6 PERT, P1 MGSI, P0 DLT
- **Expository structure**: S-LN (lecture notes)

What to emulate in your future proofs:
- Use lecture cadence: short statements, frequent intermediate results, and explicit 'next we show' transitions, with minimal digressions.
- Start from an energy, action, or cost functional, then extremize it to derive Euler–Lagrange or stationarity conditions.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Choose a perturbation parameter, build a hierarchy of approximations, and track error terms throughout.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Quantum Mechanics_An Introduction for Device Physicists and Electrical Engineers

- **Primary use**: Device-physics-first quantum mechanics with early emphasis on wells, tunneling, periodic potentials.
- **Dominant frameworks**: Waves; tunneling; periodic potentials; operators/bases; perturbation theory.
- **Repeated proof skeletons (IDs)**: P5 EIG, P25 TM, P12 BAND, P6 PERT, P1 MGSI
- **Expository structure**: S-TXT (engineering textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Begin with band-structure assumptions (Bloch/effective mass), then derive density of states and carrier statistics.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Quantum Mechanics

- **Primary use**: Quantum mechanics text/notes emphasizing conceptual structure plus operator methods.
- **Dominant frameworks**: Hilbert space; operators; dynamics; measurement.
- **Repeated proof skeletons (IDs)**: P5 EIG, P6 PERT, P0 DLT, P23 MEAS, P3 SYM
- **Expository structure**: S-TXT/LN (text/notes)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Choose a perturbation parameter, build a hierarchy of approximations, and track error terms throughout.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Problem Solving in Quantum Mechanics_From Basics to Real-World Applications

- **Primary use**: Worked problems emphasizing technique transfer from canonical QM to applied contexts.
- **Dominant frameworks**: Hilbert space; differential equations; scattering; approximation methods.
- **Repeated proof skeletons (IDs)**: P5 EIG, P6 PERT, P25 TM, P1 MGSI
- **Expository structure**: S-PROB (problem-solving book)

What to emulate in your future proofs:
- Use problem-solution cadence: restate givens, choose a method, execute cleanly, then generalize the trick for reuse.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Choose a perturbation parameter, build a hierarchy of approximations, and track error terms throughout.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Quantum Mechanical Phase and Time Operator

- **Primary use**: Operator-theoretic treatment of phase/time in quantum mechanics; commutation subtleties.
- **Dominant frameworks**: Operator algebra; spectral theory; measurement issues.
- **Repeated proof skeletons (IDs)**: P0 DLT, P5 EIG, P23 MEAS, P3 SYM
- **Expository structure**: S-REV (theory paper)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.


### Circuit Quantum Electrodynamics, Microwave Engineering, and Circuits

#### Circuit QED_Superconducting Qubits Coupled to Microwave Photons

- **Primary use**: Circuit-QED architecture and derivations linking qubits to resonators; strong coupling, dispersive readout.
- **Dominant frameworks**: Quantum circuits; Jaynes–Cummings; dispersive approximations; microwave resonators.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P5 EIG, P9 IO, P6 PERT, P23 MEAS, P8 NOISE
- **Expository structure**: S-TXT/LN (tutorial/notes)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.

#### David Isaac Schuster PhD Thesis

- **Primary use**: Experimental realization and theory-development of circuit quantum electrodynamics; spectroscopy and control.
- **Dominant frameworks**: Superconducting qubits; resonators; strong coupling; measurement backaction.
- **Repeated proof skeletons (IDs)**: P21 EXP, P9 IO, P23 MEAS, P5 EIG, P8 NOISE, P10 CIRC
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Quantum Electrical Circuits_Lecture Notes

- **Primary use**: Lecture notes on quantizing electrical circuits; canonical variables, modes, and coupling.
- **Dominant frameworks**: Circuit quantization; Hamiltonian mechanics; superconducting elements.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P5 EIG, P4 VAR, P6 PERT, P13 SC
- **Expository structure**: S-LN (lecture notes)

What to emulate in your future proofs:
- Use lecture cadence: short statements, frequent intermediate results, and explicit 'next we show' transitions, with minimal digressions.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Start from an energy, action, or cost functional, then extremize it to derive Euler–Lagrange or stationarity conditions.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.

#### Planar Microwave Engineering

- **Primary use**: Planar microwave component theory and design; S-parameters, transmission lines, matching networks.
- **Dominant frameworks**: Electromagnetics; transmission lines; network theory.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P9 IO, P25 TM, P2 SCALE, P1 MGSI
- **Expository structure**: S-TXT (engineering textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.

#### Electric Circuits, Volume I -- DC

- **Primary use**: Direct-current circuit analysis foundations: Kirchhoff laws, Thevenin/Norton, network reduction.
- **Dominant frameworks**: Linear algebra; resistive networks; basic measurement models.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P1 MGSI, P2 SCALE
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Declare the model assumptions up front, then write the governing equations, and only then choose solution tactics.
- Non-dimensionalize early, name the small/large parameters, and draw a regime map that explains which terms survive in each limit.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.

#### Electric Circuits, Volume II -- AC

- **Primary use**: Alternating-current circuit analysis: phasors, impedance, resonance, filters, power, transforms.
- **Dominant frameworks**: Complex analysis basics; linear systems; frequency response.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P9 IO, P5 EIG, P25 TM
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.


### Quantum Measurement, Noise, Optomechanics, and Metrology

#### Measurements in Quantum Mechanics

- **Primary use**: Collected/edited treatment of measurement in quantum mechanics, including formalism and applications.
- **Dominant frameworks**: Measurement postulates; POVMs; decoherence; open systems.
- **Repeated proof skeletons (IDs)**: P23 MEAS, P0 DLT, P8 NOISE
- **Expository structure**: S-REV/HB (edited volume)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Close by separating imprecision, backaction, and technical noise contributions, and by checking that spectra integrate to the expected variances in the relevant bandwidth.

#### Quantum Measurement

- **Primary use**: Textbook-level treatment of quantum measurement foundations and modern formalism.
- **Dominant frameworks**: Density matrices; POVMs; measurement disturbance; open systems.
- **Repeated proof skeletons (IDs)**: P23 MEAS, P0 DLT, P19 INFO
- **Expository structure**: S-TXT (textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- Close by stating equality conditions (when the bound is tight) and by giving an operational interpretation (distinguishability, coding rate, or hypothesis testing meaning).

#### Quantum Measurement Theory and its Applications

- **Primary use**: Continuous quantum measurement, stochastic master equations, and feedback/control, with applications spanning superconducting circuits, nanomechanics, and optomechanics.
- **Dominant frameworks**: Bayesian inference as state-of-knowledge; density matrices; Kraus/operator-sum representations; stochastic master equations (SMEs) and stochastic Schrödinger equations; Itô calculus; input–output theory; the linear/Gaussian reduction to the Kalman–Bucy filter; dynamic programming (Bellman / Hamilton–Jacobi–Bellman).
- **Repeated proof skeletons (IDs)**: P23 MEAS, P8 NOISE, P9 IO, P21 EXP, P26 NUM, P22 QFI, P19 INFO, P6 PERT
- **Expository structure**: S-TXT (textbook; theory-to-application with exercises and appendices)

What to emulate in your future proofs:
- Start with the classical inference analogue (Bayes, likelihoods, Gaussian noise), and then port it to quantum by upgrading probabilities to density matrices and likelihoods to measurement operators.
- Treat the environment as a continuous measurement channel: state the Markov assumption explicitly, use it to justify Lindblad and SME forms, and recover unconditional dynamics by averaging over noise realizations.
- Prefer the linear/Gaussian “fast track” whenever it applies: identify linear systems and linear measurements so the SME collapses to a Kalman filter with an explicit backaction term, and then use spectra to connect to what is actually recorded.
- When optimizing control, define the cost function first, then use Bellman / Hamilton–Jacobi–Bellman machinery to certify optimality, and separate “measurement design” (what to monitor) from “actuation” (what Hamiltonian/force to apply).
- Close by translating symbols into lab knobs: measurement strength $k$, efficiency $\eta$, filtering bandwidth, and the measured quadrature/current, and then by checking the noise budget and limiting cases (weak/strong measurement, low/high damping).

#### Quantum Measurement_Theory and Practice

- **Primary use**: Practice-oriented quantum measurement in superconducting circuits; amplifiers, readout, tomography.
- **Dominant frameworks**: Circuit QED measurement; amplifiers; signal processing; noise.
- **Repeated proof skeletons (IDs)**: P23 MEAS, P9 IO, P8 NOISE, P10 CIRC, P21 EXP
- **Expository structure**: S-LN/TXT (course notes)

What to emulate in your future proofs:
- Use lecture cadence: short statements, frequent intermediate results, and explicit 'next we show' transitions, with minimal digressions.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Introduction to Quantum Noise, Measurement, and Amplification

- **Primary use**: Tutorial/review on quantum noise, measurement backaction, and quantum-limited amplification.
- **Dominant frameworks**: Input–output theory; quantum Langevin; noise spectral densities.
- **Repeated proof skeletons (IDs)**: P8 NOISE, P23 MEAS, P9 IO, P7 LR, P10 CIRC
- **Expository structure**: S-REV (review/tutorial)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Close by presenting an equivalent circuit or transfer function and sanity-checking it with limiting cases (open/short, low/high frequency) and typical component values.

#### Quantum Mechanical Noise in an Interferometer

- **Primary use**: Classic derivation of quantum noise in interferometry and squeezing advantages; standard quantum limit.
- **Dominant frameworks**: Interferometry; quantum optics; noise spectra; squeezing.
- **Repeated proof skeletons (IDs)**: P8 NOISE, P23 MEAS, P22 QFI, P3 SYM
- **Expository structure**: S-REV (seminal paper)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Define the parameter encoding and the estimator, then compute Fisher or quantum Fisher information and apply Cramér–Rao bounds.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).

#### Quantum Optomechanics

- **Primary use**: Optomechanical interaction theory; measurement backaction, cooling, and quantum limits.
- **Dominant frameworks**: Coupled-mode Hamiltonians; input–output; noise spectra.
- **Repeated proof skeletons (IDs)**: P9 IO, P8 NOISE, P23 MEAS, P6 PERT, P1 MGSI
- **Expository structure**: S-REV/TXT (review/notes)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by separating imprecision, backaction, and technical noise contributions, and by checking that spectra integrate to the expected variances in the relevant bandwidth.

#### Quantum Noise in Mesoscopic Physics

- **Primary use**: Mesoscopic noise and full counting statistics; bridges transport and quantum optics methods.
- **Dominant frameworks**: Mesoscopic transport; correlation functions; scattering approach.
- **Repeated proof skeletons (IDs)**: P8 NOISE, P7 LR, P25 TM, P24 QFT, P18 GAUGE
- **Expository structure**: S-TXT/REV (advanced notes/book)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Define the response function (susceptibility, conductance) and derive it via Green’s functions or Kubo-like formulas.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Shiyuan Zhao PhD Thesis

- **Primary use**: Noise and squeezing theory for quantum-confined lasers; fluctuation analysis.
- **Dominant frameworks**: Quantum optics; Langevin noise; linear response.
- **Repeated proof skeletons (IDs)**: P8 NOISE, P7 LR, P5 EIG, P6 PERT
- **Expository structure**: S-REV (research paper)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Define the response function (susceptibility, conductance) and derive it via Green’s functions or Kubo-like formulas.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Close by separating imprecision, backaction, and technical noise contributions, and by checking that spectra integrate to the expected variances in the relevant bandwidth.

#### Vivishek Sudhir PhD Thesis

- **Primary use**: Quantum limits, backaction, and control in mechanical oscillator measurements.
- **Dominant frameworks**: Quantum measurement; optomechanics; noise spectra; feedback control.
- **Repeated proof skeletons (IDs)**: P23 MEAS, P8 NOISE, P9 IO, P22 QFI, P1 MGSI
- **Expository structure**: S-REV (theory paper/review)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Model the system as ports and modes, then derive scattering or input–output relations, and compute transfer functions.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).

#### Ronald Pagano PhD Thesis

- **Primary use**: Thermal noise measurement below the standard quantum limit; experimental techniques and noise budgets.
- **Dominant frameworks**: Precision measurement; optomechanics/optics; noise and quantum limits.
- **Repeated proof skeletons (IDs)**: P21 EXP, P8 NOISE, P23 MEAS, P22 QFI, P26 NUM
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Roman Schmeissner PhD Thesis

- **Primary use**: Experimental work near/below standard quantum limit; precision readout and noise engineering.
- **Dominant frameworks**: Precision measurement; quantum noise; amplifier chains.
- **Repeated proof skeletons (IDs)**: P21 EXP, P8 NOISE, P23 MEAS, P22 QFI, P26 NUM
- **Expository structure**: S-TH (experimental dissertation)

What to emulate in your future proofs:
- Use thesis cadence: problem statement and literature context, methods and apparatus, results with uncertainty, then interpretation and limitations.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Applications and Metrology at Nanometer Scale 2

- **Primary use**: Measurement systems and metrology concepts at nanometer scale; quantum engineering emphasis.
- **Dominant frameworks**: Measurement theory; instrumentation; noise and uncertainty; quantum limits.
- **Repeated proof skeletons (IDs)**: P21 EXP, P8 NOISE, P22 QFI, P10 CIRC
- **Expository structure**: S-REV/TXT (edited/collection style)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Define the parameter encoding and the estimator, then compute Fisher or quantum Fisher information and apply Cramér–Rao bounds.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.

#### Quantum Interferometry in Phase Space

- **Primary use**: Phase-space formulation of quantum interferometry; Wigner functions and precision bounds.
- **Dominant frameworks**: Phase-space methods; quantum optics; estimation theory.
- **Repeated proof skeletons (IDs)**: P22 QFI, P8 NOISE, P23 MEAS, P5 EIG
- **Expository structure**: S-REV/LN (theory notes)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the parameter encoding and the estimator, then compute Fisher or quantum Fisher information and apply Cramér–Rao bounds.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).

#### Generalized Measure of Quantum Fisher Information

- **Primary use**: Theory paper on generalized quantum Fisher information measures and properties.
- **Dominant frameworks**: Operator monotone functions; quantum estimation; matrix inequalities.
- **Repeated proof skeletons (IDs)**: P22 QFI, P19 INFO, P0 DLT, P23 MEAS
- **Expository structure**: S-REV (theory paper)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the parameter encoding and the estimator, then compute Fisher or quantum Fisher information and apply Cramér–Rao bounds.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).

#### Quantum Fisher Information and its Dynamical Nature

- **Primary use**: Theoretical discussion of quantum Fisher information as a dynamical quantity and its properties.
- **Dominant frameworks**: Quantum estimation; dynamical generators; operator inequalities.
- **Repeated proof skeletons (IDs)**: P22 QFI, P19 INFO, P23 MEAS, P0 DLT
- **Expository structure**: S-REV (theory paper)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the parameter encoding and the estimator, then compute Fisher or quantum Fisher information and apply Cramér–Rao bounds.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).

#### Introduction to Quantum Fisher Information

- **Primary use**: Introductory note/paper on quantum Fisher information and estimation bounds.
- **Dominant frameworks**: Estimation theory; quantum statistics; Cramér–Rao.
- **Repeated proof skeletons (IDs)**: P22 QFI, P19 INFO, P23 MEAS
- **Expository structure**: S-REV (intro notes)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the parameter encoding and the estimator, then compute Fisher or quantum Fisher information and apply Cramér–Rao bounds.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).

#### Sub-Quantum Fisher Information

- **Primary use**: Theory paper introducing/characterizing sub-quantum Fisher information variants.
- **Dominant frameworks**: Quantum estimation; operator inequalities; information geometry.
- **Repeated proof skeletons (IDs)**: P22 QFI, P19 INFO, P0 DLT, P23 MEAS
- **Expository structure**: S-REV (theory paper)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define the parameter encoding and the estimator, then compute Fisher or quantum Fisher information and apply Cramér–Rao bounds.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).

#### Quantum Optics in Phase Space

- **Primary use**: Phase-space quantum optics; Wigner functions; semiclassical limits; squeezing and interference.
- **Dominant frameworks**: Quantum optics; phase-space methods; coherent states.
- **Repeated proof skeletons (IDs)**: P8 NOISE, P5 EIG, P6 PERT, P22 QFI
- **Expository structure**: S-TXT (monograph)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Choose a perturbation parameter, build a hierarchy of approximations, and track error terms throughout.
- Close by stating the achievable bound (Cramér–Rao), the measurement that saturates it (or why it cannot), and the scaling with resources (time, photons, trials).


### Quantum Information, Computation, and Cryptography

#### A Mini Introduction to Information Theory

- **Primary use**: Compact, proof-oriented introduction to classical and quantum information theory (entropy, relative entropy, monotonicity).
- **Dominant frameworks**: Probability; convex analysis; operator algebras (density matrices).
- **Repeated proof skeletons (IDs)**: P19 INFO, P0 DLT, P23 MEAS
- **Expository structure**: S-REV (review paper)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by stating equality conditions (when the bound is tight) and by giving an operational interpretation (distinguishability, coding rate, or hypothesis testing meaning).

#### A Group Theoretic Approach to Quantum Information

- **Primary use**: Group-representation methods for quantum information tasks: entanglement structure, covariant measurements, symmetry-reduced channels, and optimal estimation of unknown unitary processes.
- **Dominant frameworks**: Group representation theory (finite groups + compact Lie groups); Schur–Weyl duality and Young diagrams; majorization and Schur convexity; covariant POVMs (positive operator-valued measures) and twirling; stabilizer/Clifford group methods.
- **Repeated proof skeletons (IDs)**: P3 SYM, P5 EIG, P19 INFO, P22 QFI, P23 MEAS, P0 DLT
- **Expository structure**: S-TXT (theorem-proof leaning monograph + exercises)

What to emulate in your future proofs:
- Declare the symmetry object up front: the group \(G\), the representation \(U: G\to\mathcal{U}(\mathcal{H})\), and whether your states/channels/measurements are **invariant**, **covariant**, or **equivariant** under \(G\).
- Turn “big matrices” into **block structure**: decompose \(\mathcal{H}^{\otimes n}\) into irreducible representation (irrep) sectors (often via Schur–Weyl duality), then rewrite operators in the irrep-adapted basis so computations become per-block.
- Use Schur’s lemma as a core “proof move”: if an operator commutes with the group action, conclude it is proportional to identity on each irrep block (or has a highly constrained intertwiner form), which collapses many optimizations to a low-dimensional eigenproblem.
- When optimizing a protocol, **twirl**: average over \(G\) to justify restricting attention to covariant measurements/channels, then compute figures of merit using projectors, characters, or multiplicity spaces.
- Close by mapping the group-theoretic statement back to an operational quantity (fidelity, error probability, Holevo information, or quantum Fisher information), and then check limiting regimes (qubit case, small \(n\), large-\(n\) asymptotics).

#### Quantum Information Theory

- **Primary use**: Rigorous quantum information theory: entropies, channels, capacities, and operational proofs.
- **Dominant frameworks**: Operator algebras; entropy inequalities; channel coding theorems.
- **Repeated proof skeletons (IDs)**: P19 INFO, P0 DLT, P20 CRYPTO, P23 MEAS
- **Expository structure**: S-TXT (theorem-proof textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- State the security game precisely, then prove security by reduction to a hardness assumption using hybrids.
- Close by bounding adversary advantage, stating parameter choices, and identifying which assumption (and which reduction step) dominates the security loss.

#### Quantum Shannon Theory

- **Primary use**: Quantum Shannon theory: communication capacities, coding theorems, and entropic converses.
- **Dominant frameworks**: Quantum channels; entropies; operational proofs; coding.
- **Repeated proof skeletons (IDs)**: P19 INFO, P0 DLT, P20 CRYPTO, P23 MEAS
- **Expository structure**: S-TXT (theorem-proof textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- State the security game precisely, then prove security by reduction to a hardness assumption using hybrids.
- Close by bounding adversary advantage, stating parameter choices, and identifying which assumption (and which reduction step) dominates the security loss.

#### Quantum Information Processing

- **Primary use**: General quantum information processing concepts and protocols (algorithms, gates, error correction).
- **Dominant frameworks**: Linear algebra; quantum circuits; complexity; information theory.
- **Repeated proof skeletons (IDs)**: P19 INFO, P0 DLT, P20 CRYPTO
- **Expository structure**: S-TXT (textbook/notes)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- State the security game precisely, then prove security by reduction to a hardness assumption using hybrids.
- Close by bounding adversary advantage, stating parameter choices, and identifying which assumption (and which reduction step) dominates the security loss.

#### Quantum Information Science

- **Primary use**: Lecture-notes style intro to quantum information science with hardware-conscious framing.
- **Dominant frameworks**: Quantum algorithms; error correction; qubits and control.
- **Repeated proof skeletons (IDs)**: P19 INFO, P20 CRYPTO, P23 MEAS, P10 CIRC
- **Expository structure**: S-LN (lecture notes)

What to emulate in your future proofs:
- Use lecture cadence: short statements, frequent intermediate results, and explicit 'next we show' transitions, with minimal digressions.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State the security game precisely, then prove security by reduction to a hardness assumption using hybrids.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by bounding adversary advantage, stating parameter choices, and identifying which assumption (and which reduction step) dominates the security loss.

#### Theory of Quantum Computation, Communication, and Cryptography

- **Primary use**: Proceedings/collection bridging quantum computation, communication, and cryptography theory.
- **Dominant frameworks**: Quantum algorithms; complexity; crypto security notions.
- **Repeated proof skeletons (IDs)**: P20 CRYPTO, P19 INFO, P0 DLT
- **Expository structure**: S-REV (conference proceedings/edited)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- State the security game precisely, then prove security by reduction to a hardness assumption using hybrids.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by bounding adversary advantage, stating parameter choices, and identifying which assumption (and which reduction step) dominates the security loss.

#### Post-Quantum Cryptography

- **Primary use**: Survey/introduction to cryptographic schemes secure against quantum adversaries; hardness assumptions.
- **Dominant frameworks**: Complexity theory; lattice codes; security definitions.
- **Repeated proof skeletons (IDs)**: P20 CRYPTO, P0 DLT, P19 INFO
- **Expository structure**: S-TXT/REV (textbook/survey)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- State the security game precisely, then prove security by reduction to a hardness assumption using hybrids.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Prove inequalities by convexity/concavity, monotonicity under channels, and data-processing arguments.
- Close by bounding adversary advantage, stating parameter choices, and identifying which assumption (and which reduction step) dominates the security loss.

#### Quantum Computing Architecture and Hardware for Engineers

- **Primary use**: Hardware architecture view of quantum computing; engineering constraints, scaling, and device modalities.
- **Dominant frameworks**: Quantum computing systems; cryo/microwave; control electronics; error sources.
- **Repeated proof skeletons (IDs)**: P10 CIRC, P21 EXP, P8 NOISE, P23 MEAS, P19 INFO
- **Expository structure**: S-TXT (engineering-focused textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Translate physics into an equivalent circuit, write Kirchhoff’s laws, and reduce the network to interpretable blocks.
- Treat experiments as inference pipelines: calibration → measurement → uncertainty budget → parameter extraction.
- Define noise sources and stochastic variables, then compute power spectral densities and noise-equivalent metrics.
- Close with a calibration/uncertainty budget, and compare theory to data via fit residuals, repeatability across samples, and systematics checks.


### Quantum Field Theory, Gauge Theory, and Strings

#### More On Gauge Theory And Geometric Langlands

- **Primary use**: Advanced gauge theory and geometric Langlands perspectives; categorical/topological structures.
- **Dominant frameworks**: Gauge theory; moduli spaces; representation theory; topology.
- **Repeated proof skeletons (IDs)**: P18 GAUGE, P24 QFT, P0 DLT, P16 FORMS
- **Expository structure**: S-REV/LN (advanced theory notes)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- Start from a Lagrangian with symmetries, derive equations of motion and Feynman rules, then compute observables.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Algebraic Structures and Differential Geometry in 2D String Theory

- **Primary use**: Mathematical structures underlying 2D string theory; geometry-to-field-theory dictionary building.
- **Dominant frameworks**: Differential geometry; conformal/quantum field theory; algebraic structures.
- **Repeated proof skeletons (IDs)**: P24 QFT, P16 FORMS, P18 GAUGE, P0 DLT
- **Expository structure**: S-REV/LN (theory monograph)

What to emulate in your future proofs:
- Use review cadence: motivation and scope, define conventions, state the key results early, then derive and discuss assumptions.
- Start from a Lagrangian with symmetries, derive equations of motion and Feynman rules, then compute observables.
- Define the manifold, forms, and orientation, then compute with exterior derivative and wedge product instead of coordinates.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Quantum Fields and Strings

- **Primary use**: Notes-style treatment of quantum fields and string theory topics; model building and symmetry structure.
- **Dominant frameworks**: Quantum field theory; string theory; gauge symmetry; geometry.
- **Repeated proof skeletons (IDs)**: P24 QFT, P18 GAUGE, P16 FORMS, P0 DLT
- **Expository structure**: S-LN (notes/compendium)

What to emulate in your future proofs:
- Use lecture cadence: short statements, frequent intermediate results, and explicit 'next we show' transitions, with minimal digressions.
- Start from a Lagrangian with symmetries, derive equations of motion and Feynman rules, then compute observables.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- Define the manifold, forms, and orientation, then compute with exterior derivative and wedge product instead of coordinates.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### The Black Book of Quantum Chromodynamics

- **Primary use**: Quantum chromodynamics field theory foundations and computations.
- **Dominant frameworks**: Non-Abelian gauge theory; renormalization; perturbation theory.
- **Repeated proof skeletons (IDs)**: P24 QFT, P18 GAUGE, P3 SYM, P0 DLT, P6 PERT
- **Expository structure**: S-TXT/REV (theory text/notes)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Start from a Lagrangian with symmetries, derive equations of motion and Feynman rules, then compute observables.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Weak Interactions

- **Primary use**: Weak interactions via gauge theory and effective field theory; symmetry-driven particle physics derivations.
- **Dominant frameworks**: Gauge theory; group representations; effective field theory.
- **Repeated proof skeletons (IDs)**: P24 QFT, P18 GAUGE, P3 SYM, P0 DLT, P6 PERT
- **Expository structure**: S-TXT (theory monograph)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Start from a Lagrangian with symmetries, derive equations of motion and Feynman rules, then compute observables.
- Define connections and curvature (field strength), then compute holonomy, Berry phases, or topological invariants.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by restating the result in a coordinate-free invariant form, then translating back to standard vector/tensor notation on a worked example to verify equivalence.

#### Quantum Theory from First Principles

- **Primary use**: Foundational formulation of quantum theory emphasizing axioms, structure, and operational meaning.
- **Dominant frameworks**: Axiomatic/operational QM; Hilbert spaces; dynamics.
- **Repeated proof skeletons (IDs)**: P0 DLT, P5 EIG, P23 MEAS, P3 SYM
- **Expository structure**: S-TXT/REV (foundations text)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- State definitions, and also state domains/codomains, units, and quantifiers, before any manipulation.
- Cast the problem as an eigenvalue/eigenmode problem, and use orthogonality/completeness to expand solutions.
- Formulate states as density matrices, write measurements as POVMs or Kraus maps, and propagate backaction explicitly.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.

#### Quantum Transport

- **Primary use**: Quantum transport techniques across mesoscopic/nano systems; conductance, scattering, Green functions.
- **Dominant frameworks**: Landauer–Büttiker; Green functions; nonequilibrium methods.
- **Repeated proof skeletons (IDs)**: P7 LR, P25 TM, P12 BAND, P24 QFT, P6 PERT
- **Expository structure**: S-TXT (specialized text/notes)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Define the response function (susceptibility, conductance) and derive it via Green’s functions or Kubo-like formulas.
- Partition space into regions, write general solutions in each region, and use boundary matching as the core proof move.
- Begin with band-structure assumptions (Bloch/effective mass), then derive density of states and carrier statistics.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.


### Foundations classical physics

#### Fundamentals of Physics

- **Primary use**: Core mechanics, special relativity, and thermodynamics; conceptual plus mathematical foundations.
- **Dominant frameworks**: Newtonian/Lagrangian mechanics; Lorentz invariance; thermodynamics/stat mech.
- **Repeated proof skeletons (IDs)**: P1 MGSI, P4 VAR, P3 SYM, P2 SCALE, P27 STAT
- **Expository structure**: S-TXT (foundations textbook)

What to emulate in your future proofs:
- Use a chapter-like cadence: preview the goal, define symbols/units, derive, then summarize and add practice checks.
- Declare the model assumptions up front, then write the governing equations, and only then choose solution tactics.
- Start from an energy, action, or cost functional, then extremize it to derive Euler–Lagrange or stationarity conditions.
- Identify symmetries and invariances first, then derive conserved quantities or selection rules, and reduce the problem dimension.
- Close by mapping symbols back to observables, checking dimensions and limiting cases, and stating which assumptions would break first in a real device or experiment.


## Acronym Glossary

```text
DLT: Definitions → Lemma → Theorem → Proof
MGSI: Model/assumptions → Governing equations → boundary/initial conditions → Solve → Interpret/sanity-check
SCALE: Non-dimensionalization and scaling/regime mapping
SYM: Symmetry and conserved quantities/selection rules
VAR: Variational principle / energy or action functional
EIG: Eigenproblem / diagonalization / mode expansion
PERT: Perturbation theory / approximation hierarchy
LR: Linear response / Green’s functions / Kubo formalism
NOISE: Noise modeling via spectral densities and quantum limits
IO: Input–output / scattering, S-parameters
CIRC: Circuit modeling and network transformations
DDP: Drift–diffusion–Poisson (semiconductor device equations)
BAND: Band theory (Bloch/effective mass), density of states, transport
SC: Superconductivity (Bardeen–Cooper–Schrieffer; Bogoliubov–de Gennes; Josephson)
MAG: Micromagnetics + Landau–Lifshitz–Gilbert dynamics
SPIN: Spin transport/torque (spin Hall effect, spin–orbit torque)
FORMS: Differential forms and coordinate-free calculus on manifolds
GA: Geometric algebra (a Clifford algebra) methods
GAUGE: Gauge theory and topology (connections, curvature, invariants)
INFO: Information theory (entropy, relative entropy, inequalities)
CRYPTO: Cryptography reductions and security proofs
EXP: Experimental inference pipeline (calibration, uncertainty, extraction)
QFI: Quantum Fisher information and estimation bounds
MEAS: Quantum measurement and open systems (density matrices, POVMs, master equations)
QFT: Quantum field theory (Lagrangians, path integrals, renormalization)
TM: Transfer-matrix / boundary matching
NUM: Numerical simulation and parameter inference
STAT: Statistical mechanics (ensembles, partition functions)
```

## Etymologies and Portmanteaus

- **Spintronics** = *spin* + *electronics*: emphasizes using spin angular momentum as an information carrier, in addition to (or instead of) charge transport.
- **Cryogenics** derives from Greek *kryos* (cold) + *-genics* (producing): engineering and physics of producing and using very low temperatures.
- **Micromagnetics** combines *micro-* (small scale) with *magnetics*: continuum magnetization fields modeled at sub-domain scales, where exchange and demagnetizing energies compete.
- **Entropy** comes from Greek *en-* (in) + *trope* (turning/transforming), popularized by Clausius; in information theory, it quantifies uncertainty and compressibility.
- **Hilbert space** is named after David Hilbert; it is the complete inner-product vector space underpinning operator-based quantum mechanics.
- **Kronig–Penney** and **Bloch** are eponymous band-structure constructs; they encode periodicity into spectral structure, which then propagates into effective-mass and transport models.

---

# Examples

## Onri Pattern Library P0–P27: One Derivation + One Fully-Worked Numerical Example per Pattern ID

This part of the document implements the **Pattern Library skeleton IDs (P0–P27)** as repeatable proof/derivation workflows, by providing, for each pattern ID, (i) one rigorous symbolic derivation and (ii) one rigorous-and-accurate numerical example with realistic values, finishing with both conventional scientific notation, plain decimals, and supplementary scientific e-notation.

## Scope, conventions, and reproducibility notes

This pattern library is written to be **auditable**: each derivation states the minimum assumptions required for the stated result, while each numerical example states its parameter values, units, and (when relevant) physical constants. Unless a pattern explicitly overrides them, the following conventions apply.

### Mathematical conventions

- **Inner products.** For complex vector spaces, the inner product satisfies conjugate symmetry $\langle x,y\rangle = \overline{\langle y,x\rangle}$ and is linear in the **second** argument and conjugate-linear in the **first** (the “mathematicians’ convention”). Norms are $\|x\| := \sqrt{\langle x,x\rangle}$.
- **Logarithms.** $\ln$ denotes the natural logarithm, and $\log_{10}$ denotes base-10 logarithm.
- **Smoothness.** When Euler–Lagrange, Taylor, or interchange-of-limit arguments appear, assume the minimum differentiability needed (stated locally in each pattern).
- **Order notation.** $O(\varepsilon^k)$ is used in its standard asymptotic sense as $\varepsilon\to 0$.

### Physical conventions

- **Units.** International System of Units (SI) are used unless otherwise stated. When electron-volts (eV) appear, the exact conversion $1\,\mathrm{eV}=e\,\mathrm{J}$ is used.
- **Noise spectral density.** Unless otherwise stated, **one-sided** power spectral density (PSD) is used for real-valued time-domain noise signals: integration is from $0$ to bandwidth $B$ in Hz.
- **Causality and steady state.** Frequency-domain “susceptibilities” and steady-state sinusoidal solutions assume linear time-invariant dynamics and that transients have decayed.

### Fundamental constants used in numerical examples

| Constant | Symbol | Value | Units | Notes |
| :--- | :---: | ---: | :---: | :--- |
| Elementary charge | $e$ | 1.602176634e-19 | C | Exact (2019 SI). |
| Planck constant | $h$ | 6.62607015e-34 | J·s | Exact (2019 SI). |
| Reduced Planck constant | $\hbar = h/(2\pi)$ | 1.0545718176461565e-34 | J·s | Derived from exact $h$. |
| Boltzmann constant | $k_B$ | 1.380649e-23 | J/K | Exact (2019 SI). |
| Speed of light | $c$ | 299792458 | m/s | Exact (SI definition). |
| Electron rest mass | $m_0$ | 9.1093837015e-31 | kg | CODATA (used for semiconductor effective-mass example(s)). |
| Joule–electron-volt conversion | $1\,\mathrm{eV}$ | 1.602176634e-19 | J | Exact (because $e$ is exact). |

## Pattern index table

| ID | Mnemonic | Skeleton recipe |
| ---: | :--------- | :---------------------------- |
| P0 | DLT | Definitions → Lemma → Theorem → Proof (formal math). |
| P1 | MGSI | Model/assumptions → governing equations → boundary/initial conditions → solve → interpret/sanity-check. |
| P2 | SCALE | Non-dimensionalization → scaling laws → regime map → limiting cases. |
| P3 | SYM | Symmetry → conserved quantities/ selection rules → reduced dynamics. |
| P4 | VAR | Variational principle/ energy functional → extremize → Euler–Lagrange/ stationarity → stability. |
| P5 | EIG | Eigenproblem/ diagonalization → spectrum → mode expansion. |
| P6 | PERT | Perturbation/ approximation hierarchy (small parameter) → corrections → error bounds/checks. |
| P7 | LR | Linear response/ Green’s functions/ Kubo → susceptibilities, conductances, correlation functions. |
| P8 | NOISE | Stochastic processes → spectral density → noise-equivalent quantities → quantum limits. |
| P9 | IO | Input–output/ scattering theory → S-parameters, transfer functions, impedance matching. |
| P10 | CIRC | Circuit modeling → network synthesis → small-signal, impedance/admittance transformations. |
| P11 | DDP | Semiconductor Poisson + continuity + drift–diffusion → depletion/quasi-neutral approximations → I–V laws. |
| P12 | BAND | Band theory (Bloch/Kronig–Penney/effective mass) → density of states → transport coefficients. |
| P13 | SC | Superconductivity (BCS/Bogoliubov–de Gennes/Josephson) → gap, quasiparticles, circuits. |
| P14 | MAG | Micromagnetics (energy terms) + Landau–Lifshitz–Gilbert dynamics → domains, switching. |
| P15 | SPIN | Spin transport/torque (spin Hall, spin–orbit torque) → magnetization dynamics & device metrics. |
| P16 | FORMS | Manifolds + differential forms + Stokes/Gauss → coordinate-free calculus. |
| P17 | GA | Geometric/Clifford algebra → multivectors, rotors → coordinate-free physics. |
| P18 | GAUGE | Gauge theory/topology → connections, curvature, holonomy, Berry phase/topological invariants. |
| P19 | INFO | Entropy/relative entropy → convexity/monotonicity → information inequalities. |
| P20 | CRYPTO | Cryptographic security reductions → hybrid arguments → hardness assumptions. |
| P21 | EXP | Experimental pipeline → calibration → measurement → uncertainty budgeting → inference. |
| P22 | QFI | Fisher/quantum Fisher information → Cramér–Rao bounds → optimal measurements/estimators. |
| P23 | MEAS | Quantum measurement/open systems → density matrices, Kraus maps, master/Lindblad equations. |
| P24 | QFT | Quantum field theory → Lagrangians, path integrals, renormalization, effective field theory. |
| P25 | TM | Transfer matrix/ scattering matrix/ boundary matching in 1D & wave systems. |
| P26 | NUM | Numerical simulation + parameter estimation → finite elements/finite differences, fitting, sensitivity. |
| P27 | STAT | Statistical mechanics → ensembles/partition functions → thermodynamic potentials & fluctuations. |

---

## Tree of pattern connections

```
Pattern Library (P0–P27)
├─ Proof/ math structure
│  ├─ P0 DLT   (Definitions→Lemma→Theorem→Proof)
│  ├─ P3 SYM   (Symmetry→Conservation)
│  ├─ P4 VAR   (Variational→Euler–Lagrange)
│  ├─ P5 EIG   (Eigen→Modes)
│  ├─ P6 PERT  (Small parameter→Corrections)
│  ├─ P16 FORMS (Differential forms→Stokes)
│  ├─ P17 GA   (Geometric algebra→Rotors)
│  ├─ P18 GAUGE (Connections→Berry phase)
│  └─ P19 INFO (Entropy→Inequalities)
├─ Physical modeling & dynamical systems
│  ├─ P1 MGSI  (Model→Solve→Interpret)
│  ├─ P2 SCALE (Non-dimensionalize→Regimes)
│  ├─ P7 LR    (Linear response→Susceptibility)
│  ├─ P8 NOISE (Stochastic→Spectral density)
│  └─ P27 STAT (Ensembles→Thermodynamics)
├─ Hardware/ devices/ waves
│  ├─ P9 IO    (Scattering, S-parameters)
│  ├─ P10 CIRC (Circuit equivalents & transforms)
│  ├─ P11 DDP  (Drift–diffusion→Diode I–V)
│  ├─ P12 BAND (Bands→Density of states)
│  ├─ P13 SC   (Josephson, quasiparticles)
│  ├─ P14 MAG  (LLG dynamics)
│  ├─ P15 SPIN (Spin Hall/ SOT)
│  └─ P25 TM   (Transfer matrices)
└─ Inference/ estimation/ computation/ security
   ├─ P20 CRYPTO (Reductions & hybrids)
   ├─ P21 EXP    (Calibration→Uncertainty)
   ├─ P22 QFI    (Fisher info→Cramér–Rao)
   ├─ P23 MEAS   (Kraus, Lindblad)
   ├─ P24 QFT    (Field equations)
   └─ P26 NUM    (Discretize→Fit→Sensitivity)
```

---

## P0 DLT: Cauchy–Schwarz via a quadratic-positivity lemma

**Intuitive explanation.** Because a squared length can never be negative, expanding that squared length carefully forces an inequality.

**Grad-level framing.** In an inner-product space, the nonnegativity of the quadratic form $\|x - t y\|^2$ for all $t\in\mathbb{R}$ implies a discriminant constraint that is equivalent to Cauchy–Schwarz.

### Assumptions, conventions, and validity domain

- **Space.** $(V,\langle\cdot,\cdot\rangle)$ is a real or complex inner-product space; in particular $\langle x,x\rangle\ge 0$ with equality iff $x=0$.
- **Conventions.** For complex spaces, conjugation is handled explicitly so the final inequality is $|\langle x,y\rangle|\le \|x\|\,\|y\|$.
- **Edge cases.** If $y=0$, the inequality is trivial; otherwise $\|y\|>0$.

### Symbolic derivation Definitions → Lemma → Theorem → Proof

**Definitions.** Let $(V,\langle\cdot,\cdot\rangle)$ be a real or complex inner-product space and define $\|x\|:=\sqrt{\langle x,x\rangle}$.

**Claim (Cauchy–Schwarz).** For all $x,y\in V$,
$$
|\langle x,y\rangle|\le \|x\|\,\|y\|.
$$

**Proof (complex-safe minimization of a nonnegative quadratic form).**

If $y=0$ then $\langle x,y\rangle=0$ and the claim is immediate. Assume $y\neq 0$, so $\langle y,y\rangle=\|y\|^2>0$.

For any scalar $t\in\mathbb{C}$, define
$$
f(t):=\|x-ty\|^2=\langle x-ty,x-ty\rangle\ge 0.
$$
Expand using conjugate symmetry and linearity in the second argument:
$$
f(t)=\langle x,x\rangle - t\langle x,y\rangle - \overline{t}\langle y,x\rangle + |t|^2\langle y,y\rangle
= \|x\|^2 - t\langle x,y\rangle - \overline{t}\,\overline{\langle x,y\rangle} + |t|^2\|y\|^2.
$$

Choose $t = \langle y,x\rangle/\langle y,y\rangle = \overline{\langle x,y\rangle}/\|y\|^2$. Then
$$
t\langle x,y\rangle = \frac{|\langle x,y\rangle|^2}{\|y\|^2}
\quad\text{and}\quad
|t|^2\|y\|^2 = \frac{|\langle x,y\rangle|^2}{\|y\|^2}.
$$
Substitute into $f(t)\ge 0$:
$$
0\le f(t)=\|x\|^2 - \frac{|\langle x,y\rangle|^2}{\|y\|^2}.
$$
Rearrange:
$$
|\langle x,y\rangle|^2 \le \|x\|^2\|y\|^2
\quad\Rightarrow\quad
|\langle x,y\rangle|\le \|x\|\,\|y\|.
$$

**Equality condition.** Equality holds if and only if $x$ and $y$ are linearly dependent. (In the specific case where $y \neq 0$, this corresponds to the error term vanishing, i.e., $x - ty = 0$).

**If the assumptions are false, how to make them true.** If your “dot product” is not a positive-definite inner product (e.g., an indefinite bilinear form as in Minkowski space), then the quantity $\|x\|=\sqrt{\langle x,x \rangle}$ is not a valid norm (it may be imaginary or zero for non-zero vectors), and Cauchy–Schwarz need not hold. To recover a Cauchy–Schwarz-type bound, either (i) restrict to a subspace where the form is positive definite, or (ii) replace the form by a positive-definite Gram inner product induced by a basis/metric choice; both operations change the geometry and therefore change which inequalities are valid.

### Numerical example

Let $a=(3,4,12)$ and $b=(1,0,2)$. Then
$$
a\cdot b = 3\cdot 1 + 4\cdot 0 + 12\cdot 2 = 27,
$$
and
$$
\|a\|_2 = \sqrt{3^2+4^2+12^2} = \sqrt{169}=13,\qquad
\|b\|_2 = \sqrt{1^2+0^2+2^2}=\sqrt{5}.
$$
Cauchy–Schwarz predicts $|a\cdot b|\le \|a\|_2\|b\|_2 = 13\sqrt{5}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $a\cdot b$ | $2.7000\times 10^{1}$ | 27.0000 | 2.7000e1 |
| $\|a\|_2$ | $1.3000\times 10^{1}$ | 13.0000 | 1.3000e1 |
| $\|b\|_2$ | $2.2361\times 10^{0}$ | 2.2361 | 2.2361e0 |
| $\|a\|_2\,\|b\|_2$ | $2.9069\times 10^{1}$ | 29.0689 | 2.9069e1 |
| $\lvert a\cdot b \lvert$ | $2.7000\times 10^{1}$ | 27.0000 | 2.7000e1 |

### 5 of 5 rigor addendum

#### Theorem Cauchy–Schwarz inequality in an inner product space

Let $(V,\langle\cdot,\cdot\rangle)$ be a real or complex inner product space, and define the induced norm by
$$
\|x\| \equiv \sqrt{\langle x,x\rangle}.
$$
Then, for all $x,y\in V$,
$$
|\langle x,y\rangle| \le \|x\|\,\|y\|.
$$
Moreover, if $y\neq 0$, equality holds if and only if $x$ is a scalar multiple of $y$.

#### Proof with the quadratic-positivity lemma

If $y=0$, then both sides equal $0$ and the result holds. Assume $y\neq 0$.

For the complex case, choose
$$
t^\star \equiv \frac{\langle y,x\rangle}{\langle y,y\rangle},
$$
and consider the nonnegative quantity
$$
0 \le \|x - t^\star y\|^2 = \langle x - t^\star y, x - t^\star y\rangle.
$$
Expanding using conjugate symmetry and sesquilinearity yields
$$
\|x - t^\star y\|^2
= \|x\|^2 - \frac{|\langle x,y\rangle|^2}{\|y\|^2}.
$$
Therefore $\|x\|^2 \ge \frac{|\langle x,y\rangle|^2}{\|y\|^2}$, which rearranges to $|\langle x,y\rangle|\le \|x\|\,\|y\|$.

Equality holds iff $\|x - t^\star y\|^2=0$, i.e., iff $x=t^\star y$.

#### Proof-obligations checklist

- [x] Specify field: real or complex.
- [x] Specify inner product convention and induced norm.
- [x] Handle the $y=0$ case explicitly.
- [x] Choose $t^\star$ using the inner product (complex-safe).
- [x] State the equality condition as linear dependence.

#### Reproducible computation

```python
import numpy as np

# Control knobs
a = np.array([3.0, 4.0, 12.0])
b = np.array([1.0, 0.0, 2.0])

dot = float(np.dot(a, b))
na = float(np.linalg.norm(a))
nb = float(np.linalg.norm(b))

print("a·b =", dot)
print("||a|| =", na)
print("||b|| =", nb)
print("||a||·||b|| =", na * nb)

assert abs(dot) <= na * nb + 1e-12
```

#### Primary sources

- MIT 18.06 Linear Algebra lecture notes, Cauchy–Schwarz inequality, PDF.
- Sheldon Axler, *Linear Algebra Done Right*, Inner Product Spaces chapter, PDF.

---

## P1 MGSI: RC step response from a governing first-order differential equation

**Intuitive explanation.** A capacitor fills up quickly at first and then more slowly, because the voltage difference driving current shrinks.

**Grad-level framing.** A linear time-invariant one-port with state variable $V_C$ yields a stable first-order ODE, solvable by an integrating factor.

### Assumptions, conventions, and validity domain

- **Circuit model.** Ideal lumped resistor $R>0$ and capacitor $C>0$, time-invariant, linear, and memoryless beyond $C$.
- **Excitation.** Step input $V_{\mathrm{in}}(t)=V_0 u(t)$ with finite $V_0$, and initial condition $V_C(0^-)=V_C(0)=0$.
- **Well-posedness.** The governing ordinary differential equation (ODE) has a unique solution for $t\ge 0$ by standard linear ODE theory.

### Symbolic derivation Model → Governing equations → IC → Solve → Interpret

**Model & assumptions.** Ideal resistor $R$, ideal capacitor $C$, driven by a step $V_\text{in}(t)=V_0\,u(t)$, with $V_C(0)=0$.

**Governing equation (KCL).** Current through $R$ equals current into $C$:
$$
\frac{V_\text{in}(t)-V_C(t)}{R} = C\frac{dV_C}{dt}.
$$
Rearrange:
$$
\frac{dV_C}{dt} + \frac{1}{RC}V_C = \frac{1}{RC}V_\text{in}(t).
$$

**Solve for $t\ge 0$ with $V_\text{in}=V_0$.** Using integrating factor $\mu(t)=e^{t/(RC)}$:
$$
\frac{d}{dt}\Big(e^{t/(RC)}V_C(t)\Big)=\frac{V_0}{RC}e^{t/(RC)}.
$$
Integrate from $0$ to $t$ and apply $V_C(0)=0$:
$$
V_C(t)=V_0\left(1-e^{-t/(RC)}\right),\qquad t\ge 0.
$$

**Interpretation.** The time constant $\tau:=RC$ is the $1-e^{-1}\approx 63.2\%$ rise time scale.

**If the assumptions are false, how to make them true.** If $C$ has leakage or dielectric absorption, or if $R$ is frequency dependent, the ODE becomes augmented or replaced by a convolutional impedance model; that changes the identity from a first-order lumped LTI RC to a higher-order, or distributed, dynamical system.

### Numerical example

Take $R=10\ \mathrm{k\Omega}$, $C=100\ \mathrm{nF}$, and $V_0=5\ \mathrm{V}$. Then $\tau=RC=1\ \mathrm{ms}$.

At $t=1\ \mathrm{ms}$:
$$
V_C(1\mathrm{ms})=5\left(1-e^{-1}\right).
$$

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\tau = RC\;[\mathrm{s}]$ | $1.0000\times 10^{-3}$ | 0.0010 | 1.0000e-3 |
| $V_C(t=1\mathrm{ms})\;[\mathrm{V}]$ | $3.1606\times 10^{0}$ | 3.1606 | 3.1606e0 |

### 5 of 5 rigor addendum

#### Proposition RC step response as a unique solution to an initial value problem

Let $R>0$, $C>0$, and consider the circuit equation
$$
RC\,\frac{dV_C}{dt} + V_C = V_0,
\qquad V_C(0)=0,
\qquad t\ge 0,
$$
which models an ideal lumped resistor-capacitor network driven by a constant step $V_0$ applied at $t=0$.

Then the unique solution for $t\ge 0$ is
$$
V_C(t) = V_0\left(1-e^{-t/(RC)}\right).
$$

#### Unit discipline check

- $[R]=\Omega = \mathrm{V/A}$
- $[C]=\mathrm{F}=\mathrm{C/V}$
- Therefore $[RC]=\Omega\cdot\mathrm{F}=\mathrm{s}$, so $t/(RC)$ is dimensionless as required.

#### Error certificate as an uncertainty and tolerance budget

Even though the model solution is exact, *real* components have tolerances. Let $\tau \equiv RC$.

If $R$ and $C$ have standard uncertainties $u_R$ and $u_C$, and are treated as independent, then
$$
\frac{u_\tau}{\tau} \approx \sqrt{\left(\frac{u_R}{R}\right)^2 + \left(\frac{u_C}{C}\right)^2 }.
$$

For $V_C(t)=V_0(1-e^{-t/\tau})$, the first-order sensitivity to $\tau$ is
$$
\frac{\partial V_C}{\partial \tau} = V_0\,\frac{t}{\tau^2}\,e^{-t/\tau}.
$$
So a first-order uncertainty estimate is
$$
u_{V_C}(t) \approx \left|\frac{\partial V_C}{\partial \tau}\right| u_\tau,
$$
and additional uncertainty from $V_0$ can be added similarly.

If the capacitor has leakage or dielectric absorption, the system identity changes: the one-state model becomes a higher-order or distributed model, and $V_C(t)$ is no longer a pure single exponential.

#### Reproducible computation

```python
import math

# Control knobs
R = 10e3          # ohms
C = 100e-9        # farads
V0 = 5.0          # volts
t = 1e-3          # seconds

tau = R * C
Vc = V0 * (1.0 - math.exp(-t / tau))

print("tau = RC [s] =", tau)
print("V_C(t) [V] =", Vc)

# Inequality sanity checks
assert tau > 0
assert 0.0 <= Vc <= V0 + 1e-12
```

#### Primary sources

- EECS 16B note on capacitors, RC circuits, and differential equations, PDF.
- University of Houston ECE single-time-constant circuits notes, PDF.

---

## P2 SCALE: Heat equation non-dimensionalization and the Fourier number

**Intuitive explanation.** If you double the length scale, diffusion takes about four times longer, because it has to random-walk farther.

**Grad-level framing.** Non-dimensionalization replaces dimensional parameters with dimensionless groups, enabling regime maps and asymptotics.

### Assumptions, conventions, and validity domain

- **Material model.** Constant thermal diffusivity $\alpha>0$ (no temperature dependence, no spatial dependence).
- **Geometry.** One-dimensional spatial coordinate $x\in[0,L]$ with $L>0$; boundary/initial conditions are assumed to be compatible with classical solutions.
- **Interpretation.** The derived timescale $t_c=L^2/\alpha$ is an order-of-magnitude diffusion time; detailed solutions depend on boundary conditions.

### Symbolic derivation Non-dimensionalization → Scaling law → Regime parameter

Start with the 1D heat equation on $x\in[0,L]$:
$$
\frac{\partial u}{\partial t}=\alpha\,\frac{\partial^2 u}{\partial x^2}.
$$
Define dimensionless variables:
$$
x=L\,x',\qquad t=t_c\,t',\qquad u=u_0\,u'.
$$
Then
$$
\frac{\partial}{\partial t}=\frac{1}{t_c}\frac{\partial}{\partial t'},\qquad
\frac{\partial^2}{\partial x^2}=\frac{1}{L^2}\frac{\partial^2}{\partial x'^2}.
$$
Substitute:
$$
\frac{u_0}{t_c}u'_{t'}=\alpha\,\frac{u_0}{L^2}u'_{x'x'}
\quad\Rightarrow\quad
u'_{t'}=\left(\frac{\alpha t_c}{L^2}\right)u'_{x'x'}.
$$
Choose $t_c:=L^2/\alpha$ to get
$$
u'_{t'}=u'_{x'x'}.
$$

Define the Fourier number (dimensionless time)
$$
\mathrm{Fo}:=\frac{\alpha t}{L^2}=\frac{t}{t_c}.
$$

**If the assumptions are false, how to make them true.** If $\alpha$ depends on $u$ or $x$, scaling produces residual dimensionless parameters, and the identity changes from linear diffusion to nonlinear, heterogeneous diffusion.

### Numerical example

Let $\alpha=1.0\times 10^{-5}\ \mathrm{m^2/s}$, $L=0.10\ \mathrm{m}$, and evaluate at $t=60\ \mathrm{s}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $t_c=L^2/\alpha\;[\mathrm{s}]$ | $1.0000\times 10^{3}$ | 1,000.0000 | 1.0000e3 |
| $\mathrm{Fo}=\alpha t/L^2\;[-]$ | $6.0000\times 10^{-2}$ | 0.0600 | 6.0000e-2 |

### 5 of 5 rigor addendum

#### Definition Fourier number as a regime parameter

For the heat equation
$$
\frac{\partial T}{\partial t} = \alpha \frac{\partial^2 T}{\partial x^2},
$$
choose a length scale $L$ and define the Fourier number
$$
\mathrm{Fo} \equiv \frac{\alpha t}{L^2}.
$$

Fo is the dimensionless ratio between elapsed time and the characteristic diffusion time $t_d=L^2/\alpha$.

#### Regime map template

A practical, auditable regime map uses explicit inequalities:

- **Early-time diffusion:** $\mathrm{Fo} \le 0.1$. The diffusion length $\delta \sim \sqrt{\alpha t}$ satisfies $\delta \ll L$.
- **Crossover:** $0.1 < \mathrm{Fo} < 10$. Boundary conditions and geometry begin to dominate.
- **Late-time approach to steady state:** $\mathrm{Fo} \ge 10$. Transients are strongly suppressed, and low-order eigenmodes dominate.

The constants $0.1$ and $10$ are heuristic “engineering thresholds.” For a monograph-grade analysis, they can be replaced by thresholds derived from the first neglected eigenmode magnitude in the particular geometry.

#### Error certificate

The nondimensionalization itself is exact. The approximation enters when you interpret “small” or “large” Fo as implying a model reduction, such as a semi-infinite approximation or a steady-state approximation. In that case, the error certificate should be tied to the ratio of neglected eigenmodes or to the boundary-layer thickness ratio $\delta/L$.

#### Reproducible computation

```python
# Control knobs
alpha = 1.0e-5   # m^2/s
L = 0.10         # m
t = 60.0         # s

Fo = alpha * t / (L**2)
t_d = (L**2) / alpha

print("Fo =", Fo)
print("diffusion time t_d [s] =", t_d)
print("t / t_d =", t / t_d)

# Regime classification
if Fo <= 0.1:
    regime = "early-time diffusion"
elif Fo >= 10.0:
    regime = "late-time / near steady"
else:
    regime = "crossover"

print("regime =", regime)
```

#### Primary sources

- MIT OpenCourseWare 18.303 notes on the heat equation, PDF.
- Stanford Math 220B handout on the heat equation, PDF.

---

## P3 SYM: Translation symmetry implies momentum conservation Noether-style

**Intuitive explanation.** If the laws do not care where you are, then there is nothing that can create or destroy momentum based on position alone.

**Grad-level framing.** Continuous symmetries of an action yield conserved currents; in mechanics, spatial translation invariance yields conserved canonical momentum. (see References)

### Assumptions, conventions, and validity domain

- **Dynamics.** $L(x,\dot x,t)$ is continuously differentiable in $(x,\dot x)$ and the trajectory $x(t)$ is twice differentiable.
- **Symmetry.** Spatial translation invariance means $L$ has **no explicit** dependence on $x$: $\partial L/\partial x = 0$.
- **Variational framework.** Euler–Lagrange equations hold for variations with fixed endpoints.

### Symbolic derivation Symmetry → Conserved quantity → Reduced dynamics

We make the “Noether-style” argument explicit at the level of the Euler–Lagrange equation and, briefly, at the action-symmetry level.

### 1 Euler–Lagrange route minimal machinery

Let the action be
$$
S[x]=\int_{t_0}^{t_1} L(x,\dot x,t)\,dt,
$$
with $L$ continuously differentiable. Stationary trajectories satisfy the Euler–Lagrange equation
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot x}\right)-\frac{\partial L}{\partial x}=0.
$$

**Translation invariance hypothesis.** Spatial translation invariance in 1D mechanics means the Lagrangian has no explicit $x$-dependence:
$$
\frac{\partial L}{\partial x}=0.
$$
Substitute into Euler–Lagrange:
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot x}\right)=0.
$$
Define the canonical momentum
$$
p := \frac{\partial L}{\partial \dot x}.
$$
Then $dp/dt=0$, so $p$ is conserved.

### 2 Action-symmetry Noether route one-line version

If the action is invariant under the infinitesimal transformation $x\mapsto x+\varepsilon$ (constant $\varepsilon$), then Noether’s theorem yields a conserved quantity equal to the conjugate momentum $p$. In this 1D setting, the condition of invariance is precisely $\partial L/\partial x=0$, so the Noether statement reduces to the Euler–Lagrange computation above.

**If the assumptions are false, how to make them true.** If $L$ depends explicitly on $x$ (e.g., through a potential $V(x)$), translation symmetry is broken and canonical momentum need not be conserved. You can recover a conserved momentum by enlarging the system so that the “source of the potential” is included as dynamical (closed system), or by identifying the residual symmetry (e.g., discrete translations) that yields a weaker invariant.

### Numerical example

For a free particle, $L=\tfrac12 m\dot x^2$, hence $p=m\dot x$.

Take $m=2.0\ \mathrm{kg}$ and $\dot x=v=3.0\ \mathrm{m/s}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $p=m\dot x\;[\mathrm{kg\,m/s}]$ | $6.0000\times 10^{0}$ | 6.0000 | 6.0000e0 |

### 5 of 5 rigor addendum

#### Proposition cyclic coordinate implies conserved canonical momentum

Let $L(q,\dot q,t)$ be a Lagrangian with $L\in C^2$ in $(q,\dot q)$, and consider action
$$
S[q] = \int_{t_0}^{t_1} L(q,\dot q,t)\,dt
$$
over $C^2$ paths $q(t)$ with fixed endpoints $q(t_0),q(t_1)$.

If coordinate $q_i$ is cyclic, meaning $\partial L/\partial q_i = 0$ everywhere in the domain, then along any Euler–Lagrange solution,
$$
\frac{d}{dt}\left(\frac{\partial L}{\partial \dot q_i}\right)=0,
$$
so the canonical momentum $p_i \equiv \partial L/\partial \dot q_i$ is conserved.

#### Theorem Noether 1-parameter symmetry statement

Suppose the action is invariant under a smooth 1-parameter family of transformations
$$
q(t)\mapsto q_\varepsilon(t)=q(t)+\varepsilon\,\delta q(t)+O(\varepsilon^2),
\qquad t\mapsto t_\varepsilon = t + \varepsilon\,\delta t + O(\varepsilon^2),
$$
in the sense that
$$
\delta L = \varepsilon \frac{dF}{dt}
$$
for some smooth function $F(q,t)$, and boundary variations are compatible with endpoint constraints. Then there exists a conserved quantity
$$
J = \sum_i \frac{\partial L}{\partial \dot q_i}\,\delta q_i - \left( L\,\delta t - F \right),
\qquad \frac{dJ}{dt}=0
$$
along solutions of the Euler–Lagrange equations.

The cyclic-coordinate result above is recovered by choosing $\delta t=0$, $\delta q_i=1$ for a translation in $q_i$, and $F=0$.

#### Proof-obligations checklist

- [x] Specify regularity $L\in C^2$ and path class $q\in C^2$.
- [x] Specify endpoint constraints for the variational problem.
- [x] Identify whether invariance is exact or up to a total derivative term $dF/dt$.
- [x] If invariance is only up to a boundary term, include the corrected conserved quantity.

#### Reproducible computation

```python
# Momentum example
m = 2.0     # kg
v = 3.0     # m/s

p = m * v
print("p = m v [kg·m/s] =", p)
```

#### Primary sources

- Lecture notes on Noether’s theorems and symmetries, PDF.
- MIT OpenCourseWare 8.06 notes on Lagrangians and symmetries, PDF.

---

## P4 VAR: Euler–Lagrange equation for the harmonic oscillator

**Intuitive explanation.** The mass trades kinetic energy and spring potential energy back and forth, producing sinusoidal motion.

**Grad-level framing.** Stationarity of the action $S[x]=\int L(x,\dot x,t)\,dt$ yields Euler–Lagrange equations. (see References)

### Assumptions, conventions, and validity domain

- **Variational setting.** $x(t)$ is twice differentiable on $[t_0,t_1]$; admissible variations $\eta(t)$ satisfy $\eta(t_0)=\eta(t_1)=0$.
- **Model.** $m>0$, $k>0$ are constants; the Lagrangian $L=\tfrac12 m\dot x^2-\tfrac12 kx^2$ is time-independent.
- **Interpretation.** The Euler–Lagrange equation gives the classical equation of motion for stationary action paths.

### Symbolic derivation Variational principle → Euler–Lagrange → Stability

We derive Euler–Lagrange for this specific Lagrangian with explicit endpoint conditions.

### 1 Action functional

Let
$$
L(x,\dot x)=\frac12 m\dot x^2-\frac12 kx^2,
\qquad
S[x]=\int_{t_0}^{t_1}L(x,\dot x)\,dt.
$$
Assume $x$ is twice differentiable and consider variations $x_\epsilon=x+\epsilon\eta$ where $\eta(t_0)=\eta(t_1)=0$.

### 2 First variation and integration by parts

Compute the first variation:
$$
\frac{d}{d\epsilon}S[x_\epsilon]\Big|_{\epsilon=0}
=\int_{t_0}^{t_1}\left(\frac{\partial L}{\partial x}\eta + \frac{\partial L}{\partial \dot x}\dot\eta\right)\,dt.
$$
Here
$$
\frac{\partial L}{\partial x}=-kx,\qquad
\frac{\partial L}{\partial \dot x}=m\dot x.
$$
Thus
$$
\delta S
=\int_{t_0}^{t_1}\left(-kx\,\eta + m\dot x\,\dot\eta\right)\,dt.
$$
Integrate the second term by parts:
$$
\int_{t_0}^{t_1} m\dot x\,\dot\eta\,dt
=\Big[m\dot x\,\eta\Big]_{t_0}^{t_1}
-\int_{t_0}^{t_1} m\ddot x\,\eta\,dt.
$$
The boundary term vanishes because $\eta(t_0)=\eta(t_1)=0$. Therefore
$$
\delta S
=\int_{t_0}^{t_1}\left(-kx - m\ddot x\right)\eta(t)\,dt.
$$

### 3 Fundamental lemma → equation of motion

Because $\eta(t)$ is arbitrary (subject to vanishing endpoints), the fundamental lemma of the calculus of variations implies
$$
m\ddot x + kx = 0.
$$
This is the harmonic oscillator equation with angular frequency $\omega=\sqrt{k/m}$.

**If the assumptions are false, how to make them true.** If non-conservative forces (damping, driving) are present, stationary action for $S=\int L\,dt$ is no longer the correct identity. To incorporate dissipation, introduce a Rayleigh dissipation functional or use the Lagrange–d’Alembert principle; the identity changes from conservative Euler–Lagrange dynamics to forced/dissipative dynamics.

### Numerical example

Take $m=0.20\ \mathrm{kg}$ and $k=8.0\ \mathrm{N/m}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\omega=\sqrt{k/m}\;[\mathrm{rad/s}]$ | $6.3246\times 10^{0}$ | 6.3246 | 6.3246e0 |
| $f=\omega/(2\pi)\;[\mathrm{Hz}]$ | $1.0066\times 10^{0}$ | 1.0066 | 1.0066e0 |

### 5 of 5 rigor addendum

#### Proposition Euler–Lagrange gives the harmonic oscillator equation

Let $L(x,\dot x,t)=\frac{1}{2}m\dot x^2-\frac{1}{2}k x^2$ with $m>0$, $k>0$, and let $x(t)$ be a stationary path of the action with fixed endpoints.

Then $x(t)$ satisfies the Euler–Lagrange equation
$$
m\ddot x + kx = 0.
$$

#### Stability note

Hamilton’s principle yields a *stationary* action, not necessarily a minimum. Physical stability is instead assessed through the dynamics.

For the harmonic oscillator, linearization about equilibrium is exact and yields eigenvalues $\lambda=\pm i\omega$ with $\omega=\sqrt{k/m}$, implying bounded oscillatory motion. In contrast, if the potential were inverted, $V(x)=-\frac{1}{2}k x^2$, then $\lambda=\pm \omega$ and the equilibrium would be dynamically unstable.

Equivalently, the potential energy has $V''(0)=k>0$, so $x=0$ is a stable equilibrium in the energy landscape sense.

#### Error certificate

The derivation is exact within the linear spring and point-mass model class. Model error dominates:

- If the spring has a cubic term $V(x)=\frac12 kx^2+\frac14\beta x^4$, then the first neglected correction produces Duffing-type amplitude dependence. A conservative regime statement is $|\beta x^2| \ll k$.

#### Reproducible computation

```python
import math

# Control knobs
m = 0.20   # kg
k = 8.0    # N/m

omega = math.sqrt(k / m)        # rad/s
f = omega / (2.0 * math.pi)     # Hz

print("omega [rad/s] =", omega)
print("f [Hz] =", f)
```

#### Primary sources

- MIT OpenCourseWare notes on the calculus of variations and Euler–Lagrange equations.
- Classical mechanics lecture notes covering Hamilton’s principle and the harmonic oscillator.

---

## P5 EIG: Normal modes from a 2×2 eigenproblem two masses, three springs

**Intuitive explanation.** Coupled objects have collective ways to wiggle, and each has a characteristic frequency.

**Grad-level framing.** Linearization around equilibrium gives $M\ddot x + Kx=0$; diagonalizing $M^{-1}K$ yields eigenfrequencies and orthogonal modes.

### Assumptions, conventions, and validity domain

- **Linearization.** Small oscillations around equilibrium so Hooke’s law springs are linear and geometry is fixed.
- **Conservative system.** No damping or forcing; masses and springs are time-invariant.
- **Matrix properties.** Mass matrix $M=mI$ is positive definite and stiffness matrix $K$ is symmetric positive definite, enabling real eigenfrequencies.

### Symbolic derivation Eigenproblem → Spectrum → Mode expansion

Two equal masses $m$ connected to walls by springs $k$ and coupled by a spring $k$:

Let $x=[x_1,x_2]^T$. The equations are
$$
m\ddot x_1 = -2k x_1 + k x_2,\qquad
m\ddot x_2 = k x_1 - 2k x_2.
$$
Matrix form:
$$
m\ddot x + k\begin{bmatrix}2&-1\\-1&2\end{bmatrix}x=0.
$$
Try $x(t)=v e^{i\omega t}$:
$$
\left(k\begin{bmatrix}2&-1\\-1&2\end{bmatrix}-m\omega^2 I\right)v=0.
$$
Let $\lambda:=m\omega^2/k$. Then
$$
\det\left(\begin{bmatrix}2&-1\\-1&2\end{bmatrix}-\lambda I\right)=0
\Rightarrow
(2-\lambda)^2-1=0
\Rightarrow
\lambda\in\{1,3\}.
$$
So
$$
\omega_1=\sqrt{\frac{k}{m}},\qquad \omega_2=\sqrt{\frac{3k}{m}}.
$$

**If the assumptions are false, how to make them true.** With strong damping, eigenmodes become complex “quasinormal” modes; you can restore modal decomposition by treating damping as a perturbation (light damping), changing the identity from conservative to weakly dissipative modes.

### Numerical example

Take $m=0.50\ \mathrm{kg}$ and $k=200\ \mathrm{N/m}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\omega_1\;[\mathrm{rad/s}]$ | $2.0000\times 10^{1}$ | 20.0000 | 2.0000e1 |
| $\omega_2\;[\mathrm{rad/s}]$ | $3.4641\times 10^{1}$ | 34.6410 | 3.4641e1 |

### 5 of 5 rigor addendum

#### Generalized eigenproblem statement

For small oscillations of an $n$-degree-of-freedom linear mechanical system with mass matrix $M$ and stiffness matrix $K$, the equations can be written as
$$
M\ddot x + Kx = 0,
$$
with $M$ symmetric positive definite and $K$ symmetric positive semidefinite for passive conservative systems.

Normal modes solve the generalized eigenproblem
$$
K a_i = \omega_i^2 M a_i.
$$

#### Orthonormalization and reconstruction via modal expansion

Because $M$ is positive definite, the eigenvectors can be chosen **$M$-orthonormal**:
$$
a_i^\mathsf{T} M a_j = \delta_{ij}.
$$

Expand the displacement as
$$
x(t) = \sum_{i=1}^n q_i(t)\,a_i.
$$
Substituting into $M\ddot x + Kx = 0$ and left-multiplying by $a_j^\mathsf{T}$ yields decoupled modal coordinates:
$$
\ddot q_j + \omega_j^2 q_j = 0.
$$

Reconstruction from initial conditions is explicit:
$$
q_j(0) = a_j^\mathsf{T} M x(0),
\qquad
\dot q_j(0) = a_j^\mathsf{T} M \dot x(0).
$$

#### Error certificate

The mode expansion is exact within linearized small-oscillation assumptions. Nonlinearity enters when restoring forces are not linear; a practical regime criterion is that geometric or material nonlinear terms remain small compared to the linear stiffness terms.

#### Reproducible computation

```python
import math

# Control knobs from the worked example
m = 0.50    # kg
k = 200.0   # N/m

omega1 = math.sqrt(k / m)
omega2 = math.sqrt(3.0 * k / m)

print("omega1 [rad/s] =", omega1)
print("omega2 [rad/s] =", omega2)

# Mode vectors for the symmetric 2-mass, 3-spring case
a1 = (1.0, 1.0)     # in-phase
a2 = (1.0, -1.0)    # out-of-phase
print("mode shapes a1, a2 =", a1, a2)
```

#### Primary sources

- Lecture notes on normal modes and generalized eigenproblems in vibrations.
- MIT OpenCourseWare materials on eigenvalues, orthogonality, and modal analysis.

---

## P6 PERT: Regular perturbation of $\sqrt{1+\varepsilon}$ with an explicit error check

**Intuitive explanation.** For small tweaks, a function changes almost linearly, and the first few Taylor terms often give an excellent estimate.

**Grad-level framing.** Regular perturbation expands analytic functions in a small parameter and can bound truncation error by the first neglected term, under smoothness assumptions.

### Assumptions, conventions, and validity domain

- **Analyticity region.** $f(\varepsilon)=\sqrt{1+\varepsilon}$ is analytic for $|\varepsilon|<1$ (branch cut at $\varepsilon\le -1$).
- **Error control.** Taylor’s theorem with remainder applies provided $f^{(3)}$ is bounded on the interval between $0$ and $\varepsilon$.
- **Numerics.** The explicit remainder bound is computed using an interval bound on $(1+\xi)^{-5/2}$.

### Symbolic derivation Small parameter → Corrections → Error check

For $|\varepsilon|<1$, the binomial series converges absolutely:
$$
(1+\varepsilon)^{1/2}=\sum_{n=0}^{\infty}\binom{1/2}{n}\varepsilon^n,
\qquad
\binom{1/2}{n}=\frac{(1/2)(1/2-1)\cdots(1/2-n+1)}{n!}.
$$
The first three coefficients are
$$
\binom{1/2}{0}=1,\qquad
\binom{1/2}{1}=\frac12,\qquad
\binom{1/2}{2}=-\frac18,
$$
so the second-order approximation is
$$
\sqrt{1+\varepsilon}=1+\frac12\varepsilon-\frac18\varepsilon^2 + R_2(\varepsilon).
$$

**Explicit remainder bound (Taylor’s theorem).** Let $f(\varepsilon)=\sqrt{1+\varepsilon}$. Then
$$
f^{(3)}(x)=\frac{3}{8}(1+x)^{-5/2}.
$$
Taylor’s theorem about $0$ gives
$$
R_2(\varepsilon)=\frac{f^{(3)}(\xi)}{3!}\,\varepsilon^3
=\frac{1}{16}\,(1+\xi)^{-5/2}\,\varepsilon^3
\quad\text{for some }\xi\text{ between }0\text{ and }\varepsilon.
$$
Hence, for any $\varepsilon\in(-1,1)$,
$$
|R_2(\varepsilon)|
\le
\frac{|\varepsilon|^3}{16}\,
\max_{\xi\in[\min(0,\varepsilon),\,\max(0,\varepsilon)]}(1+\xi)^{-5/2}.
$$
In particular, if $\varepsilon\ge 0$ then $(1+\xi)^{-5/2}\le 1$ on $[0,\varepsilon]$, so
$$
|R_2(\varepsilon)|\le \frac{|\varepsilon|^3}{16}\qquad(\varepsilon\ge 0).
$$
This provides a concrete, checkable truncation-error certificate for the second-order approximation in the positive-$\varepsilon$ regime.

**If the assumptions are false, how to make them true.** If $|\varepsilon|$ is not small (or $\varepsilon\le -1$ where the real square root ceases to exist), then the truncated series is not a controlled approximation. You can (i) compute $\sqrt{1+
\varepsilon}$ exactly, or (ii) reparameterize (e.g., factor out a scale and expand around a different point) so that the new expansion parameter is small; this changes the identity from a low-order asymptotic series to an exact or re-centered approximation.

### Numerical example

Let $\varepsilon=0.04$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\sqrt{1+\varepsilon}\;[-] (true)$ | $1.0198\times 10^{0}$ | 1.0198 | 1.0198e0 |
| $\text{2nd-order approx}\;[-]$ | $1.0198\times 10^{0}$ | 1.0198 | 1.0198e0 |
| $\text{error}\;[-]$ | $-3.9027\times 10^{-6}$ | -0.0000039027 | -3.9027e-6 |
| $\text{relative error}\;[-]$ | $-3.8269\times 10^{-6}$ | -0.0000038269 | -3.8269e-6 |

### 5 of 5 rigor addendum

#### Error certificate template

This pattern is the canonical “certified approximation” move:

1. Choose an analytic function $f$ and a small parameter $\varepsilon$.
2. Expand to a chosen order and write the remainder in a standard form.
3. Bound the remainder on an explicit interval.

In general, if $f$ is $C^{n+1}$ on an interval containing $0$ and $\varepsilon$, then Taylor’s theorem provides
$$
f(\varepsilon) = \sum_{k=0}^n \frac{f^{(k)}(0)}{k!}\varepsilon^k + R_{n+1}(\varepsilon),
\qquad
R_{n+1}(\varepsilon)=\frac{f^{(n+1)}(\xi)}{(n+1)!}\varepsilon^{n+1}
$$
for some $\xi$ between $0$ and $\varepsilon$, and therefore
$$
|R_{n+1}(\varepsilon)| \le \frac{\max_{u\in[0,\varepsilon]}|f^{(n+1)}(u)|}{(n+1)!}|\varepsilon|^{n+1}.
$$

#### Reproducible computation

```python
import math

# Control knobs
eps = 0.04

approx = 1.0 + 0.5 * eps - 0.125 * eps**2
exact = math.sqrt(1.0 + eps)
err = abs(exact - approx)

print("approx =", approx)
print("exact  =", exact)
print("abs error =", err)
```

#### Primary sources

- Standard real analysis or calculus notes on Taylor’s theorem with remainder.

---

## P7 LR: Susceptibility of a driven, damped harmonic oscillator frequency-domain linear response

**Intuitive explanation.** If you shake a spring-mass system near its natural frequency, it responds strongly, and damping sets the peak height.

**Grad-level framing.** Linear response treats forcing as a perturbation and expresses the steady-state response through a complex susceptibility $\chi(\omega)$. (see References)

### Assumptions, conventions, and validity domain

- **Linear time-invariant model.** Constant coefficients $m>0$, $\omega_0>0$, damping ratio $\zeta\ge 0$; forcing is sinusoidal at angular frequency $\omega$.
- **Steady state.** The complex-ansatz solution corresponds to the unique bounded steady-state response after transients decay (for $\zeta>0$).
- **Fourier convention.** $e^{i\omega t}$ time dependence is used for phasors; physical signals are real parts.

### Symbolic derivation ODE → Fourier ansatz → $\chi\omega$

Consider
$$
m\ddot x + 2\zeta m\omega_0 \dot x + m\omega_0^2 x = F_0\cos(\omega t).
$$
Use complex forcing $F_0 e^{i\omega t}$ and seek $x(t)=\Re\{X e^{i\omega t}\}$.
Then $\dot x\mapsto i\omega X e^{i\omega t}$ and $\ddot x\mapsto -\omega^2 X e^{i\omega t}$, giving
$$
\left[m(\omega_0^2-\omega^2)+i(2\zeta m\omega_0\omega)\right]X = F_0.
$$
Define susceptibility
$$
\chi(\omega):=\frac{X}{F_0}=\frac{1}{m(\omega_0^2-\omega^2)+i\,2\zeta m\omega_0\omega}.
$$
Amplitude:
$$
A=|X|=\frac{F_0/m}{\sqrt{(\omega_0^2-\omega^2)^2+(2\zeta\omega_0\omega)^2}}.
$$

**If the assumptions are false, how to make them true.** If response is nonlinear, you can linearize or adopt nonlinear response kernels; that changes the identity from linear susceptibility to nonlinear response functionals.

### Numerical example

Let $m=1.0\ \mathrm{kg}$, $\omega_0=100\ \mathrm{rad/s}$, $\zeta=0.02$, $F_0=1.0\ \mathrm{N}$, and drive at $\omega=90\ \mathrm{rad/s}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $A\;[\mathrm{m}]$ | $5.1712\times 10^{-4}$ | 0.0005 | 5.1712e-4 |
| $A\;[\mathrm{mm}]$ | $5.1712\times 10^{-1}$ | 0.5171 | 5.1712e-1 |

### 5 of 5 rigor addendum

#### Causality and Kramers–Kronig relations for susceptibility

In high-school terms, a causal system cannot respond before it is driven.

In graduate-level language, if the response is causal,
$$
x(t)=\int_{-\infty}^{\infty}\chi(t-t')\,F(t')\,dt',
\qquad
\chi(t)=0\ \text{for}\ t<0,
$$
then the Fourier transform $\chi(\omega)$ extends to a function analytic in the upper half complex $\omega$-plane. As a consequence, the real and imaginary parts are not independent; they satisfy Kramers–Kronig relations, for example
$$
\Re \chi(\omega) = \frac{1}{\pi}\,\mathcal{P}\!\!\int_{-\infty}^{\infty}\frac{\Im\chi(\omega')}{\omega'-\omega}\,d\omega',
\qquad
\Im \chi(\omega) = -\frac{1}{\pi}\,\mathcal{P}\!\!\int_{-\infty}^{\infty}\frac{\Re\chi(\omega')}{\omega'-\omega}\,d\omega',
$$
where $\mathcal{P}$ denotes the Cauchy principal value.

For the damped harmonic oscillator,
$$
\chi(\omega)=\frac{1}{m\left(\omega_0^2-\omega^2-i\gamma\omega\right)},
$$
analyticity holds for $\gamma>0$, and $\Im\chi(\omega)$ is associated with dissipation and absorbed power.

#### Error certificate for linear response

Linear response assumes that the system is well-approximated by a linear, time-invariant model near the operating point. A practical engineering certificate is:

- keep displacement amplitude small enough that nonlinear restoring terms remain negligible,
- keep drive amplitude small enough that damping remains linear,
- and report the operating point and characteristic nonlinearity scale.

#### Reproducible computation

```python
import math

# Control knobs
m = 1.0
omega0 = 100.0
zeta = 0.02
F0 = 1.0
omega = 90.0

gamma = 2.0 * zeta * omega0

den = math.sqrt((omega0**2 - omega**2)**2 + (gamma * omega)**2)
A = F0 / (m * den)

print("gamma =", gamma)
print("denominator magnitude =", den)
print("steady-state amplitude A =", A)
```

#### Primary sources

- Lecture notes on Kramers–Kronig relations and causality for response functions, PDF.
- Classical linear response and susceptibility notes based on the Kubo formalism.

---

## P8 NOISE: Johnson–Nyquist thermal noise over a finite bandwidth

**Intuitive explanation.** Random thermal motion produces a jittery voltage, and wider bandwidth means more jitter gets through.

**Grad-level framing.** Fluctuation–dissipation connects dissipation (resistance) to equilibrium fluctuations (noise). (see References)

### Assumptions, conventions, and validity domain

- **Thermal equilibrium.** The resistor is in equilibrium at temperature $T$ (Kelvin) and is well-modeled as a frequency-independent resistance $R$ over the bandwidth of interest.
- **PSD convention.** **One-sided** voltage-noise PSD $S_V(f)$ is used for real signals: $\langle v_n^2\rangle=\int_0^B S_V(f)\,df$.
- **Classical limit.** The classical formula $S_V(f)=4k_BTR$ requires $hf\ll k_BT$ over the band; otherwise use the quantum (Planck) form given below.

### Symbolic derivation Spectral density → Band-limited RMS

**Classical Johnson–Nyquist result (one-sided PSD convention).** For an ideal resistor $R$ at absolute temperature $T$, the **one-sided** equilibrium voltage-noise PSD is
$$
S_V(f)=4k_BTR\qquad [\mathrm{V^2/Hz}],\quad f\ge 0.
$$
For a measurement bandwidth $B$ (Hz), the mean-square noise voltage is
$$
\langle v_n^2\rangle=\int_{0}^{B} S_V(f)\,df
=\int_{0}^{B}4k_BTR\,df
=4k_BTRB,
$$
and therefore
$$
v_{\mathrm{rms}}=\sqrt{\langle v_n^2\rangle}=\sqrt{4k_BTRB}.
$$

**Two-sided PSD note (conversion).** If instead you use a two-sided PSD $S_V^{(2)}(f)$ defined for $f\in\mathbb{R}$ with
$\langle v_n^2\rangle=\int_{-\infty}^{\infty}S_V^{(2)}(f)\,df$,
then the classical constant is $S_V^{(2)}(f)=2k_BTR$, and integrating over a symmetric band gives the same $4k_BTRB$ result. The difference is purely a convention factor-of-two.

**Quantum (Planck) correction (when $hf \not\ll k_BT$).**
A common symmetrized quantum expression for the two-sided voltage-noise spectrum of a resistor is
$$
S_V^{(2)}(\omega)=2\hbar\omega R\,\coth\!\left(\frac{\hbar\omega}{2k_BT}\right)
\qquad [\mathrm{V^2/(rad/s)}],
$$
with $\omega=2\pi f$. In the classical limit $\hbar\omega\ll k_BT$, $\coth(x)\sim 1/x$ and this reduces to the Johnson–Nyquist constant spectrum. For $hf\gg k_BT$, the spectrum approaches the vacuum (zero-point) fluctuation form $\propto \hbar\omega R$.

**Validity check used implicitly in the worked example.** At the highest frequency in-band, verify $hf_{\max}/(k_BT)\ll 1$; if so, the classical expression is rigorously justified as the leading term of the quantum expression.

**If the assumptions are false, how to make them true.** If $R$ is frequency dependent, replace $R$ by $\mathrm{Re}\{Z(f)\}$ in the fluctuation–dissipation relation; if $hf$ is not negligible compared to $k_BT$, use the quantum spectrum (and ensure your PSD convention matches the chosen formula). These changes shift the identity from classical white noise to impedance-shaped and potentially quantum-limited noise.

### Numerical example

Take $R=50\ \Omega$, $T=300\ \mathrm{K}$, and $B=10\ \mathrm{MHz}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $v_\mathrm{rms}\;[\mathrm{V}]$ | $2.8782\times 10^{-6}$ | 0.0000028782 | 2.8782e-6 |
| $v_\mathrm{rms}\;[\mathrm{\mu V}]$ | $2.8782\times 10^{0}$ | 2.8782 | 2.8782e0 |

### 5 of 5 rigor addendum

#### Measurement chain example with noise figure and referred noise

Suppose a resistor at physical temperature $T$ is connected to an amplifier chain whose input-referred noise can be parameterized by a noise figure $F$ relative to reference temperature $T_0$.

Define the equivalent noise temperature
$$
T_e \equiv (F-1)\,T_0.
$$
Then the available input noise in bandwidth $B$ is effectively
$$
\langle v_n^2\rangle \approx 4k_B R (T+T_e)\,B,
$$
in the classical white-noise limit. This makes the “measurement chain” explicit: physical noise plus receiver-added noise.

If the bandwidth is large enough that $hf$ is not negligible compared to $k_B T$, replace the classical expression with the full Planck–Nyquist form in terms of $\Re Z(f)$, as already stated in the main text.

#### Error certificate

- The “white” approximation requires a flat $\Re Z(f)$ over the measurement band and $hf\ll k_B T$ within the band.
- If a bandpass filter defines the measurement band, then $B$ should be interpreted as the equivalent noise bandwidth of the filter, not merely its 3 dB width.

#### Reproducible computation

```python
import math

kB = 1.380649e-23

# Control knobs
R = 1.0e3         # ohms
T = 300.0         # kelvin
B = 10.0e3        # Hz

# Receiver noise figure model
F = 2.0           # linear noise figure (3 dB)
T0 = 290.0        # kelvin
Te = (F - 1.0) * T0

vn_rms = math.sqrt(4.0 * kB * R * (T + Te) * B)
print("Te [K] =", Te)
print("v_n,rms [V] =", vn_rms)
```

#### Primary sources

- NIST technical note on Johnson noise thermometry and the Nyquist relation, PDF.
- Open lecture notes on Johnson–Nyquist noise and noise temperature concepts, PDF.

---

## P9 IO: Reflection coefficient and return loss from impedance mismatch

**Intuitive explanation.** If the load does not look like the line, some wave energy reflects.

**Grad-level framing.** Boundary matching in 1D waveguides yields complex reflection coefficients; S-parameters are normalized scattering ratios.

### Assumptions, conventions, and validity domain

- **Transmission-line model.** Characteristic impedance $Z_0$ is real and positive (lossless line) unless stated otherwise.
- **Loads.** Load impedance $Z_L$ is linear; for real $Z_L>0$ the reflection magnitude satisfies $|\Gamma|<1$.
- **Steady state.** Sinusoidal steady state is assumed; for broadband signals, apply the formulas frequency-by-frequency.

### Symbolic derivation Boundary matching → $\Gamma$

At the load, $V=V^++V^-$ and $I=(V^+-V^-)/Z_0$. Impose $V=Z_L I$:
$$
V^+ + V^- = Z_L\frac{V^+ - V^-}{Z_0}.
$$
Solve for $\Gamma=V^-/V^+$:
$$
\Gamma=\frac{Z_L-Z_0}{Z_L+Z_0}.
$$
Return loss and standing-wave ratio:
$$
\mathrm{RL}:=-20\log_{10}|\Gamma|,\qquad
\mathrm{VSWR}=\frac{1+|\Gamma|}{1-|\Gamma|}.
$$

**If the assumptions are false, how to make them true.** With loss or dispersion, $\Gamma$ becomes frequency dependent; you can make the simple expression true by evaluating in narrowband and using complex impedances.

### Numerical example

Let $Z_0=50\ \Omega$ and $Z_L=75\ \Omega$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\Gamma\;[-]$ | $2.0000\times 10^{-1}$ | 0.2000 | 2.0000e-1 |
| $\mathrm{VSWR}\;[-]$ | $1.5000\times 10^{0}$ | 1.5000 | 1.5000e0 |
| $\mathrm{RL}\;[\mathrm{dB}]$ | $1.3979\times 10^{1}$ | 13.9794 | 1.3979e1 |

### 5 of 5 rigor addendum

#### Complex characteristic impedance and passivity constraints

In high-school terms, mismatch is “how different the load is from what the line expects.”

In graduate-level terms, for a general transmission line with loss, the characteristic impedance $Z_0$ can be complex. The reflection coefficient at the load is still
$$
\Gamma_L = \frac{Z_L - Z_0}{Z_L + Z_0},
$$
but interpretation changes:

- If the reference impedance $Z_0$ is complex, then the mapping from $\Gamma$ to power reflection is more subtle than $|\Gamma|^2$ unless you explicitly define the reference power waves.
- For a passive load and passive line, physical power constraints imply that reflection does not create net energy; in standard real-$Z_0$ power-wave conventions, this shows up as $|\Gamma|\le 1$.
- Active or non-passive terminations can yield $|\Gamma|>1$ and negative resistance behavior; the “same formula” then describes gain rather than mere reflection.

A monograph-grade workflow therefore pins down:

1. the choice of $Z_0$ and whether it is real or complex,
2. whether $\Gamma$ is defined using voltage waves, power waves, or pseudo-waves,
3. and whether the device is passive, active, or potentially unstable.

#### Reproducible computation

```python
import cmath

# Control knobs
Z0 = 50.0 + 0.0j
ZL = 100.0 + 0.0j

Gamma = (ZL - Z0) / (ZL + Z0)
RL_db = -20.0 * cmath.log10(abs(Gamma)).real

print("Gamma =", Gamma)
print("|Gamma| =", abs(Gamma))
print("Return loss [dB] =", RL_db)

assert abs(Gamma) <= 1.0 + 1e-12
```

#### Primary sources

- Lecture notes on transmission lines, characteristic impedance, and reflection coefficient, PDF.
- Notes on S-parameters and reference impedance choices, PDF.

---

## P10 CIRC: Thévenin equivalent as a constitutive relation and then a load calculation

**Intuitive explanation.** A complicated linear network can be replaced by a simpler “battery plus resistor” that behaves the same at the terminals.

**Grad-level framing.** Any linear one-port has an affine $i$–$v$ relation, therefore it admits a Thévenin representation. (see References)

### Assumptions, conventions, and validity domain

- **One-port linearity.** The network seen at the port is linear (superposition holds) and time-invariant (or analyzed in a fixed frequency domain where impedances are constant).
- **Sources.** Independent sources are well-defined and can be “deactivated” (voltage sources shorted, current sources opened) for resistance extraction.
- **Domain note.** If reactive components exist, $R_{\mathrm{th}}$ generalizes to a complex Thévenin impedance $Z_{\mathrm{th}}(\omega)$.

### Symbolic derivation Linear one-port → affine $i$–$v$ → Thévenin

A rigorous way to state Thévenin equivalence is as a theorem about affine port relations.

**Setup.** Consider any linear one-port network $N$ with a distinguished pair of terminals. Let $v$ be the terminal voltage (positive at the defined “+” terminal) and let $i$ be the terminal current **entering** the “+” terminal.

**Claim (affine port relation).** Under linearity, the $i$–$v$ relation of $N$ is affine:
$$
v = V_{\mathrm{th}} + iR_{\mathrm{th}},
$$
for uniquely determined constants $V_{\mathrm{th}}$ (open-circuit voltage) and $R_{\mathrm{th}}\ge 0$ (Thévenin resistance), provided the network is well-posed (no singular dependent-source pathologies).

**Equivalent sign convention.** If instead one defines $i_{\mathrm{out}}$ as the current **leaving** the “+” terminal into an external load, then $i_{\mathrm{out}}=-i$ and the same relation becomes the familiar
$$
v = V_{\mathrm{th}} - i_{\mathrm{out}}R_{\mathrm{th}}.
$$

**Proof sketch (superposition + resistance definition).**

1. **Open-circuit voltage.** With $i=0$, the terminal voltage is, by definition,
   $$
   V_{\mathrm{th}} := v\big|_{i=0}.
   $$

2. **Decompose by superposition.** By linearity, for an arbitrary port current $i$,
   $$
   v(i) = v(0) + \big(v(i)-v(0)\big)=V_{\mathrm{th}}+\Delta v(i),
   $$
   where $\Delta v(i)$ is the incremental port voltage produced by the port current with **all independent internal sources set to zero**.

3. **Source-deactivated input resistance.** In the source-deactivated network, the port is a linear passive (or, more generally, linear) one-port. At DC it has an input resistance $R_{\mathrm{th}}$ such that
   $$
   \Delta v(i)= iR_{\mathrm{th}}.
   $$
   (At frequency $\omega$, replace $R_{\mathrm{th}}$ with the complex input impedance $Z_{\mathrm{th}}(\omega)$ and interpret $v,i$ as phasors.)

Combining yields $v = V_{\mathrm{th}} + iR_{\mathrm{th}}$, i.e., the Thévenin equivalent of a voltage source $V_{\mathrm{th}}$ in series with a resistor $R_{\mathrm{th}}$.

**Uniqueness.** If $v=V_1+iR_1=V_2+iR_2$ for all $i$, then setting $i=0$ gives $V_1=V_2$, and comparing slopes gives $R_1=R_2$.

**If the assumptions are false, how to make them true.** If the network is nonlinear, a global Thévenin equivalent does not exist; linearize about an operating point to obtain a **small-signal** Thévenin model, which changes the identity from global equivalence to local (incremental) equivalence. If the network is dynamic, use $Z_{\mathrm{th}}(\omega)$ rather than a scalar $R_{\mathrm{th}}$.

### Numerical example

Circuit: $V_s=12\ \mathrm{V}$, $R_1=2\ \mathrm{k\Omega}$ in series with $R_2=3\ \mathrm{k\Omega}$ to ground; output node loaded by $R_L=1\ \mathrm{k\Omega}$.

1) Open-circuit (Thévenin) voltage:
$$
V_\mathrm{th}=V_s\frac{R_2}{R_1+R_2}.
$$
2) Thévenin resistance:
$$
R_\mathrm{th}=R_1\parallel R_2.
$$
3) Loaded output:
$$
V_\mathrm{out}=V_\mathrm{th}\frac{R_L}{R_\mathrm{th}+R_L}.
$$

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $V_\mathrm{th}\;[\mathrm{V}]$ | $7.2000\times 10^{0}$ | 7.2000 | 7.2000e0 |
| $R_\mathrm{th}\;[\Omega]$ | $1.2000\times 10^{3}$ | 1,200.0000 | 1.2000e3 |
| $V_\mathrm{out}\;[\mathrm{V}]$ | $3.2727\times 10^{0}$ | 3.2727 | 3.2727e0 |

### 5 of 5 rigor addendum

#### Theorem Thévenin form as an affine port relation

Let a one-port be **linear** at a pair of terminals, meaning the terminal voltage $v$ and current $i$ satisfy an affine relation
$$
v = v_\mathrm{oc} - Z_\mathrm{th}(\omega)\,i
$$
in the frequency domain, or $v = v_\mathrm{oc} - R_\mathrm{th}\,i$ in the direct-current limit. Then the one-port is equivalent, at that port, to an ideal source $V_\mathrm{th}$ in series with $Z_\mathrm{th}$.

This equivalence is a statement about **port behavior**, not about internal structure.

#### Dependent sources and the test-source rule

If dependent sources are present, “turn off independent sources and compute resistance” is not sufficient by itself.

A robust, always-correct method is:

1. Zero all independent sources.
2. Apply a test voltage $V_\mathrm{test}$ at the port and compute the resulting test current $I_\mathrm{test}$.
3. Define $Z_\mathrm{th} = V_\mathrm{test}/I_\mathrm{test}$.

This method works for direct current, for phasor-domain alternating current, and for any linear time-invariant one-port.

#### Error certificate

Equivalence holds within the linear regime. If the port is nonlinear, Thévenin becomes a local linearization around an operating point:
$$
v \approx v_0 + \left.\frac{\partial v}{\partial i}\right|_{i_0}(i-i_0),
$$
and the “Thévenin resistance” becomes a small-signal differential resistance.

#### Reproducible computation

```python
# Voltage divider Thevenin example
Vs = 12.0
R1 = 2.0e3
R2 = 3.0e3

Vth = Vs * R2 / (R1 + R2)
Rth = (R1 * R2) / (R1 + R2)

RL = 1.0e3
IL = Vth / (Rth + RL)
VL = IL * RL

print("Vth [V] =", Vth)
print("Rth [ohm] =", Rth)
print("Load current [A] =", IL)
print("Load voltage [V] =", VL)
```

#### Primary sources

- Open circuits notes on Thévenin and Norton equivalence in the frequency domain, PDF.
- University course notes emphasizing the test-source rule for dependent sources, PDF.

---

## P11 DDP: From drift–diffusion to the Shockley diode equation quasi-neutral limit

**Intuitive explanation.** Forward bias injects carriers, so current rises rapidly, roughly exponentially with voltage.

**Grad-level framing.** Under quasi-equilibrium, low-level injection, and quasi-neutral regions, minority-carrier diffusion produces an exponential I–V law. (see References)

### Assumptions, conventions, and validity domain

- **Junction model.** Abrupt 1D $p\text{–}n$ junction with uniform cross-section area $A$; quasi-neutral regions exist on each side.
- **Regime.** Steady state, low-level injection, negligible electric field in quasi-neutral regions, and negligible recombination in the depletion region (ideal Shockley regime).
- **Boundary conditions.** Quasi-equilibrium at depletion edges gives minority concentrations $n_p(0)=n_{p0}e^{V/V_T}$ and $p_n(0)=p_{n0}e^{V/V_T}$, where $V_T=k_BT/q$.
- **Transport parameters.** Constant diffusion coefficients $D_n,D_p$ and lifetimes $\tau_n,\tau_p$ define diffusion lengths $L_n=\sqrt{D_n\tau_n}$, $L_p=\sqrt{D_p\tau_p}$.

### Symbolic derivation Assumptions → diffusion equation → boundary conditions → I–V

We derive the ideal Shockley diode equation from the steady-state minority-carrier diffusion equations in the quasi-neutral regions.

### 1 Governing diffusion equations in quasi-neutral regions

Let $x$ measure distance away from the depletion edge into each quasi-neutral region, with $x=0$ at the depletion boundary.

- In the $p$-type quasi-neutral region, the **minority electrons** have concentration $n_p(x)$. Define the excess minority concentration
$$
\Delta n_p(x):=n_p(x)-n_{p0},
$$
where $n_{p0}$ is the equilibrium minority electron concentration in the $p$-region.

Under steady state, low-level injection, and negligible electric field in the quasi-neutral region, the minority electron continuity equation reduces to
$$
D_n \frac{d^2 \Delta n_p}{dx^2}-\frac{\Delta n_p}{\tau_n}=0.
$$
Define the electron diffusion length $L_n:=\sqrt{D_n\tau_n}$. Then the ODE is
$$
\frac{d^2 \Delta n_p}{dx^2}-\frac{\Delta n_p}{L_n^2}=0.
$$
The bounded solution satisfying $\Delta n_p(x)\to 0$ as $x\to+\infty$ is
$$
\Delta n_p(x)=\Delta n_p(0)\,e^{-x/L_n}.
$$

- Similarly, in the $n$-type quasi-neutral region, the **minority holes** have concentration $p_n(x)$ with excess $\Delta p_n(x):=p_n(x)-p_{n0}$. Under the same regime,
$$
D_p \frac{d^2 \Delta p_n}{dx^2}-\frac{\Delta p_n}{\tau_p}=0,
\quad
L_p:=\sqrt{D_p\tau_p},
$$
so the bounded solution is
$$
\Delta p_n(x)=\Delta p_n(0)\,e^{-x/L_p}.
$$

### 2 Boundary conditions at the depletion edges quasi-equilibrium

In the ideal Shockley regime, the depletion region is assumed to be in quasi-equilibrium under applied bias $V$. This implies that the minority carrier concentrations at the depletion edges satisfy
$$
n_p(0)=n_{p0}\,e^{V/V_T},
\qquad
p_n(0)=p_{n0}\,e^{V/V_T},
\qquad
V_T:=\frac{k_BT}{q}.
$$
Therefore the excess boundary values are
$$
\Delta n_p(0)=n_{p0}\big(e^{V/V_T}-1\big),
\qquad
\Delta p_n(0)=p_{n0}\big(e^{V/V_T}-1\big).
$$

### 3 Diffusion currents at the depletion edges

Because the electric field is negligible in the quasi-neutral regions, minority carrier currents are diffusion-dominated:

- Electron diffusion current density in the $p$-region:
$$
J_n(x)= qD_n\frac{dn_p}{dx}
= qD_n\frac{d\Delta n_p}{dx}.
$$
Using $\Delta n_p(x)=\Delta n_p(0)e^{-x/L_n}$,
$$
\left.\frac{d\Delta n_p}{dx}\right|_{x=0}=-\frac{\Delta n_p(0)}{L_n},
$$
so
$$
J_n(0)= -qD_n\frac{\Delta n_p(0)}{L_n}.
$$
The magnitude of electron current injected across the depletion region is $I_n = A|J_n(0)|$, hence
$$
I_n = A\,qD_n\frac{n_{p0}}{L_n}\big(e^{V/V_T}-1\big).
$$

- Hole diffusion current density in the $n$-region:
$$
J_p(x)= -qD_p\frac{dp_n}{dx}
= -qD_p\frac{d\Delta p_n}{dx}.
$$
With $\Delta p_n(x)=\Delta p_n(0)e^{-x/L_p}$,
$$
\left.\frac{d\Delta p_n}{dx}\right|_{x=0}=-\frac{\Delta p_n(0)}{L_p},
$$
so
$$
J_p(0)= qD_p\frac{\Delta p_n(0)}{L_p}.
$$
Thus
$$
I_p = A\,qD_p\frac{p_{n0}}{L_p}\big(e^{V/V_T}-1\big).
$$

### 4 Total diode current and the saturation current

The total current is the sum of electron and hole components:
$$
I = I_n + I_p
= A q\left(\frac{D_n n_{p0}}{L_n}+\frac{D_p p_{n0}}{L_p}\right)\big(e^{V/V_T}-1\big).
$$
Define the saturation current
$$
I_s := A q\left(\frac{D_n n_{p0}}{L_n}+\frac{D_p p_{n0}}{L_p}\right),
$$
giving the ideal Shockley diode equation:
$$
I = I_s\left(e^{V/V_T}-1\right).
$$

### 5 Where the ideality factor $n$ comes from model extension

If depletion-region recombination, high-level injection, or series resistance are significant, the ideal model is modified. A common empirical generalization is
$$
I = I_s\left(e^{V/(nV_T)}-1\right),
$$
with $n\approx 1$ for diffusion-dominated current and $n\approx 2$ when depletion-region recombination dominates; series resistance introduces the implicit replacement $V\mapsto V-IR_s$.

**If the assumptions are false, how to make them true.** If depletion-region recombination dominates, include a recombination current term (often yielding an effective ideality factor $n pprox 2$); if series resistance is non-negligible, replace $V$ by $V-IR_s$. High-level injection, mobility dependence, and field-dependent transport require returning to the full drift–diffusion–Poisson system; these modifications change the identity from the ideal Shockley diode to a composite device model.

### Numerical example

Let $I_s=1.0\times 10^{-12}\ \mathrm{A}$, $n=1.8$, $T=300\ \mathrm{K}$, and $V=0.70\ \mathrm{V}$:
$$
I = I_s\left(\exp\left(\frac{qV}{n k_B T}\right)-1\right).
$$

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $I\;[\mathrm{A}]$ | $3.4123\times 10^{-6}$ | 0.0000034123 | 3.4123e-6 |
| $I\;[\mathrm{mA}]$ | $3.4123\times 10^{-3}$ | 0.0034 | 3.4123e-3 |

### 5 of 5 rigor addendum

#### Link back to the full drift–diffusion–Poisson system

The Shockley diode law is not a primitive law; it is a reduced constitutive relation derived from a more detailed transport model.

A standard 1D steady-state drift–diffusion–Poisson closure can be written as:

- Drift–diffusion currents
$$
J_n = q\mu_n n E + q D_n \frac{dn}{dx},
\qquad
J_p = q\mu_p p E - q D_p \frac{dp}{dx}.
$$

- Continuity with recombination
$$
\frac{dJ_n}{dx} = qR,
\qquad
\frac{dJ_p}{dx} = -qR.
$$

- Poisson equation
$$
\frac{dE}{dx} = \frac{q}{\varepsilon}\left(p-n+N_D^+ - N_A^-\right),
\qquad
E = -\frac{d\phi}{dx}.
$$

The Shockley form emerges after a sequence of regime reductions:

1. **Depletion approximation:** a narrow region carries most electric field and most potential drop.
2. **Quasi-neutral regions:** away from the depletion region, charge neutrality holds and $E$ is weak.
3. **Low-level injection and steady state:** minority carrier transport is approximately linear, with exponential boundary conditions set by the applied bias.
4. **Boundary-layer matching:** the depletion region provides boundary conditions for minority carrier diffusion equations in the neutral regions.

In that sense, the diode equation is a matched-asymptotics or boundary-layer reduction: quasi-neutral diffusion solutions matched through a thin depletion layer.

#### Error certificate

The classic ideal Shockley law
$$
I = I_S\left(e^{qV/(nk_BT)}-1\right)
$$
assumes, among other conditions:

- low-level injection,
- negligible series resistance,
- negligible high-field mobility degradation,
- recombination consistent with an ideality factor $n$ (often $n=1$ diffusion-limited, $n=2$ recombination-dominated).

Model error becomes significant when series resistance causes a measurable voltage drop, or when high injection invalidates the exponential minority carrier boundary condition.

#### Reproducible computation

```python
import math

q = 1.602176634e-19
kB = 1.380649e-23

# Control knobs
Is = 1e-12         # A
T = 300.0          # K
n = 1.0            # ideality factor
V = 0.70           # V

I = Is * (math.exp(q * V / (n * kB * T)) - 1.0)
print("I [A] =", I)
```

#### Primary sources

- Open lecture notes deriving the diode equation from drift–diffusion and the depletion approximation, PDF.
- Semiconductor device physics notes that explicitly state the quasi-neutral and boundary-layer steps.

---

## P12 BAND: 3D parabolic-band DOS → effective density of states → carrier density

**Intuitive explanation.** More available quantum states near the conduction band means more places electrons can go, and temperature helps them climb into those states.

**Grad-level framing.** For a parabolic dispersion, 3D density of states scales as $\sqrt{E-E_c}$; integrating DOS against a Boltzmann factor yields the effective density of states $N_c$.

### Assumptions, conventions, and validity domain

- **Band model.** Single isotropic parabolic conduction band with effective mass $m^*$ and dispersion $E(k)=E_c+\hbar^2k^2/(2m^*)$.
- **Counting of states.** Periodic boundary conditions in a large cubic box, with spin degeneracy $g_s=2$; additional valley degeneracy $g_v$ is not included unless stated.
- **Statistics.** Non-degenerate (Maxwell–Boltzmann) limit $E_c-E_F\gg k_BT$, enabling $f(E)\approx e^{-(E-E_F)/k_BT}$.

### Symbolic derivation Parabolic band → DOS → $N_c$

Assume
$$
E(k)=E_c+\frac{\hbar^2 k^2}{2m^*}.
$$
States with magnitude $\le k$ in volume $V$ (including spin):
$$
N(k)=2\cdot \frac{V}{(2\pi)^3}\cdot \frac{4\pi k^3}{3}.
$$
Differentiate with respect to energy to get DOS per unit volume:
$$
g(E)=\frac{1}{V}\frac{dN}{dE}
=\frac{1}{2\pi^2}\left(\frac{2m^*}{\hbar^2}\right)^{3/2}\sqrt{E-E_c}\quad [E\ge E_c].
$$
In the non-degenerate limit,
$$
n=\int_{E_c}^{\infty} g(E)\,e^{-(E-E_F)/(k_BT)}\,dE
=N_c\,e^{-(E_c-E_F)/(k_BT)},
$$
with
$$
N_c := 2\left(\frac{2\pi m^* k_B T}{h^2}\right)^{3/2}.
$$

**If the assumptions are false, how to make them true.** If the carrier gas is degenerate, replace Boltzmann by Fermi–Dirac; that changes the identity from a simple exponential law to Fermi–Dirac integrals.

### Numerical example

Take $m^*=1.08\,m_0$, $T=300\ \mathrm{K}$, and then compute $n$ for $E_c-E_F=0.2\ \mathrm{eV}$:
$$
n = N_c\exp\left(-\frac{E_c-E_F}{k_BT}\right).
$$

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $N_c\;[\mathrm{cm^{-3}}]$ | $2.8165\times 10^{19}$ | 28,164,862,973,567,410,176.0000 | 2.8165e19 |
| $k_BT\;[\mathrm{eV}]$ | $2.5852\times 10^{-2}$ | 0.0259 | 2.5852e-2 |
| $n\;[\mathrm{cm^{-3}}] (E_c-E_F=0.2\ \mathrm{eV})$ | $1.2299\times 10^{16}$ | 12,298,595,536,304,824.0000 | 1.2299e16 |

### 5 of 5 rigor addendum

#### Fermi–Dirac integral form and degeneracy threshold

The main text uses the Maxwell–Boltzmann approximation, which is accurate only in the nondegenerate regime.

The more general electron density in a 3D parabolic band is
$$
n = N_C\,F_{1/2}(\eta),
\qquad
\eta \equiv \frac{E_F - E_C}{k_BT},
$$
where $F_{1/2}$ is the complete Fermi–Dirac integral of order $1/2$.

In the nondegenerate limit $\eta \ll -1$,
$$
F_{1/2}(\eta) \approx e^{\eta},
$$
which recovers the Maxwell–Boltzmann form used in the main derivation.

A practical degeneracy threshold criterion is one of the following equivalent statements:

- $\eta \gtrsim -2$ indicates that Fermi–Dirac corrections may be non-negligible.
- $n \gtrsim 0.1\,N_C$ indicates that the Maxwell–Boltzmann approximation is not quantitatively tight.

#### Error certificate

When using Maxwell–Boltzmann, a coarse quantitative certificate can be stated as:

- If $\eta \le -3$, then $F_{1/2}(\eta)$ is within a few percent of $e^\eta$.
- If $\eta > -2$, use the full Fermi–Dirac integral or a standard approximation for $F_{1/2}$.

#### Reproducible computation

```python
# Degeneracy threshold example using the criterion n / Nc
n = 1.0e23   # m^-3, control knob
Nc = 2.8e25  # m^-3, example magnitude for Si at 300 K, order-of-magnitude only

ratio = n / Nc
print("n/Nc =", ratio)

if ratio < 1e-2:
    print("strongly nondegenerate")
elif ratio < 1e-1:
    print("likely nondegenerate but check")
else:
    print("degenerate or near-degenerate: use Fermi–Dirac")
```

#### Primary sources

- Open notes on Fermi–Dirac integrals and semiconductor carrier statistics, PDF.
- Semiconductor statistics references that define $N_C$, $N_V$, and the $F_{1/2}$ mapping.

---

## P13 SC: Josephson junction relations phase/flux dynamics → frequency–voltage conversion

**Intuitive explanation.** A Josephson junction behaves like a lossless nonlinear inductor: the current depends sinusoidally on the superconducting phase difference, and a constant voltage makes that phase advance steadily in time, producing an oscillation.

**Grad-level framing.** The Josephson relations follow from gauge invariance of the condensate order parameter and yield a metrologically exact proportionality between DC voltage and AC frequency. In superconducting circuit quantization, the node-flux $\Phi$ and node-charge $Q$ are canonically conjugate, satisfying $[\hat{\Phi},\hat{Q}]=i\hbar$, which enforces the uncertainty relation $\Delta \Phi\,\Delta Q\ge \hbar/2$.

### Assumptions, conventions, and validity domain

- **Weak-link regime.** A superconducting weak link supports a well-defined gauge-invariant phase difference $\delta\in\mathbb{R}/2\pi\mathbb{Z}$ across the junction, and a critical current $I_c>0$.
- **Voltage convention.** $V$ denotes the voltage across the junction (positive in the direction of the defined phase drop).
- **Ideal element vs. environment.** The *bare* Josephson element is lossless; realistic junction dynamics in a circuit require shunt capacitance and dissipation (e.g., RCSJ), or a linear embedding network (black-box quantization).
- **Flux quantum.** $\Phi_0 := h/(2e)$ is the superconducting flux quantum.

### Symbolic derivation Josephson relations → frequency–voltage constant → energy and inductance

#### 1 Josephson current–phase relation DC Josephson effect

The supercurrent is
$$
I(\delta)=I_c\sin\delta.
$$

Equivalently, in terms of a branch flux variable $\Phi$ one may identify the phase as $\delta = 2\pi \Phi/\Phi_0$ (mod $2\pi$), which yields the nonlinear inductive constitutive law
$$
I(\Phi)=I_c\sin\!\left(\frac{2\pi}{\Phi_0}\Phi\right).
$$

#### 2 Josephson phase–voltage relation AC Josephson effect

The phase evolves according to
$$
\frac{d\delta}{dt}=\frac{2e}{\hbar}V=\frac{2\pi}{\Phi_0}V.
$$
For constant voltage $V(t)=V$:
$$
\delta(t)=\delta(0)+\frac{2eV}{\hbar}t.
$$
Therefore, the supercurrent $I(t)=I_c\sin\delta(t)$ is periodic with Josephson frequency
$$
f_J=\frac{1}{2\pi}\frac{d\delta}{dt}=\frac{2e}{h}V=:K_J V,
$$
where $K_J=2e/h$ is the Josephson constant.

#### 3 Josephson energy and small-signal inductance

A conservative element admits a potential energy $U(\delta)$ such that $V=(\Phi_0/2\pi)\dot{\delta}$ and $P=VI=\dot{U}$ up to sign. Using $I=I_c\sin\delta$ gives
$$
U_J(\delta)=-E_J\cos\delta,\qquad E_J=\frac{\Phi_0 I_c}{2\pi}=\frac{\hbar I_c}{2e}.
$$

Linearizing around a bias point $\delta_0$ gives the incremental inductance
$$
L_J(\delta_0)=\left(\frac{dI}{d\Phi}\right)^{-1}_{\Phi_0\delta_0/(2\pi)}
=\frac{\Phi_0}{2\pi I_c\cos\delta_0},
$$
so near $\delta_0=0$ one has $L_J\approx \Phi_0/(2\pi I_c)$.

#### 4 Minimal dynamical completion: the RCSJ equation one common closure

Including a shunt capacitance $C$ and resistance $R$ (parallel to the Josephson element) and a bias current $I_b(t)$ yields
$$
I_b(t)=I_c\sin\delta(t)+\frac{V(t)}{R}+C\frac{dV}{dt},
\qquad
V(t)=\frac{\Phi_0}{2\pi}\frac{d\delta}{dt}.
$$
Eliminating $V$ yields the nonlinear second-order phase equation
$$
C\left(\frac{\Phi_0}{2\pi}\right)\ddot{\delta}
+\frac{1}{R}\left(\frac{\Phi_0}{2\pi}\right)\dot{\delta}
+I_c\sin\delta
=I_b(t).
$$

**If the assumptions are false, how to make them true.** If phase is not well-defined (strong quasiparticle poisoning, strong dissipation, or large-amplitude phase slips), then the Josephson element is not accurately modeled by a single $\delta$ degree of freedom. To restore a controlled model, either (i) include additional microscopic degrees of freedom (e.g., quasiparticles), or (ii) work in an experimentally validated effective circuit model with parameters fit to spectroscopy; the identity shifts from an ideal single-variable Josephson element to a multi-mode open quantum system.

### Numerical example

Take a constant junction voltage $V=100\ \mu\mathrm{V}=1.0000\times 10^{-4}\ \mathrm{V}$ and compute $f_J=K_J V$ with $K_J=2e/h$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $K_J=2e/h\;[\mathrm{Hz/V}]$ | $4.8360\times 10^{14}$ | 483,597,848,416,983.6000 | 4.8360e14 |
| $f_J\;[\mathrm{Hz}]$ | $4.8360\times 10^{10}$ | 48,359,784,841.6984 | 4.8360e10 |
| $f_J\;[\mathrm{GHz}]$ | $4.8360\times 10^{1}$ | 48.3598 | 4.8360e1 |

### 5 of 5 rigor addendum

#### Gauge-invariant superconducting phase difference

The physically meaningful Josephson phase difference is not merely a subtraction of two phases; it is gauge invariant.

Define
$$
\delta \equiv \phi_1 - \phi_2 - \frac{2\pi}{\Phi_0}\int_{1}^{2} \mathbf{A}\cdot d\mathbf{l},
\qquad
\Phi_0 \equiv \frac{h}{2e}.
$$
This combination is invariant under $\phi\mapsto \phi + \frac{2\pi}{\Phi_0}\Lambda$ and $\mathbf{A}\mapsto \mathbf{A}+\nabla\Lambda$.

The Josephson relations are then expressed in terms of $\delta$:
$$
I = I_c \sin\delta,
\qquad
\frac{d\delta}{dt} = \frac{2e}{\hbar}V.
$$

#### Environment modeling via the RCSJ equation

A realistic junction is rarely isolated; it is embedded in an electromagnetic environment. A standard closure is the Resistively and Capacitively Shunted Junction model, which yields
$$
C\left(\frac{\hbar}{2e}\right)\ddot\delta + \frac{1}{R}\left(\frac{\hbar}{2e}\right)\dot\delta + I_c\sin\delta = I_\mathrm{bias} + I_\mathrm{noise},
$$
so phase dynamics, dissipation, and noise are explicit and auditable.

#### Reproducible computation

```python
import math

# Josephson frequency–voltage conversion
e = 1.602176634e-19
h = 6.62607015e-34

# Control knobs
V = 1e-6   # volts

f = (2.0 * e / h) * V  # Hz
print("Josephson frequency f [Hz] =", f)
```

#### Primary sources

- NIST Josephson effect references and Josephson voltage standards materials.
- Open superconducting circuits lecture notes deriving the gauge-invariant phase and the RCSJ model.

---

## P14 MAG: LLG precession frequency in a uniform field small-angle limit

**Intuitive explanation.** A magnetic moment in a field precesses, like a spinning top.

**Grad-level framing.** Linearized Landau–Lifshitz–Gilbert dynamics yield a precession frequency set by the gyromagnetic ratio and effective field. (see References)

### Assumptions, conventions, and validity domain

- **Magnetization model.** Uniform macrospin magnetization $\mathbf{M}(t)$ with constant magnitude $|\mathbf{M}|=M_s$.
- **Dynamics.** Landau–Lifshitz–Gilbert (LLG) equation with Gilbert damping constant $\alpha\ge 0$; the stated frequency is the small-angle precession around a constant $\mathbf{H}_{\mathrm{eff}}$.
- **Sign convention.** $\gamma>0$ denotes the magnitude of the gyromagnetic ratio; the precession sense is set by the cross product.

### Symbolic derivation Effective field → LLG → precession

Start from the Landau–Lifshitz–Gilbert (LLG) equation in Gilbert form:
$$
\frac{d\mathbf{M}}{dt}=-\gamma\,\mathbf{M}\times \mathbf{H}_{\mathrm{eff}}
+\frac{\alpha}{M_s}\,\mathbf{M}\times\frac{d\mathbf{M}}{dt},
$$
where $\gamma>0$ is the gyromagnetic ratio magnitude, $M_s=|\mathbf{M}|$ is the saturation magnetization, and $\alpha\ge 0$ is the (dimensionless) Gilbert damping constant.

### Small-angle, uniform-field linearization

Assume $\mathbf{H}_{\mathrm{eff}}=H\,\hat z$ is constant and $\mathbf{M}$ is close to $+M_s\hat z$. Write the transverse magnetization $\mathbf{m}_\perp=(M_x,M_y)$ with $|\mathbf{m}_\perp|\ll M_s$. To leading order, the dynamics of the complex transverse component
$$
m_+(t):=M_x(t)+iM_y(t)
$$
obeys the linear ODE
$$
(1+i\alpha)\,\frac{dm_+}{dt}= i\gamma H\, m_+.
$$
Therefore
$$
\frac{dm_+}{dt}
=\frac{i\gamma H}{1+i\alpha}\,m_+
=\left(\frac{i\gamma H}{1+\alpha^2}\right)m_+ - \left(\frac{\alpha\gamma H}{1+\alpha^2}\right)m_+.
$$
Integrating gives
$$
m_+(t)=m_+(0)\exp\!\left(-\frac{\alpha\gamma H}{1+\alpha^2}t\right)\,
\exp\!\left(i\frac{\gamma H}{1+\alpha^2}t\right).
$$

### Precession frequency and decay rate

Hence the **precession angular frequency** is
$$
\omega = \frac{\gamma H}{1+\alpha^2},
$$
and the transverse amplitude decays with rate
$$
\Gamma = \frac{\alpha\gamma H}{1+\alpha^2}.
$$
In the weak-damping regime $\alpha\ll 1$, these reduce to the commonly used approximations
$$
\omega \approx \gamma H,\qquad \Gamma \approx \alpha\gamma H.
$$

**If the assumptions are false, how to make them true.** If $\mathbf{H}_{\mathrm{eff}}$ includes anisotropy and demagnetizing fields, the resonance frequency is not simply $\gamma H$; use a Kittel-type effective-field formulation (or full micromagnetic linearization) to obtain the correct mode frequency and linewidth. This changes the identity from uniform-field Larmor precession to ferromagnetic resonance in a structured energy landscape.

### Numerical example

Using $\gamma/(2\pi)\approx 28\ \mathrm{GHz/T}$ and $|\mathbf{H}_\mathrm{eff}|=0.05\ \mathrm{T}$:

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $f\;[\mathrm{Hz}]$ | $1.4000\times 10^{9}$ | 1,400,000,000.0000 | 1.4000e9 |
| $f\;[\mathrm{GHz}]$ | $1.4000\times 10^{0}$ | 1.4000 | 1.4000e0 |

### 5 of 5 rigor addendum

#### Kittel formula connection for ferromagnetic resonance

The small-angle linearized Landau–Lifshitz–Gilbert dynamics yields precession, but experimentally one often reports resonance via Kittel-type formulas.

For a uniformly magnetized ellipsoid with demagnetizing factors $N_x,N_y,N_z$ and external field $H$, the ferromagnetic resonance frequency can be written in the form
$$
\omega = \gamma \sqrt{(H + H_k + (N_y-N_z)M_s)(H + H_k + (N_x-N_z)M_s)},
$$
with geometry encoded through the demagnetizing factors and $M_s$.

Special cases yield familiar thin-film expressions, such as
$$
\omega = \gamma\sqrt{(H+H_k)(H+H_k+M_\mathrm{eff})},
$$
which is a Kittel formula for in-plane geometries.

#### Demagnetizing geometry example

For a very thin film magnetized in-plane, one typically has $N_z\approx 1$ and $N_x\approx N_y\approx 0$, so shape anisotropy strongly shifts the resonance relative to the vacuum-field $\omega=\gamma H$ result.

A monograph-grade workflow therefore states the geometry and demagnetizing assumption explicitly.

#### Error certificate

Linearization requires small transverse components $m_\perp \ll M_s$. A practical quantitative certificate is to keep the cone angle small, e.g., $\theta\lesssim 5^\circ$, depending on anisotropy and driving strength.

#### Reproducible computation

```python
import math

# Control knobs
gamma = 1.760e11   # rad/s/T, magnitude
B = 0.10           # tesla

omega = gamma * B
f = omega / (2.0 * math.pi)

print("omega [rad/s] =", omega)
print("f [Hz] =", f)
```

#### Primary sources

- Open lecture notes on Landau–Lifshitz–Gilbert dynamics and ferromagnetic resonance.
- Materials discussing the Kittel formula and demagnetizing factors in common geometries.

---

## P15 SPIN: Spin Hall angle as a conversion factor charge current → spin current

**Intuitive explanation.** In some materials, a charge current can generate a transverse spin flow.

**Grad-level framing.** The spin Hall angle $\theta_\mathrm{SH}$ parameterizes spin–orbit conversion between charge current density and spin angular-momentum current density. (see References)

### Assumptions, conventions, and validity domain

- **Geometry.** Specify a conventional spin Hall geometry: charge current density $\mathbf{J}_c$ along $+\hat x$, spin current flowing along $+\hat y$ with spin polarization along $+\hat z$.
- **Tensor nature.** Spin current is a rank-2 object $J_{s,i}^{\ \alpha}$ (flow direction $i$, spin polarization $\alpha$).
- **Normalization.** $J_s$ is reported as **angular-momentum current density** (units J/m$^2$); equivalently, $(2e/\hbar)J_s$ has units A/m$^2$.
- **Material regime.** Bulk spin Hall effect in a homogeneous normal metal, ignoring spin backflow and interface transparency effects (device-level corrections noted separately).

### Symbolic derivation Definition → conversion law

We make the conversion law precise by fixing geometry and normalization.

### 1 Definitions: charge-current density and spin-current tensor

- Charge current density $\mathbf{J}_c$ has units A/m$^2$ and represents charge flow.
- Spin current is a **tensor** $J_{s,i}^{\ \alpha}$, where:
  - $i\in\{x,y,z\}$ indexes the spatial direction of **flow**,
  - $\alpha\in\{x,y,z\}$ indexes the direction of **spin polarization** carried by that flow.

A common normalization for spin current is angular-momentum flux per area, so $J_{s,i}^{\ \alpha}$ has units
$$
\frac{\text{angular momentum}}{\text{time}\cdot \text{area}}
=\frac{\mathrm{J\cdot s}}{\mathrm{s\cdot m^2}}
=\mathrm{J/m^2}.
$$
Under this normalization, multiplying by $(2e/\hbar)$ converts $J_s$ into an “equivalent” charge current density with units A/m$^2$.

### 2 Spin Hall constitutive relation bulk, isotropic, steady state

In an isotropic normal metal with a spin Hall angle $\theta_{\mathrm{SH}}$, a standard constitutive relation (for the conventional spin Hall geometry) is
$$
J_{s,i}^{\ \alpha}
=\theta_{\mathrm{SH}}\,\frac{\hbar}{2e}\,
\sum_{j\in\{x,y,z\}}
\varepsilon_{i j \alpha}\,J_{c,j},
$$
where $\varepsilon_{i j \alpha}$ is the Levi–Civita symbol.

For the commonly used configuration
$$
\mathbf{J}_c = J_{c,x}\,\hat x,
\quad\text{then}\quad
J_{s,y}^{\ z} = \theta_{\mathrm{SH}}\frac{\hbar}{2e}J_{c,x},
$$
and all other components are determined by symmetry and sign conventions.

### 3 Device-level caveat why this is only the *bulk* conversion

In thin films and multilayers, the effective torque delivered to an adjacent ferromagnet depends on spin diffusion, interfacial spin mixing conductance, and backflow. In that setting, $\theta_{\mathrm{SH}}$ above is replaced by an effective efficiency $\theta_{\mathrm{eff}}$ that is thickness- and interface-dependent.

**If the assumptions are false, how to make them true.** In real devices, spin diffusion, finite thickness, and interface transparency renormalize the delivered spin current. To make predictions rigorous, solve coupled charge–spin drift–diffusion with boundary conditions using spin-mixing conductance; the identity shifts from a bulk $	heta_{\mathrm{SH}}$ to an effective device efficiency $	heta_{\mathrm{eff}}$.

### Numerical example

Take $\theta_\mathrm{SH}=0.10$ and $J_c=1.0\times 10^{11}\ \mathrm{A/m^2}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $J_s\;[\mathrm{J/m^2}]$ | $3.2911\times 10^{-6}$ | 0.0000032911 | 3.2911e-6 |
| $J_s\;[\mathrm{\mu J/m^2}]$ | $3.2911\times 10^{0}$ | 3.2911 | 3.2911e0 |

### 5 of 5 rigor addendum

#### Diffusion and interface transparency model for an effective spin Hall angle

The “bare” conversion law
$$
J_s = \left(\frac{\hbar}{2e}\right)\theta_\mathrm{SH} J_c
$$
is a constitutive statement for bulk conversion inside the heavy metal.

In a device, what matters is the *absorbed* spin current at an interface, which is reduced by spin diffusion and imperfect interface transmission.

A minimal 1D steady-state model uses a spin accumulation $\mu_s(z)$ in a heavy metal of thickness $t$ that obeys
$$
\frac{d^2\mu_s}{dz^2} = \frac{\mu_s}{\lambda^2},
$$
where $\lambda$ is the spin diffusion length.

A widely used phenomenological boundary condition is:

- free surface at $z=t$: no spin current leaving, $J_s(t)=0$,
- interface at $z=0$: absorbed spin current proportional to spin accumulation,
  $$
  J_s(0) = G_\mathrm{int}\,\mu_s(0),
  $$
  where $G_\mathrm{int}$ is an effective interface spin conductance proportional to the spin-mixing conductance.

Solving the diffusion equation with these boundary conditions yields an absorbed spin current of the form
$$
J_s(0) = \left(\frac{\hbar}{2e}\right)\theta_\mathrm{eff}(t)\,J_c,
$$
with a thickness-dependent effective spin Hall angle that, in a common simplified transparency model, can be written
$$
\theta_\mathrm{eff}(t)
\approx
\theta_\mathrm{SH}
\left(1-\operatorname{sech}\!\left(\frac{t}{\lambda}\right)\right)
\underbrace{\frac{G_\mathrm{int}}{G_\mathrm{int}+G_\mathrm{bulk}}}_{\text{interface transparency }T},
\qquad
G_\mathrm{bulk}\sim \frac{\sigma}{\lambda}.
$$

This makes the identity shift explicit:

- $\theta_\mathrm{SH}$ is a bulk conversion parameter,
- $\theta_\mathrm{eff}$ is a device-level effective parameter, which is what torque experiments infer unless they explicitly de-embed diffusion and interface physics.

#### Error certificate

The simplified formula above is a coarse closure. The first corrections that often matter are:

- spin memory loss at the interface,
- complex spin-mixing conductance,
- nonuniform current distribution, and
- temperature dependence of $\lambda$ and $\sigma$.

A quantitative certificate therefore includes a report of $t/\lambda$ and an estimate of $T$.

#### Reproducible computation

```python
import math

# Control knobs
theta_SH = 0.10
t = 4.0e-9          # m
lam = 2.0e-9        # m

sigma = 5.0e6       # S/m, example magnitude
G_int = 1.0e15      # 1/ohm/m^2, example effective interface conductance

G_bulk = sigma / lam
T = G_int / (G_int + G_bulk)

theta_eff = theta_SH * (1.0 - 1.0 / math.cosh(t / lam)) * T

print("t/lambda =", t / lam)
print("transparency T =", T)
print("theta_eff =", theta_eff)
```

#### Primary sources

- Sinova et al., review on spin Hall effects, arXiv.
- Open spin-transport notes discussing spin diffusion length and interface transparency closures.

---

## P16 FORMS: Faraday’s law as Stokes’ theorem integral form

**Intuitive explanation.** A changing magnetic field through a loop induces a voltage around the loop.

**Grad-level framing.** Maxwell’s equations become compact in differential forms; Stokes’ theorem is the coordinate-free bridge between differential and integral laws. (see References)

### Assumptions, conventions, and validity domain

- **Fields.** $\mathbf{E}(\mathbf{x},t)$ and $\mathbf{B}(\mathbf{x},t)$ are sufficiently smooth to justify differentiating under the integral sign.
- **Geometry.** $S$ is a fixed, oriented surface with boundary $\partial S$; orientation follows the right-hand rule.
- **Moving boundaries.** If $\partial S$ moves, include motional electromotive force (EMF); the fixed-surface derivation is stated explicitly.

### Symbolic derivation Curl form → Stokes → EMF–flux relation

Start with
$$
\nabla\times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t}.
$$
Integrate over surface $S$ with boundary $\partial S$:
$$
\oint_{\partial S} \mathbf{E}\cdot d\boldsymbol{\ell}
= \int_S (\nabla\times \mathbf{E})\cdot d\mathbf{A}
= -\frac{d}{dt}\int_S \mathbf{B}\cdot d\mathbf{A}.
$$
Define EMF $\mathcal{E}$ and flux $\Phi_B$:
$$
\mathcal{E}=-\frac{d\Phi_B}{dt}.
$$

**If the assumptions are false, how to make them true.** For moving/deforming loops, include motional EMF; the identity shifts from transformer induction to transformer-plus-motional induction.

### Numerical example

Uniform $B(t)$ through a fixed loop of area $A$ gives $\mathcal{E}=-A\,dB/dt$.

Take $A=1.0\ \mathrm{cm^2}=1.0\times 10^{-4}\ \mathrm{m^2}$ and $dB/dt=0.02\ \mathrm{T/s}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\mathcal{E}\;[\mathrm{V}]$ | $-2.0000\times 10^{-6}$ | -0.0000020000 | -2.0000e-6 |
| $\mathcal{E}\;[\mathrm{\mu V}]$ | $-2.0000\times 10^{0}$ | -2.0000 | -2.0000e0 |

### 5 of 5 rigor addendum

#### Moving-boundary extension and motional electromotive force

The main text presents Faraday’s law for a fixed surface. If the loop moves or the spanning surface changes with time, the correct electromotive force includes motional terms.

A standard form is
$$
\mathcal{E}(t)
\equiv
\oint_{C(t)} \left(\mathbf{E} + \mathbf{v}\times \mathbf{B}\right)\cdot d\mathbf{l}
=
-\frac{d}{dt}\int_{S(t)} \mathbf{B}\cdot d\mathbf{A},
$$
where $\mathbf{v}$ is the local velocity of the circuit element.

This identity can be derived by combining the fixed-surface Maxwell–Faraday equation with a transport theorem for a moving surface, and it cleanly separates:

- transformer electromotive force from $\partial\mathbf{B}/\partial t$,
- motional electromotive force from $\mathbf{v}\times\mathbf{B}$.

#### Worked extension example sliding rod

A conducting rod of length $\ell$ moving at speed $v$ perpendicular to a uniform magnetic field $B$ generates a motional electromotive force
$$
\mathcal{E} = B\ell v.
$$

#### Reproducible computation

```python
# Control knobs
B = 0.50      # tesla
ell = 0.10    # m
v = 2.0       # m/s

emf = B * ell * v
print("EMF [V] =", emf)
```

#### Primary sources

- MIT 8.02 electromagnetism notes deriving motional electromotive force from Faraday’s law, PDF.
- Differential-forms-based electromagnetism notes explaining moving-boundary transport theorems.

---

## P17 GA: 3D rotation via a rotor geometric algebra

**Intuitive explanation.** Rotation preserves length while mixing components; geometric algebra packages the “mixing” into a compact exponential object that acts by sandwiching.

**Grad-level framing.** In Euclidean geometric (Clifford) algebra $\mathrm{Cl}_{3,0}$, the geometric product of vectors unifies the dot and wedge products, and rotors $R\in\mathrm{Spin}(3)$ implement orthogonal transformations by $v'=Rv\widetilde{R}$, generalizing complex phases and quaternions. This unification perspective is emphasized in modern geometric-algebra treatments of physics and engineering.

### Assumptions, conventions, and validity domain

- **Algebra.** Euclidean 3D geometric algebra $\mathrm{Cl}_{3,0}$ generated by an orthonormal basis $\{e_1,e_2,e_3\}$ with $e_i^2=+1$.
- **Geometric product.** For vectors $a,b$, the geometric product decomposes as
  $$
  ab = a\cdot b + a\wedge b,
  $$
  where $a\cdot b=\tfrac12(ab+ba)$ (scalar) and $a\wedge b=\tfrac12(ab-ba)$ (bivector).
- **Reversion.** $\widetilde{(\cdot)}$ reverses the order of vector factors: $\widetilde{e_{i_1}\cdots e_{i_k}}=e_{i_k}\cdots e_{i_1}$.
- **Rotor.** A rotor satisfies $R\widetilde{R}=1$ and acts on vectors by sandwiching: $v' = Rv\widetilde{R}$.
- **Angle/axis parametrization.** A rotation of angle $\theta$ about unit axis $\hat n$ is represented by the unit bivector $B:=I\hat n$, where $I:=e_1e_2e_3$ and $B^2=-1$.

### Symbolic derivation geometric product → rotor exponential → sandwich action

#### 1 Rotor exponential form

Let $B$ be a **unit** bivector, $B^2=-1$. Define the rotor
$$
R := e^{-B\theta/2}.
$$
Using the power series and $B^2=-1$ gives the closed form
$$
R=\cos\frac{\theta}{2}-B\sin\frac{\theta}{2},
\qquad
\widetilde{R}=\cos\frac{\theta}{2}+B\sin\frac{\theta}{2},
$$
and hence $R\widetilde{R}=1$.

#### 2 Sandwiching implements an orthogonal map

Define the map $\mathcal{R}(v):=Rv\widetilde{R}$. Since $R\widetilde{R}=1$ and reversion is an anti-automorphism,
$$
\mathcal{R}(v)\cdot \mathcal{R}(v)
=\langle (Rv\widetilde{R})(Rv\widetilde{R})\rangle_0
=\langle R(vv)\widetilde{R}\rangle_0
=\langle vv\rangle_0
=v\cdot v,
$$
so lengths are preserved; $\mathcal{R}$ is therefore an element of $\mathrm{SO}(3)$.

#### 3 Recovering the familiar axis–angle formula

Decompose $v=v_\parallel+v_\perp$ where $v_\parallel:=(v\cdot\hat n)\hat n$ and $v_\perp:=v-v_\parallel$. Then $v_\parallel$ commutes with $B$ and $v_\perp$ anticommutes with $B$. Expanding $v'=Rv\widetilde{R}$ yields
$$
v' = v_\parallel + v_\perp\cos\theta + (Bv_\perp)\sin\theta.
$$
Using $Bv_\perp=I\hat n\,v_\perp=-\hat n\times v_\perp$ (via $a\times b=-I(a\wedge b)$ in $\mathrm{Cl}_{3,0}$), this is equivalent to the Rodrigues rotation formula.

**If the assumptions are false, how to make them true.** In non-Euclidean signature (e.g., spacetime algebra), bivectors can square to $+1$ as well as $-1$, and the corresponding exponentials generate Lorentz boosts as well as rotations. To make the Euclidean rotor story apply, restrict to a Euclidean subalgebra or to spacelike bivector planes; the identity shifts from $\mathrm{SO}(3)$ rotations to $\mathrm{SO}(1,3)$ Lorentz transformations.

### Numerical example

Rotate $v=(1,0,0)$ by $\theta=30^\circ$ about $\hat z$. The expected result is $v'=(\cos\theta,\sin\theta,0)$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $v'_x\;[-]$ | $8.6603\times 10^{-1}$ | 0.8660 | 8.6603e-1 |
| $v'_y\;[-]$ | $5.0000\times 10^{-1}$ | 0.5000 | 5.0000e-1 |

### 5 of 5 rigor addendum

#### Bivector sign conventions and rotor exponential

Different geometric algebra texts choose different sign conventions for the rotor exponential, which affects whether one writes
$$
R = \exp\!\left(-\frac{B\theta}{2}\right)
\quad\text{or}\quad
R = \exp\!\left(+\frac{B\theta}{2}\right),
$$
where $B$ is a unit bivector representing the oriented plane of rotation.

A monograph-grade workflow therefore does two things:

1. States the convention, including the definition of the reverse $\\widetilde{R}$.
2. Validates the convention on a worked example by comparing to the standard rotation matrix.

For a right-handed rotation by angle $\theta$ about the $+z$ axis, with basis $(e_1,e_2,e_3)$, the rotation plane is $e_1e_2$, so a consistent rotor choice is
$$
R = \exp\!\left(-\frac{e_1e_2\,\theta}{2}\right),
\qquad
v' = R v \\widetilde{R}.
$$

#### Worked equivalence check with the Rodrigues matrix form

For rotation about $+z$ by $\theta$,
$$
\begin{pmatrix}
x'\\
y'\\
z'
\end{pmatrix}
=
\begin{pmatrix}
\cos\theta & -\sin\theta & 0\\
\sin\theta & \cos\theta & 0\\
0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
x\\
y\\
z
\end{pmatrix}.
$$

#### Reproducible computation

```python
import math

# Control knobs
theta = math.pi / 2.0
x, y, z = 1.0, 2.0, 3.0

# Matrix rotation about z
xp = math.cos(theta) * x - math.sin(theta) * y
yp = math.sin(theta) * x + math.cos(theta) * y
zp = z

print("rotated (matrix) =", (xp, yp, zp))
# For theta = pi/2, expect (-y, x, z)
assert abs(xp - (-y)) < 1e-12
assert abs(yp - (x)) < 1e-12
assert abs(zp - (z)) < 1e-12
```

#### Primary sources

- Open lecture notes on geometric algebra rotors and their relation to rotation matrices.
- Lasenby, *Geometric Algebra as a Unifying Language for Physics and Engineering*, arXiv or open manuscript.

---

## P18 GAUGE: Berry phase for spin-1/2 tracing a cone holonomy

**Intuitive explanation.** Returning to the same physical state can still accumulate an extra geometric phase.

**Grad-level framing.** Berry phase is holonomy of a U(1) connection; for spin-1/2 it equals minus half the Bloch-sphere solid angle. (see References)

### Assumptions, conventions, and validity domain

- **Hamiltonian.** Spin-1/2 in a slowly varying magnetic field: $H(t)=-(\hbar\omega_0/2)\,\hat n(t)\cdot\boldsymbol{\sigma}$ with $|\hat n(t)|=1$.
- **Adiabaticity.** Evolution is adiabatic: the system remains in an instantaneous non-degenerate eigenstate up to a phase; the gap $\hbar\omega_0$ remains nonzero along the path.
- **Closed loop.** $\hat n(t)$ traces a closed loop on the Bloch sphere; Berry phase is gauge-invariant modulo $2\pi$.
- **Sign conventions.** The sign of $\gamma_B$ depends on whether the state is aligned or anti-aligned with $\hat n$; the formula below is stated for the “spin-up along $\hat n$” eigenstate of $\hat n\cdot\boldsymbol{\sigma}$.

### Symbolic derivation Solid angle → geometric phase

We compute the Berry phase for a spin-1/2 whose Hamiltonian direction $\hat n(t)$ traces a closed cone.

### 1 Hamiltonian and instantaneous eigenstates

Let
$$
H(t)= -\frac{\hbar\omega_0}{2}\,\hat n(t)\cdot\boldsymbol{\sigma},
\qquad |\hat n(t)|=1,
$$
where $\boldsymbol{\sigma}$ are the Pauli matrices. The instantaneous eigenstates satisfy
$$
\hat n(t)\cdot\boldsymbol{\sigma}\,|+\!(t)\rangle = |+\!(t)\rangle,
\qquad
\hat n(t)\cdot\boldsymbol{\sigma}\,|-\!(t)\rangle = -|-\!(t)\rangle.
$$
Assume adiabatic evolution and that the system remains in $|+\!(t)\rangle$ up to a phase.

### 2 Berry connection and Berry phase

The Berry connection for the chosen eigenstate is
$$
\mathbf{A}(\hat n)= i\langle +| \nabla_{\hat n} |+\rangle,
$$
and the Berry phase accumulated along a closed loop $\mathcal{C}$ is
$$
\gamma_B = \oint_{\mathcal{C}} \mathbf{A}\cdot d\hat n
=\int\!\!\!\int_{\Sigma} \mathbf{F}\cdot d\mathbf{S},
$$
where $\mathbf{F}=\nabla_{\hat n}\times \mathbf{A}$ is the Berry curvature and $\Sigma$ is any surface on the Bloch sphere with boundary $\partial\Sigma=\mathcal{C}$.

For spin-1/2, the Berry curvature corresponds to a magnetic-monopole field on the sphere with strength $1/2$, yielding
$$
\gamma_B = -\frac{1}{2}\Omega,
$$
where $\Omega$ is the solid angle enclosed by $\mathcal{C}$ (the sign corresponds to the $|+\rangle$ eigenstate of $\hat n\cdot\boldsymbol{\sigma}$; choosing $|-\rangle$ flips the sign).

### 3 Cone of fixed polar angle $\theta$

If $\hat n(t)$ traces a cone at polar angle $\theta$ with azimuth $\phi:0\to 2\pi$, the enclosed solid angle is
$$
\Omega = 2\pi\,(1-\cos\theta),
$$
so
$$
\gamma_B = -\frac{\Omega}{2} = -\pi(1-\cos\theta).
$$

**If the assumptions are false, how to make them true.** If the evolution is not adiabatic (finite-speed protocol, level crossings, or strong noise), transitions between eigenstates occur and the geometric phase is no longer simply $-\Omega/2$. Enforce adiabaticity by slowing the protocol relative to the gap scale and suppressing noise, or use non-adiabatic geometric-phase formalisms; this changes the identity from pure Berry holonomy to mixed dynamical–geometric behavior.

### Numerical example

Take $\theta=30^\circ$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\gamma_B\;[\mathrm{rad}]$ | $-4.2089\times 10^{-1}$ | -0.4209 | -4.2089e-1 |

### 5 of 5 rigor addendum

#### Adiabatic condition estimate

The Berry phase formula is geometric, but it is only realized when the evolution is adiabatic.

A common quantitative adiabatic condition is:
$$
\max_{m\neq n}\frac{|\langle m(t)|\dot{H}(t)|n(t)\rangle|}{\hbar\,\omega_{mn}(t)^2} \ll 1,
\qquad
\omega_{mn} \equiv \frac{E_m-E_n}{\hbar}.
$$

For a spin-1/2 in a magnetic field $\mathbf{B}(t)$ of approximately constant magnitude $B_0$, the relevant gap is $\Delta E \sim \hbar \gamma B_0$. A practical adiabatic certificate is therefore
$$
\left|\frac{d\hat{\mathbf{B}}}{dt}\right| \ll \gamma B_0,
$$
meaning the field direction changes slowly compared to the Larmor frequency.

#### Reproducible computation

```python
import math

# Control knobs
theta = math.radians(30.0)

Omega = 2.0 * math.pi * (1.0 - math.cos(theta))
gamma_B = -0.5 * Omega

print("solid angle Omega [sr] =", Omega)
print("Berry phase gamma_B [rad] =", gamma_B)
```

#### Primary sources

- MIT OpenCourseWare notes on the adiabatic approximation and Berry phase, PDF.
- Open-access reviews on geometric phases and adiabatic theorems.

---

## P19 INFO: Gibbs’ inequality $D_{KL}\ge 0$ and a Bernoulli KL calculation

**Intuitive explanation.** Using the wrong probabilities cannot, on average, compress data better than using the right ones.

**Grad-level framing.** Relative entropy is nonnegative by convexity of $-\ln x$ (equivalently Jensen). (see References)

### Assumptions, conventions, and validity domain

- **Probability model.** $p=(p_i)$ and $q=(q_i)$ are distributions on a finite or countable alphabet with $p_i\ge 0$, $q_i\ge 0$, $\sum_i p_i=\sum_i q_i=1$.
- **Absolute continuity.** If $p_i>0$ then require $q_i>0$ for finiteness; otherwise $D_{KL}(p\|q)=+\infty$.
- **Convexity tool.** Use either Jensen’s inequality or the scalar bound $-\ln x\ge 1-x$ for $x>0$.

### Symbolic derivation Convexity → inequality

Define
$$
D_{KL}(p\|q):=\sum_i p_i\ln\frac{p_i}{q_i}.
$$
Use $-\ln x \ge 1-x$ for $x>0$. Let $x_i=q_i/p_i$:
$$
-\ln\frac{q_i}{p_i} \ge 1-\frac{q_i}{p_i}.
$$
Multiply by $p_i$ and sum:
$$
\sum_i p_i\ln\frac{p_i}{q_i} \ge \sum_i (p_i-q_i)=0.
$$

**If the assumptions are false, how to make them true.** If some $q_i=0$ with $p_i>0$, divergence is infinite; smoothing $q$ changes the identity to a regularized divergence.

### Numerical example: Bernoullip vs Bernoulliq

For Bernoulli parameters $p$ and $q$,
$$
D_{KL}(p\|q)=p\ln\frac{p}{q}+(1-p)\ln\frac{1-p}{1-q}.
$$
Let $p=0.7$ and $q=0.5$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $D_\mathrm{KL}(p\|q)\;[\mathrm{nats}]$ | $8.2283\times 10^{-2}$ | 0.0823 | 8.2283e-2 |
| $D_\mathrm{KL}(p\|q)\;[\mathrm{bits}]$ | $1.1871\times 10^{-1}$ | 0.1187 | 1.1871e-1 |

### 5 of 5 rigor addendum

#### Equality conditions for Gibbs inequality and the log-sum inequality link

For discrete distributions $p$ and $q$ on the same finite support with $p_i\ge 0$, $q_i>0$, and $\sum_i p_i=\sum_i q_i=1$, the Kullback–Leibler divergence
$$
D_{KL}(p\|q)=\sum_i p_i \ln\frac{p_i}{q_i}
$$
satisfies $D_{KL}(p\|q)\ge 0$.

**Equality condition:** $D_{KL}(p\|q)=0$ if and only if $p_i=q_i$ for all $i$ with $p_i>0$.

A closely related inequality is the log-sum inequality: for nonnegative sequences $a_i,b_i$,
$$
\sum_i a_i \ln\frac{a_i}{b_i} \ge \left(\sum_i a_i\right)\ln\left(\frac{\sum_i a_i}{\sum_i b_i}\right).
$$
Setting $a_i=p_i$ and $b_i=q_i$ with both sums equal to 1 reduces the log-sum inequality to Gibbs inequality.

#### Reproducible computation

```python
import math

# Control knobs for Bernoulli
p = 0.30
q = 0.50

DKL = p * math.log(p / q) + (1.0 - p) * math.log((1.0 - p) / (1.0 - q))
print("DKL =", DKL)

assert DKL >= -1e-15
```

#### Primary sources

- Information theory lecture notes deriving Gibbs inequality via convexity and the log-sum inequality, PDF.

---

## P20 CRYPTO: A hybrid-style reduction bound CTR-mode IND-CPA example

**Intuitive explanation.** If the keystream looks random, XOR hides the message; if the keystream is distinguishable, the cipher becomes distinguishable.

**Grad-level framing.** Game-hopping bounds advantage by summing distinguishability gaps and adding a collision term when internal states/inputs can repeat.

### Assumptions, conventions, and validity domain

- **Primitive.** Block cipher $E_K$ is a pseudorandom permutation (PRP) on $\{0,1\}^n$ for $n$-bit blocks.
- **CTR construction.** Ciphertext blocks are $C_j = P_j \oplus E_K(\mathrm{IV}_j)$, where $\mathrm{IV}_j\in\{0,1\}^n$ are derived from a nonce and counter.
- **Nonce model.** This bound is stated for the common case where the nonce is uniformly random per encryption (so repeats can occur with birthday probability) and counters do not wrap within a nonce.
- **Security notion.** IND-CPA (Indistinguishability under Chosen Plaintext Attack) advantage is defined in the standard left–right game; the proof uses explicit game hops.
- **Accounting.** Let $q$ be the total number of **block** encryptions across all adversary queries, and let $\nu$ be the nonce bit-length (so $n=\nu+r$ with $r$ counter bits).

### Symbolic derivation Reduction + hybrid hops + collision term

We present an explicit game-based bound for CTR mode under a standard nonce model.

### CTR definition blockwise

Let $E_K:\{0,1\}^n\to\{0,1\}^n$ be a block cipher. CTR encryption of a message split into $n$-bit blocks $P_0,\ldots,P_{\ell-1}$ proceeds as follows:

- Choose a $\nu$-bit nonce $N$ uniformly at random (fresh per encryption query).
- Form block inputs $\mathrm{IV}_j := N \parallel \mathrm{ctr}_j$, where $\mathrm{ctr}_j\in\{0,1\}^r$ is a counter value and $\nu+r=n$.
- Output ciphertext blocks
$$
C_j := P_j \oplus E_K(\mathrm{IV}_j),\qquad j=0,\ldots,\ell-1.
$$

Assume counters never repeat **within** a single encryption query (no wraparound), so repeats can only occur across queries if the same nonce $N$ is reused.

### IND-CPA game and advantage

Let $\mathrm{Adv}^{\mathrm{CTR}}_{\mathrm{IND\text{-}CPA}}(A)$ be the standard left–right indistinguishability advantage of adversary $A$ with encryption-oracle access.

### Game hop 0 → 1 replace PRP with random permutation

Define Game 0 as the real CTR scheme using $E_K$. Define Game 1 by replacing $E_K$ with a truly random permutation $\Pi$ on $\{0,1\}^n$.

By definition of PRP advantage, there exists a PRP distinguisher $B$ such that
$$
\left|\Pr[\mathrm{Game0}(A)=1]-\Pr[\mathrm{Game1}(A)=1]\right|
\le
\mathrm{Adv}_{\mathrm{PRP}}(B).
$$

### Game hop 1 → 2 replace permutation with random function, paying a collision term

Define Game 2 by replacing $\Pi$ with a truly random function $F:\{0,1\}^n\to\{0,1\}^n$.

Let $\mathsf{Bad}$ be the event that the oracle is queried on a repeated block input $\mathrm{IV}_j$. Conditioned on $\neg\mathsf{Bad}$, the outputs of a random permutation and a random function on distinct inputs are identically distributed, so
$$
\left|\Pr[\mathrm{Game1}(A)=1]-\Pr[\mathrm{Game2}(A)=1]\right|
\le
\Pr[\mathsf{Bad}].
$$

### Bounding $\Pr[\mathsf{Bad}]$ under the random-nonce model

Let $q$ be the total number of block encryptions across all adversary queries (equivalently, total number of distinct counters used across all nonces). Under the assumption of no counter wrap, the only way to repeat a block input is to repeat a nonce $N$ and also reuse the same counter value.

A simple conservative upper bound is obtained by ignoring counters and bounding nonce collisions alone. If nonces are $\nu$-bit uniformly random, then by the birthday bound,
$$
\Pr[\text{nonce collision among at most }q\text{ nonce draws}]
\le
\frac{\binom{q}{2}}{2^{\nu}}
\le
\frac{q^2}{2^{\nu+1}}.
$$
This upper-bounds $\Pr[\mathsf{Bad}]$, hence
$$
\Pr[\mathsf{Bad}] \le \frac{q^2}{2^{\nu+1}}.
$$

### Game 2 perfect secrecy

In Game 2, each block mask $F(\mathrm{IV}_j)$ is uniformly random and independent (except for repeats, which are excluded by conditioning). Therefore each ciphertext block is a one-time pad of its corresponding plaintext block, and the left and right plaintexts are information-theoretically indistinguishable:
$$
\Pr[\mathrm{Game2}(A)=1]=\tfrac12
\quad\Rightarrow\quad
\mathrm{Adv}=0\text{ in Game 2}.
$$

### Final bound

Combining the hops (triangle inequality),
$$
\mathrm{Adv}^{\mathrm{CTR}}_{\mathrm{IND\text{-}CPA}}(A)
\le
\mathrm{Adv}_{\mathrm{PRP}}(B) + \frac{q^2}{2^{\nu+1}}.
$$

**Stronger statement under nonce uniqueness.** If the scheme enforces nonce uniqueness (never repeats $N$), then $\Pr[\mathsf{Bad}]=0$ (assuming no counter wrap), and the collision term drops out entirely.

**If the assumptions are false, how to make them true.** If nonces can repeat at non-negligible probability (or if counters can wrap), CTR security degrades sharply because keystream blocks repeat. Enforce nonce uniqueness (and prevent counter wrap) to make $\Pr[\mathsf{Bad}]=0$, or switch to misuse-resistant authenticated-encryption schemes; this changes the identity from nonce-respecting CTR to misuse-resistant encryption.

### Numerical example

Assume a 128-bit block cipher (n=128) with a 96-bit random nonce ($\nu=96$) and a 32-bit counter ($r=32$), and suppose the adversary causes at most $q=2^{32}$ total block encryptions. Take $\mathrm{Adv}_\mathrm{PRP}(B)=2^{-40}$.

Under the random-nonce model, the collision term is bounded by $q^2/2^{\nu+1}=2^{-33}$, so the overall advantage bound is:
$$
\mathrm{Adv}^\mathrm{CTR}_\mathrm{IND\text{-}CPA}(A) \le \mathrm{Adv}_\mathrm{PRP}(B) + \frac{q^2}{2^{\nu+1}}.
$$

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $q\;[\mathrm{blocks}]$ | $4.2950\times 10^{9}$ | 4,294,967,296.0000 | 4.2950e9 |
| $\mathrm{Adv}_\mathrm{PRP}\;[-]$ | $9.0949\times 10^{-13}$ | 0.0000000000009094947017729282379150390625 | 9.0949e-13 |
| $q^2/2^{\nu+1}\;[-]$ | $1.1642\times 10^{-10}$ | 0.000000000116415321826934814453125 | 1.1642e-10 |
| $\text{total bound}\;[-]$ | $1.1732\times 10^{-10}$ | 0.0000000001173248165287077426910400390625 | 1.1732e-10 |

### 5 of 5 rigor addendum

#### Precise IND-CPA game definition and resource bounds

A canonical left-right indistinguishability under chosen-plaintext attack game can be stated:

1. Challenger samples key $K$.
2. Adversary $\mathcal{A}$ may query an encryption oracle on messages of its choice.
3. $\mathcal{A}$ outputs equal-length challenge messages $(m_0,m_1)$.
4. Challenger samples $b\leftarrow\{0,1\}$ and returns $c^\star = \mathrm{Enc}_K(m_b)$.
5. $\mathcal{A}$ continues oracle queries, subject to standard restrictions.
6. $\mathcal{A}$ outputs $\hat b$ and wins if $\hat b=b$.

The advantage is
$$
\mathrm{Adv}^{\mathrm{IND\text{-}CPA}}_{\mathcal{A}} \equiv \left|\Pr[\hat b=b]-\frac12\right|.
$$

Resource bounds are part of the statement: $\mathcal{A}$ is typically probabilistic polynomial time, with at most $q$ oracle queries and total encrypted block count at most $Q$.

#### Tight collision accounting in CTR mode

CTR mode uses a keystream indexed by a nonce and counter. Security reductions typically require that the nonce–counter pairs not repeat.

If a $v$-bit nonce is sampled uniformly at random for each encryption query, the probability of *any* nonce collision over $q$ queries is bounded by the birthday term
$$
\Pr[\text{collision}] \le \frac{q(q-1)}{2^{v+1}} \approx \frac{q^2}{2^{v+1}}.
$$

A tight account also tracks total block count $Q$, because counter overlap within a single nonce can occur if messages are too long; a monograph-grade statement therefore includes a maximum message length or a bound on $Q$.

#### Reproducible computation

```python
# Birthday bound for nonce collisions
v = 96
q = 1_000_000

p_collision = q * (q - 1) / (2.0 ** (v + 1))
print("collision upper bound =", p_collision)
```

#### Primary sources

- Lecture notes on CTR mode security via hybrids and birthday bounds, PDF.
- Cryptography course notes defining IND-CPA games and reductions, PDF.

---

## P21 EXP: Uncertainty propagation for a derived quantity $R=V/I$

**Intuitive explanation.** If voltage and current each have measurement wiggle, resistance inherits a combined wiggle.

**Grad-level framing.** First-order uncertainty propagation uses a Jacobian; independent variances add in quadrature.

### Assumptions, conventions, and validity domain

- **Small-uncertainty regime.** Use first-order (linear) propagation: higher-order terms are neglected, which is valid when relative uncertainties are small.
- **Random variables.** $V$ and $I$ are modeled as unbiased estimates with known standard uncertainties $u_V,u_I$.
- **Independence.** The worked example assumes $\mathrm{Cov}(V,I)=0$; the general covariance form is stated explicitly.

### Symbolic derivation Linearization → uncertainty budget

For $y=f(x_1,\dots,x_n)$, small errors give
$$
\delta y \approx \sum_i \frac{\partial f}{\partial x_i}\delta x_i.
$$
Independent inputs imply
$$
u_y^2 \approx \sum_i \left(\frac{\partial f}{\partial x_i}\right)^2 u_{x_i}^2.
$$
For $R(V,I)=V/I$:
$$
\frac{\partial R}{\partial V}=\frac{1}{I},\qquad
\frac{\partial R}{\partial I}=-\frac{V}{I^2},
$$
so
$$
u_R=\sqrt{\left(\frac{u_V}{I}\right)^2+\left(\frac{V\,u_I}{I^2}\right)^2}.
$$

**If the assumptions are false, how to make them true.** If $V$ and $I$ are correlated, include covariance terms; identity shifts from diagonal to full covariance propagation.

### Numerical example

Take $V=1.200\ \mathrm{V}$ with $u_V=0.002\ \mathrm{V}$, and $I=20.0\ \mathrm{mA}$ with $u_I=0.10\ \mathrm{mA}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $R=V/I\;[\Omega]$ | $6.0000\times 10^{1}$ | 60.0000 | 6.0000e1 |
| $u_R\;[\Omega]\ (1\sigma)$ | $3.1623\times 10^{-1}$ | 0.3162 | 3.1623e-1 |
| $u_R/R\;[-]$ | $5.2705\times 10^{-3}$ | 0.0053 | 5.2705e-3 |

### 5 of 5 rigor addendum

#### Full covariance propagation example

For a scalar output $y=f(x)$ with $x\in\mathbb{R}^n$ and covariance matrix $\Sigma_x$, the first-order delta method yields
$$
\mathrm{Var}(y)\approx \nabla f(\mu)^\mathsf{T}\,\Sigma_x\,\nabla f(\mu).
$$

Example: $R = V/I$ with correlated $V$ and $I$.

Let
$$
f(V,I)=\frac{V}{I},
\qquad
\nabla f = \left(\frac{\partial f}{\partial V},\frac{\partial f}{\partial I}\right) =
\left(\frac{1}{I}, -\frac{V}{I^2}\right).
$$
Then
$$
\mathrm{Var}(R)\approx
\left(\frac{1}{I}\right)^2\mathrm{Var}(V)
+
\left(\frac{V}{I^2}\right)^2\mathrm{Var}(I)
+
2\left(\frac{1}{I}\right)\left(-\frac{V}{I^2}\right)\mathrm{Cov}(V,I).
$$

#### Second-order nonlinearity caveat with quantification

The first-order propagation is accurate when $f$ is approximately linear over the uncertainty scale. A practical quantitative trigger for second-order corrections is:

- evaluate second derivatives (Hessian) and compare the second-order term magnitude to the first-order term magnitude.

For scalar $y=f(x)$ with one variable, a conservative heuristic is:
$$
\left|\frac{1}{2}f''(\mu)\,u_x^2\right| \ll |f'(\mu)|\,u_x,
$$
where $u_x$ is the standard uncertainty in $x$.

#### Reproducible computation

```python
import math

# Control knobs
V = 1.000  # V
I = 0.010  # A

uV = 0.005  # V
uI = 0.0002 # A
rho = 0.5   # correlation coefficient

covVI = rho * uV * uI

dRdV = 1.0 / I
dRdI = -V / (I**2)

varR = (dRdV**2) * (uV**2) + (dRdI**2) * (uI**2) + 2.0 * dRdV * dRdI * covVI
uR = math.sqrt(varR)

print("R [ohm] =", V / I)
print("uR [ohm] =", uR)
```

#### Primary sources

- NIST Technical Note 1900, *NIST/SEMATECH e-Handbook of Statistical Methods* and uncertainty guidance.
- Joint Committee for Guides in Metrology guidance on uncertainty propagation.

---

## P22 QFI: Fisher information → Cramér–Rao bound Gaussian mean

**Intuitive explanation.** More samples or less noise means a tighter estimate.

**Grad-level framing.** Fisher information measures likelihood curvature; the Cramér–Rao bound lower-bounds variance of unbiased estimators by inverse information. (see References)

### Assumptions, conventions, and validity domain

- **Regularity.** Probability density $p(x|\theta)$ is differentiable in $\theta$ and allows interchange of differentiation and integration: $\partial_\theta \int p=\int \partial_\theta p$.
- **Support.** The support of $p(x|\theta)$ does not depend on $\theta$ (or boundary terms vanish).
- **Estimator condition.** The classical Cramér–Rao bound applies to unbiased estimators; biased versions require additional terms.
- **Model.** The example uses $x_i\sim\mathcal{N}(\mu,\sigma^2)$ with known $\sigma$.

### Symbolic derivation Likelihood curvature → CRB

We derive the Fisher information and the Cramér–Rao bound (CRB) explicitly for the Gaussian-mean problem.

### 1 Model and likelihood

Let $x_1,\ldots,x_N$ be independent and identically distributed (i.i.d.) with
$$
x_i \sim \mathcal{N}(\mu,\sigma^2),
$$
where $\sigma>0$ is known and $\mu$ is the parameter to estimate.

The joint density is
$$
p(\mathbf{x}\mid \mu)
=\prod_{i=1}^N \frac{1}{\sqrt{2\pi}\sigma}\exp\!\left(-\frac{(x_i-\mu)^2}{2\sigma^2}\right).
$$
The log-likelihood is
$$
\ell(\mu):=\ln p(\mathbf{x}\mid \mu)
=-N\ln(\sqrt{2\pi}\sigma) - \frac{1}{2\sigma^2}\sum_{i=1}^N (x_i-\mu)^2.
$$

### 2 Score function and Fisher information

Differentiate:
$$
\frac{\partial \ell}{\partial \mu}
=-\frac{1}{2\sigma^2}\sum_{i=1}^N 2(x_i-\mu)(-1)
=\frac{1}{\sigma^2}\sum_{i=1}^N (x_i-\mu).
$$
The Fisher information is
$$
\mathcal{I}(\mu)
=\mathbb{E}\left[\left(\frac{\partial \ell}{\partial \mu}\right)^2\right]
=\mathbb{E}\left[\frac{1}{\sigma^4}\left(\sum_{i=1}^N (x_i-\mu)\right)^2\right].
$$
Because the $x_i$ are independent with $\mathbb{E}[x_i-\mu]=0$ and $\mathrm{Var}(x_i-\mu)=\sigma^2$,
$$
\mathrm{Var}\!\left(\sum_{i=1}^N (x_i-\mu)\right)=N\sigma^2,
$$
and the mean is zero, so
$$
\mathcal{I}(\mu)=\frac{1}{\sigma^4}\,N\sigma^2=\frac{N}{\sigma^2}.
$$

### 3 Cramér–Rao bound

For any unbiased estimator $\hat\mu$ of $\mu$,
$$
\mathrm{Var}(\hat\mu)\ge \frac{1}{\mathcal{I}(\mu)}=\frac{\sigma^2}{N}.
$$
This bound is **tight**: the sample mean $\bar x=\frac{1}{N}\sum_i x_i$ is unbiased and satisfies $\mathrm{Var}(\bar x)=\sigma^2/N$.

**If the assumptions are false, how to make them true.** If the estimator is biased, use the biased CRB (which includes bias-derivative terms); if regularity conditions fail (e.g., parameter-dependent support), CRB may not apply and alternative bounds (van Trees, Hammersley–Chapman–Robbins) may be needed. This changes the identity from an unbiased-information bound to a more general estimation bound.

### Numerical example

Let $\sigma=0.20$ and $N=50$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\mathrm{Var}(\hat\mu)\;[-]$ | $8.0000\times 10^{-4}$ | 0.0008 | 8.0000e-4 |
| $\mathrm{Std}(\hat\mu)\;[-]$ | $2.8284\times 10^{-2}$ | 0.0283 | 2.8284e-2 |

### 5 of 5 rigor addendum

#### Quantum Fisher information example and saturation condition

For a parametric family of quantum states $\rho(\theta)$, the quantum Fisher information is
$$
F_Q(\theta) = \mathrm{Tr}\!\left(\rho(\theta)\,L(\theta)^2\right),
$$
where the symmetric logarithmic derivative $L$ satisfies
$$
\frac{\partial \rho}{\partial \theta} = \frac{1}{2}\left(L\rho+\rho L\right).
$$

The quantum Cramér–Rao bound is
$$
\mathrm{Var}(\hat\theta)\ge \frac{1}{M\,F_Q(\theta)},
$$
for $M$ independent repetitions and locally unbiased estimators.

##### Worked qubit phase example

Let
$$
|\psi(\theta)\rangle = \frac{|0\rangle + e^{i\theta}|1\rangle}{\sqrt{2}},
\qquad
\rho(\theta)=|\psi(\theta)\rangle\langle\psi(\theta)|.
$$
This is a unitary family generated by $G=\frac{1}{2}\sigma_z$ acting on $|+\rangle$, so for pure states,
$$
F_Q = 4\,\mathrm{Var}(G) = 1.
$$
Therefore the quantum bound is $\mathrm{Var}(\hat\theta)\ge 1/M$.

A measurement saturates the bound when it is compatible with the symmetric logarithmic derivative eigenbasis, which for single-parameter pure-state families can often be realized with a projective measurement in an appropriate basis. For this phase family, measuring in the $X$ basis yields a classical Fisher information equal to 1, achieving the quantum value.

#### Reproducible computation

```python
import math

# Classical Fisher information for measuring |psi(theta)> in the X basis
theta = 0.3

# Probabilities in {|+x>, |-x>} basis
p_plus = (1.0 + math.cos(theta)) / 2.0
p_minus = (1.0 - math.cos(theta)) / 2.0

# Derivatives
dp_plus = -0.5 * math.sin(theta)
dp_minus = 0.5 * math.sin(theta)

I = (dp_plus**2) / p_plus + (dp_minus**2) / p_minus
print("Classical Fisher I =", I)

# Quantum Fisher for this family is 1
print("Quantum Fisher F_Q =", 1.0)
```

#### Primary sources

- Liu et al., review on quantum Fisher information, arXiv.
- Open quantum metrology lecture notes deriving the symmetric logarithmic derivative and saturation conditions.

---

## P23 MEAS: A Kraus map amplitude damping applied to a qubit density matrix

**Intuitive explanation.** If a qubit can spontaneously relax from $|1\rangle$ to $|0\rangle$, then populations and coherences change predictably, and the change can be encoded by a small set of matrices.

**Grad-level framing.** The most general Markovian, memoryless quantum evolution over a finite time step is a completely-positive trace-preserving (CPTP) map. Any CPTP map admits a Kraus operator-sum representation, and in the continuous-time weak-coupling limit the generator is of Gorini–Kossakowski–Sudarshan–Lindblad (GKSL) form.

### Assumptions, conventions, and validity domain

- **Quantum state.** $\rho$ is a density operator: $\rho\succeq 0$ and $\mathrm{Tr}(\rho)=1$ on a two-dimensional Hilbert space.
- **Channel family.** Amplitude damping parameter $p\in[0,1]$ specifies a one-parameter family of CPTP maps modeling energy relaxation to a (near) zero-temperature bath.
- **Basis.** Computational basis $\{|0\rangle,|1\rangle\}$ is chosen so that damping moves $|1\rangle\to|0\rangle$.
- **Markovian closure (optional).** In a continuous-time model with decay rate $\gamma$, one has $p(t)=1-e^{-\gamma t}$ under standard weak-coupling, memoryless assumptions.

### Symbolic derivation Kraus operators → CPTP constraints → state update → Lindblad limit

#### 1 Kraus representation and CPTP constraints

A linear map $\mathcal{E}$ is CPTP iff it can be written as
$$
\mathcal{E}(\rho)=\sum_{k} K_k \rho K_k^\dagger,
\qquad
\sum_k K_k^\dagger K_k = I,
$$
where $\{K_k\}$ are Kraus operators.

#### 2 Amplitude damping Kraus operators

One standard Kraus decomposition for amplitude damping with probability $p$ is
$$
K_0=\begin{bmatrix}1&0\\0&\sqrt{1-p}\end{bmatrix},
\qquad
K_1=\begin{bmatrix}0&\sqrt{p}\\0&0\end{bmatrix}.
$$
Trace preservation is immediate:
$$
K_0^\dagger K_0 + K_1^\dagger K_1
=\begin{bmatrix}1&0\\0&1-p\end{bmatrix}
+
\begin{bmatrix}p&0\\0&0\end{bmatrix}
=I.
$$

#### 3 Explicit action on a general qubit density matrix

Let
$$
\rho=
\begin{bmatrix}
\rho_{00} & \rho_{01}\\
\rho_{10} & \rho_{11}
\end{bmatrix},
\qquad
\rho_{10}=\rho_{01}^*,
\quad
\rho_{00}+\rho_{11}=1.
$$
Then
$$
\rho'=\mathcal{E}(\rho)=K_0\rho K_0^\dagger + K_1\rho K_1^\dagger
=\begin{bmatrix}
\rho_{00}+p\rho_{11} & \sqrt{1-p}\,\rho_{01}\\
\sqrt{1-p}\,\rho_{10} & (1-p)\rho_{11}
\end{bmatrix}.
$$

#### 4 Continuous-time Lindblad generator GKSL form

For a Markovian master equation,
$$
\dot{\rho}
=-\frac{i}{\hbar}[H,\rho]
+\sum_j\left(L_j\rho L_j^\dagger - \frac12\{L_j^\dagger L_j,\rho\}\right),
$$
where $\{L_j\}$ are jump operators. Pure amplitude damping at rate $\gamma$ corresponds to a single jump operator
$$
L=\sqrt{\gamma}\,\sigma_-,
\qquad
\sigma_- = |0\rangle\langle 1|.
$$
Solving the resulting ODE yields $p(t)=1-e^{-\gamma t}$ and reproduces the Kraus map above at each time $t$.

**If the assumptions are false, how to make them true.** If the bath has memory (non-Markovian), or if finite temperature is relevant, then amplitude damping requires additional channels (thermal excitation) and time-dependent kernels. To regain a controlled model, either (i) enlarge the system to include the relevant environment modes (unitary evolution on system+environment), or (ii) use a non-Markovian master equation with experimentally validated spectral density; the identity shifts from a semigroup CPTP map to a history-dependent quantum process.

### Numerical example

Let $\rho=|+\rangle\langle +|=\tfrac12\begin{bmatrix}1&1\\1&1\end{bmatrix}$ and $p=0.10$, so $\sqrt{1-p}=\sqrt{0.9}=0.9486832980505138$ and
$$
\rho'=
\begin{bmatrix}
0.5+0.1\cdot 0.5 & 0.9486832980505138\cdot 0.5\\
0.9486832980505138\cdot 0.5 & 0.9\cdot 0.5
\end{bmatrix}=
\begin{bmatrix}
0.55 & 0.4743416490252569\\
0.4743416490252569 & 0.45
\end{bmatrix}.
$$

| Entry | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\rho'_{11}$ | $5.5000\times 10^{-1}$ | 0.5500 | 5.5000e-1 |
| $\rho'_{12}$ | $4.7434\times 10^{-1}$ | 0.4743 | 4.7434e-1 |
| $\rho'_{21}$ | $4.7434\times 10^{-1}$ | 0.4743 | 4.7434e-1 |
| $\rho'_{22}$ | $4.5000\times 10^{-1}$ | 0.4500 | 4.5000e-1 |

### 5 of 5 rigor addendum

#### CPTP verification checklist

A map $\mathcal{E}$ on density matrices is a valid quantum channel when it is:

1. **Completely positive:** $\mathcal{E}\otimes \mathbb{I}$ maps positive operators to positive operators for all ancilla dimensions.
2. **Trace preserving:** $\mathrm{Tr}[\mathcal{E}(\rho)]=\mathrm{Tr}[\rho]$ for all $\rho$.

A practical monograph-grade checklist:

- If a Kraus representation is given,
  $$
  \mathcal{E}(\rho) = \sum_k A_k \rho A_k^\dagger,
  $$
  then complete positivity is automatic.

- Trace preservation holds if and only if
  $$
  \sum_k A_k^\dagger A_k = I.
  $$

- If no Kraus form is given, compute the Choi matrix
  $$
  J(\mathcal{E})=\sum_{i,j} |i\rangle\langle j|\otimes \mathcal{E}(|i\rangle\langle j|),
  $$
  and check $J(\mathcal{E})\succeq 0$ for complete positivity, and $\mathrm{Tr}_2 J(\mathcal{E}) = I$ for trace preservation.

#### Reproducible computation

```python
import numpy as np

# Amplitude damping channel as a worked CPTP check
gamma = 0.2  # control knob

A0 = np.array([[1.0, 0.0],
               [0.0, np.sqrt(1.0 - gamma)]])
A1 = np.array([[0.0, np.sqrt(gamma)],
               [0.0, 0.0]])

S = A0.T.conj() @ A0 + A1.T.conj() @ A1
print("Sum A_k^† A_k =\n", S)

assert np.allclose(S, np.eye(2))
```

#### Primary sources

- Open lecture notes on Kraus operators and the Kraus representation theorem, PDF.
- Quantum information course notes defining the Choi matrix test for complete positivity.

---

## P24 QFT: Field Euler–Lagrange equation → Klein–Gordon dispersion relation

**Intuitive explanation.** A wave can behave as if it has inertia (mass), changing its frequency–wavelength relation.

**Grad-level framing.** A Lagrangian density yields field equations via spacetime Euler–Lagrange; for a free scalar, this yields Klein–Gordon. (see References)

### Assumptions, conventions, and validity domain

- **Spacetime convention.** Minkowski metric signature $(+,-,-,-)$ and d’Alembertian $\Box=(1/c^2)\partial_t^2-\nabla^2$.
- **Field regularity.** $\phi$ is twice differentiable and variations vanish on the boundary (or fields fall off sufficiently fast at infinity).
- **Free field.** No interaction terms; adding interactions changes the dispersion and requires renormalization/effective-field reasoning.

### Symbolic derivation Lagrangian density → Euler–Lagrange → dispersion

Take
$$
\mathcal{L}=\frac12\left(\partial_\mu\phi\,\partial^\mu\phi - \frac{m^2 c^2}{\hbar^2}\phi^2\right).
$$
Euler–Lagrange for fields:
$$
\frac{\partial \mathcal{L}}{\partial \phi} - \partial_\mu\left(\frac{\partial \mathcal{L}}{\partial(\partial_\mu\phi)}\right)=0.
$$
Compute:
$$
\frac{\partial \mathcal{L}}{\partial \phi}= -\frac{m^2 c^2}{\hbar^2}\phi,\qquad
\frac{\partial \mathcal{L}}{\partial(\partial_\mu\phi)}=\partial^\mu\phi.
$$
Thus
$$
\left(\Box + \frac{m^2 c^2}{\hbar^2}\right)\phi=0,\qquad
\Box=\frac{1}{c^2}\partial_t^2-\nabla^2.
$$
For $\phi\sim e^{i(\mathbf{k}\cdot\mathbf{x}-\omega t)}$:
$$
\omega^2 = c^2k^2 + \left(\frac{mc^2}{\hbar}\right)^2.
$$

**If the assumptions are false, how to make them true.** With interactions, dispersion renormalizes; in weak coupling you recover an effective mass via perturbation theory, shifting identity from free to effective field theory.

### Numerical example

Take $m=1\ \mathrm{eV}/c^2$ and $k=1.0\times 10^6\ \mathrm{m^{-1}}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $m\;[\mathrm{kg}]\ (1\ \mathrm{eV}/c^2)$ | $1.7827\times 10^{-36}$ | 0.0000000000000000000000000000000000017827 | 1.7827e-36 |
| $\omega\;[\mathrm{rad/s}]$ | $1.5486\times 10^{15}$ | 1,548,563,559,846,944.0000 | 1.5486e15 |

### 5 of 5 rigor addendum

#### Units and natural-unit conventions

In relativistic quantum field theory, it is common to set $\hbar=c=1$. When doing so:

- energy, mass, and frequency share units,
- length and time are inverse-energy units,
- and the action is dimensionless in the exponent $e^{iS}$.

To restore units, insert factors of $\hbar$ and $c$ by dimensional analysis. For example,
$$
\omega^2 = k^2 + m^2
\quad\text{in}\ \hbar=c=1
\quad\Rightarrow\quad
(\hbar\omega)^2 = (\hbar c k)^2 + (mc^2)^2
\ \text{in SI}.
$$

#### Interacting modification example and identity shift

The free Klein–Gordon Lagrangian is
$$
\mathcal{L}_0 = \frac12 (\partial_\mu \phi)(\partial^\mu \phi) - \frac12 m^2 \phi^2.
$$
An interacting $\phi^4$ theory adds
$$
\mathcal{L} = \mathcal{L}_0 - \frac{\lambda}{4!}\phi^4.
$$
The Euler–Lagrange field equation becomes
$$
(\Box + m^2)\phi + \frac{\lambda}{3!}\phi^3 = 0.
$$

This illustrates a key “identity shift” rule:

- the free dispersion relation is not a theorem about the interacting theory,
- in quantum theory, interactions renormalize parameters, so the physical mass and the propagator pole structure shift.

#### Reproducible computation

```python
import math

# Dispersion relation check in natural-unit style
m = 2.0   # mass parameter, control knob
k = 3.0   # momentum magnitude, control knob

omega = math.sqrt(k**2 + m**2)
print("omega =", omega)
```

#### Primary sources

- Open quantum field theory lecture notes stating natural-unit conventions and the Klein–Gordon derivation, PDF.
- Open materials discussing interacting scalar field theory and renormalization as identity shift.

---

## P25 T M: Transfer matrix of a single thin film at normal incidence reflection

**Intuitive explanation.** Partial reflections in a thin layer interfere, which can boost or cancel reflection.

**Grad-level framing.** Boundary matching across layered media composes via transfer matrices; reflection follows from the total matrix. (see References)

### Assumptions, conventions, and validity domain

- **Optical regime.** Normal incidence, isotropic, non-magnetic media ($\mu_r=1$); TE and TM polarizations coincide at normal incidence.
- **Admittance convention.** Use **optical admittance** $\eta_j := n_j$ for non-magnetic media at normal incidence (normalized so that boundary conditions take a symmetric form).
- **Loss.** Refractive indices may be complex $n_j\in\mathbb{C}$ to model absorption; the worked example uses real $n_j$.
- **Coherence.** The film is coherent (thickness smaller than coherence length of illumination) so interference is phase-stable.

### Symbolic derivation Layer matrix → reflection coefficient

We derive the single-layer transfer matrix and the resulting reflection coefficient at normal incidence.

### 1 Field representation and boundary conditions normal incidence

At normal incidence in non-magnetic media ($\mu_r=1$), a plane wave in medium $j$ can be written as
$$
E_j(z) = E_j^{+}e^{ik_j z} + E_j^{-}e^{-ik_j z},
\qquad
H_j(z) = \eta_j\left(E_j^{+}e^{ik_j z} - E_j^{-}e^{-ik_j z}\right),
$$
where $k_j = 2\pi n_j/\lambda$ and $\eta_j$ is the **optical admittance**. Under the chosen normalization for non-magnetic media at normal incidence,
$$
\eta_j = n_j,
$$
which makes the continuity conditions symmetric.

At each interface, tangential $E$ and $H$ are continuous:
$$
E\ \text{continuous},\qquad H\ \text{continuous}.
$$

### 2 Transfer matrix for a homogeneous layer

For a layer (medium 1) of thickness $d$, define the phase thickness
$$
\delta := k_1 d = \frac{2\pi n_1 d}{\lambda}.
$$
The transfer matrix relates the field vector $\begin{bmatrix}E\\H\end{bmatrix}$ at the entrance of the layer to that at the exit:
$$\begin{bmatrix}E\\H\end{bmatrix}_{z=0}=
M
\begin{bmatrix}E\\H\end{bmatrix}_{z=d},
$$
with
$$
M=
\begin{bmatrix}
\cos\delta & \frac{i}{\eta_1}\sin\delta \\
i\eta_1\sin\delta & \cos\delta
\end{bmatrix}.
$$

### 3 Reflection coefficient from the total matrix

Let medium 0 be incident (admittance $\eta_0$) and medium 2 be substrate (admittance $\eta_2$). Define the input admittance looking into the stack:
$$
\eta_{\mathrm{in}} := \frac{H}{E}\Big|_{z=0}.
$$
Using the transfer matrix and imposing that the transmitted wave in the substrate is forward-only (no incoming wave from $z=+\infty$), one obtains
$$\eta_{\mathrm{in}}=
\frac{M_{21}+\eta_2 M_{22}}{M_{11}+\eta_2 M_{12}}.
$$
Then the Fresnel-form reflection coefficient at the entrance is
$$
r=\frac{\eta_0-\eta_{\mathrm{in}}}{\eta_0+\eta_{\mathrm{in}}}.
$$
Substituting $\eta_{\mathrm{in}}$ and simplifying yields the commonly quoted closed form:
$$
r = \frac{\eta_0 M_{11} + \eta_0\eta_2 M_{12} - M_{21} - \eta_2 M_{22}}
{\eta_0 M_{11} + \eta_0\eta_2 M_{12} + M_{21} + \eta_2 M_{22}},
\qquad
R=|r|^2.
$$

### 4 Loss and polarization notes

- If the film is absorbing, use complex $n_1$ and therefore complex $\eta_1$ and $\delta$; the same algebra applies.
- At oblique incidence, TE and TM polarizations have different admittances and phase factors; the normal-incidence simplification used here no longer holds.

**If the assumptions are false, how to make them true.** For oblique incidence, TE and TM polarizations require different admittances and phase thicknesses; for incoherent illumination, intensities rather than fields must be composed (no stable phase). Including these effects changes the identity from coherent normal-incidence transfer matrices to polarization-aware and/or incoherent multilayer optics.

### Numerical example

Air–film–substrate at normal incidence:
$n_0=1.0$, $n_1=1.5$, $n_2=3.5$, thickness $d=100\ \mathrm{nm}$, wavelength $\lambda=550\ \mathrm{nm}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $\Re\{r\}\;[-]$ | $1.9598\times 10^{-1}$ | 0.1960 | 1.9598e-1 |
| $\Im\{r\}\;[-]$ | $-1.2685\times 10^{-1}$ | -0.1268 | -1.2685e-1 |
| $\lvert r\lvert \;[-]$ | $2.3345\times 10^{-1}$ | 0.2335 | 2.3345e-1 |
| $R=\lvert r \lvert^2\;[-]$ | $5.4499\times 10^{-2}$ | 0.0545 | 5.4499e-2 |
| $R\;[\%]$ | $5.4499\times 10^{0}$ | 5.4499 | 5.4499e0 |

### 5 of 5 rigor addendum

#### Oblique incidence and TE TM split

At normal incidence, polarization does not matter. At oblique incidence, transfer-matrix calculations split into transverse electric and transverse magnetic polarizations.

For an interface between indices $n_i$ and $n_j$ with incidence angle $\theta_i$ and transmission angle $\theta_j$ satisfying Snell’s law, Fresnel reflection coefficients are:

- Transverse electric:
$$
r_s = \frac{n_i\cos\theta_i - n_j\cos\theta_j}{n_i\cos\theta_i + n_j\cos\theta_j}.
$$

- Transverse magnetic:
$$
r_p = \frac{n_j\cos\theta_i - n_i\cos\theta_j}{n_j\cos\theta_i + n_i\cos\theta_j}.
$$

In a transfer-matrix formulation, this enters through the polarization-dependent admittance, so the same matrix structure applies, but with different effective impedances.

#### Incoherent limit companion pattern

The main text assumes coherent interference across layers. If thickness fluctuations, finite source linewidth, or scattering destroy coherence, then phase averaging replaces field-amplitude composition with intensity composition.

A practical monograph-grade rule:

- if optical path variations exceed coherence length, treat layers incoherently, and average over phase.

#### Reproducible computation

```python
import cmath
import math

# Normal incidence reflection example, coherent
n0 = 1.0
n1 = 1.5
r = (n0 - n1) / (n0 + n1)
R = abs(r)**2
print("R =", R)

# Oblique incidence TE example
theta_i = math.radians(30.0)
# Snell: n0 sin(theta_i) = n1 sin(theta_t)
theta_t = math.asin(n0 * math.sin(theta_i) / n1)

rs = (n0*math.cos(theta_i) - n1*math.cos(theta_t)) / (n0*math.cos(theta_i) + n1*math.cos(theta_t))
Rs = rs**2
print("Rs (TE) =", Rs)
```

#### Primary sources

- Byrnes, *Multilayer optical calculations*, arXiv.
- Open thin-film optics lecture notes deriving transfer matrices and TE TM Fresnel coefficients.

---

## P26 NUM: Explicit finite-difference diffusion update and its stability condition

**Intuitive explanation.** If you take too large a time step while smoothing, the numbers can overshoot and blow up.

**Grad-level framing.** Von Neumann analysis of FTCS gives a stability condition on $r=\alpha\Delta t/\Delta x^2$.

### Assumptions, conventions, and validity domain

- **Discretization.** Uniform grid with spacing $\Delta x$ and timestep $\Delta t$; explicit forward-time centered-space (FTCS) update.
- **Stability analysis.** Von Neumann analysis assumes periodic or infinite domain so Fourier modes form a basis; coefficients are constant.
- **PDE model.** Linear diffusion with constant $\alpha$.

### Symbolic derivation Discretize → amplification factor → stability

For $u_t=\alpha u_{xx}$, FTCS is
$$
u_i^{n+1}=u_i^n + r\left(u_{i+1}^n-2u_i^n+u_{i-1}^n\right),
\qquad r=\frac{\alpha\Delta t}{\Delta x^2}.
$$
Assume mode $u_i^n = G^n e^{ik i\Delta x}$. Then
$$
G = 1 + r\left(e^{ik\Delta x}-2+e^{-ik\Delta x}\right)
=1-4r\sin^2\left(\frac{k\Delta x}{2}\right).
$$
Require $|G|\le 1$ for all $k$, so the worst case gives
$$
|1-4r|\le 1\Rightarrow 0\le r\le \frac12.
$$

**If the assumptions are false, how to make them true.** If you need larger $\Delta t$, switch to implicit stepping (backward Euler, Crank–Nicolson); identity shifts from explicit conditionally stable to implicit unconditionally stable.

### Numerical example

Let $\alpha=1.0\times 10^{-5}\ \mathrm{m^2/s}$, $\Delta x=1.0\ \mathrm{mm}$, $\Delta t=0.040\ \mathrm{s}$, and $(u_{i-1}^n,u_i^n,u_{i+1}^n)=(0,1,0)$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $r=\alpha\Delta t/\Delta x^2\;[-]$ | $4.0000\times 10^{-1}$ | 0.4000 | 4.0000e-1 |
| $u_i^{n+1}\;[-]$ | $2.0000\times 10^{-1}$ | 0.2000 | 2.0000e-1 |

### 5 of 5 rigor addendum

#### Consistency, stability, convergence and Lax equivalence

For linear well-posed initial value problems, a central theorem in numerical analysis is:

- **Lax equivalence principle:** for a consistent finite difference approximation of a linear well-posed problem, stability is equivalent to convergence.

In practice, this means:

1. Show the scheme is **consistent**: the local truncation error goes to zero as $\Delta t,\Delta x\to 0$.
2. Show the scheme is **stable**: amplification factors remain bounded.
3. Conclude the scheme is **convergent**: numerical solution approaches the true solution.

This upgrades “stability analysis” into a convergence guarantee when the assumptions are satisfied.

#### Reproducible computation

```python
# Control knobs
alpha = 1.0e-5
dx = 1.0e-3
dt = 0.04

r = alpha * dt / (dx**2)
print("r =", r)

if r <= 0.5:
    print("FTCS diffusion stability condition satisfied")
else:
    print("unstable: reduce dt or increase dx")
```

#### Primary sources

- Lecture notes on the Lax–Richtmyer equivalence theorem and convergence of finite difference methods, PDF.
- Open numerical PDE notes covering von Neumann stability for diffusion schemes.

---
## P27 STAT: Boltzmann distribution from maximum entropy + a two-level partition function

**Intuitive explanation.** At fixed temperature, higher-energy states are less likely, with exponential suppression.

**Grad-level framing.** Maximizing entropy under normalization and mean-energy constraints yields the canonical distribution; the partition function normalizes and generates thermodynamics. (see References)

### Assumptions, conventions, and validity domain

- **Maximum entropy principle.** Choose the distribution $\{p_i\}$ that maximizes Shannon entropy subject to normalization and fixed mean energy.
- **Energy spectrum.** Discrete levels $E_i$ are assumed for clarity; the derivation extends to continuous spectra with integrals.
- **Thermodynamic identification.** The Lagrange multiplier $\beta$ is identified with $1/(k_BT)$ by matching with thermodynamic relations (stated explicitly).

### Symbolic derivation Max entropy → multipliers → Boltzmann weights

We maximize entropy subject to normalization and mean-energy constraints and then identify the thermodynamic meaning of the multiplier.

### 1 Constrained maximization problem

Maximize Shannon entropy
$$
S(p) = -\sum_i p_i\ln p_i
$$
over $p_i\ge 0$, subject to
$$
\sum_i p_i = 1,
\qquad
\sum_i p_i E_i = U.
$$

### 2 Lagrangian and stationarity

Form the Lagrangian (objective + constraints)
$$\mathcal{J}(p,\alpha,\beta)
=-\sum_i p_i\ln p_i
-\alpha\left(\sum_i p_i-1\right)
-\beta\left(\sum_i p_iE_i-U\right).
$$
Differentiate with respect to $p_i$ and set to zero:
$$
\frac{\partial\mathcal{J}}{\partial p_i}
=-(\ln p_i+1)-\alpha-\beta E_i = 0
\quad\Rightarrow\quad
p_i = e^{-1-\alpha}e^{-\beta E_i}.
$$

### 3 Normalization and the partition function

Define the partition function
$$
Z(\beta):=\sum_i e^{-\beta E_i}.
$$
Normalization $\sum_i p_i=1$ forces $e^{-1-\alpha}=1/Z$, hence
$$
p_i = \frac{e^{-\beta E_i}}{Z(\beta)}.
$$

### 4 Thermodynamic identification of $\beta$

The mean energy under $p$ is
$$
U(\beta)=\sum_i p_i E_i = -\frac{\partial}{\partial\beta}\ln Z(\beta).
$$
In equilibrium thermodynamics, the Legendre relation between entropy and energy implies
$$
\frac{\partial S}{\partial U}=\frac{1}{T}.
$$
Carrying out the derivative of the maximized entropy with respect to $U$ yields $\beta = 1/(k_BT)$. Therefore the maximum-entropy distribution consistent with equilibrium at temperature $T$ is
$$
p_i = \frac{e^{-E_i/(k_BT)}}{Z},
\qquad
Z=\sum_i e^{-E_i/(k_BT)}.
$$

**If the assumptions are false, how to make them true.** If particle number fluctuates, include a chemical potential and use the grand canonical ensemble; if the system is driven far from equilibrium, maximum entropy with equilibrium constraints is not the correct identity and one must use non-equilibrium ensembles or maximum caliber. These changes shift the identity from canonical equilibrium to grand-canonical or non-equilibrium statistical mechanics.

### Numerical example: two-level system

Let $E_0=0$ and $E_1=0.10\ \mathrm{eV}$ at $T=300\ \mathrm{K}$.

| Quantity | Conventional sci. | Decimal | e-notation |
| :--- | :--- | :--- | :--- |
| $Z\;[-]$ | $1.0209\times 10^{0}$ | 1.0209 | 1.0209e0 |
| $p_0\;[-]$ | $9.7953\times 10^{-1}$ | 0.9795 | 9.7953e-1 |
| $p_1\;[-]$ | $2.0469\times 10^{-2}$ | 0.0205 | 2.0469e-2 |
| $U\;[\mathrm{J}]$ | $3.2795\times 10^{-22}$ | 0.00000000000000000000032795 | 3.2795e-22 |
| $U\;[\mathrm{eV}]$ | $2.0469\times 10^{-3}$ | 0.0020 | 2.0469e-3 |

---

### 5 of 5 rigor addendum

#### Grand canonical ensemble extension

The canonical ensemble maximizes entropy with a mean-energy constraint. The grand canonical ensemble adds a mean-particle-number constraint.

Maximize entropy subject to
$$
\sum_i p_i = 1,\qquad \sum_i p_i E_i = \langle E\rangle,\qquad \sum_i p_i N_i = \langle N\rangle.
$$
The solution is
$$
p_i = \frac{1}{\Xi}\exp\!\left(-\beta(E_i-\mu N_i)\right),
\qquad
\Xi = \sum_i \exp\!\left(-\beta(E_i-\mu N_i)\right),
$$
where $\mu$ is the chemical potential and $\Xi$ is the grand partition function.

This explicitly extends the “identity” of the distribution: canonical is a slice of the grand canonical family with fixed $N$.

#### Maximum caliber pointer as a nonequilibrium extension

Maximum entropy is a static inference rule. A nonequilibrium analog is maximum caliber, which maximizes *path entropy* under constraints on dynamical observables, such as transition counts or fluxes, producing Markovian dynamics as the maximum-entropy path measure under appropriate constraints.

This is an identity shift: from distributions over states to distributions over trajectories.

#### Reproducible computation

```python
import math

# Two-level canonical example
kB = 1.380649e-23

# Control knobs
E0 = 0.0
E1 = 2.0e-21   # joules
T = 300.0

beta = 1.0 / (kB * T)
Z = math.exp(-beta * E0) + math.exp(-beta * E1)

p0 = math.exp(-beta * E0) / Z
p1 = math.exp(-beta * E1) / Z

print("Z =", Z)
print("p0, p1 =", p0, p1)
```

#### Primary sources

- Open statistical mechanics notes on canonical and grand canonical ensembles.
- Dixit et al. and related open-access works on maximum caliber and nonequilibrium path entropy.

---

## Acronym glossary 

| Mnemonic | Expansion |
| :--- | :--- |
| DLT | Definitions → Lemma → Theorem (→ Proof) |
| MGSI | Model → Governing equations → (Boundary/Initial conditions) → Solve → Interpret |
| SCALE | Non-dimensionalization → scaling laws → regimes |
| SYM | Symmetry (→ conservation laws / selection rules) |
| VAR | Variational principle (→ Euler–Lagrange/ stationarity) |
| EIG | Eigenproblem (→ diagonalization, spectrum, modes) |
| PERT | Perturbation theory |
| LR | Linear response |
| NOISE | Stochastic noise/ spectral density |
| IO | Input–output/ scattering |
| CIRC | Circuit modeling/ network synthesis |
| DDP | Drift–Diffusion–Poisson (semiconductor transport core) |
| BAND | Band theory |
| SC | Superconductivity |
| MAG | Micromagnetics |
| SPIN | Spin transport/ spin–orbit torque |
| FORMS | Differential forms |
| GA | Geometric (Clifford) algebra |
| GAUGE | Gauge theory/ topology |
| INFO | Information theory |
| CRYPTO | Cryptography |
| EXP | Experimental pipeline |
| QFI | Quantum Fisher information (and Fisher information) |
| MEAS | Quantum measurement / open systems |
| QFT | Quantum field theory |
| TM | Transfer matrix |
| NUM | Numerics/ numerical simulation |
| STAT | Statistical mechanics |

### General technical acronym glossary

| Acronym | Expansion | Notes |
| :--- | :--- | :--- |
| AC | Alternating Current | Versus DC. |
| DC | Direct Current | Time-independent limit. |
| ODE | Ordinary Differential Equation | Finite-dimensional dynamical systems. |
| PDE | Partial Differential Equation | Field evolution, such as diffusion and waves. |
| IC | Initial Condition | Values specified at an initial time. |
| BC | Boundary Condition | Values or fluxes specified at boundaries. |
| LTI | Linear Time-Invariant | Enables convolution and transfer functions. |
| PSD | Power Spectral Density | Must specify one-sided vs two-sided convention. |
| FFT | Fast Fourier Transform | Algorithmic acceleration of discrete Fourier transforms. |
| EMF | Electromotive Force | Loop integral of force per unit charge. |
| TE | Transverse Electric | “s-polarized” in optics. |
| TM | Transverse Magnetic | “p-polarized” in optics. |
| KL | Kullback–Leibler | Divergence in information theory. |
| CPTP | Completely Positive Trace Preserving | Valid quantum channel condition. |
| SLD | Symmetric Logarithmic Derivative | Defines quantum Fisher information. |
| QFI | Quantum Fisher Information | Upper bound on classical Fisher information over measurements. |
| IND-CPA | Indistinguishability Under Chosen Plaintext Attack | Standard symmetric-encryption security notion. |
| PRF | Pseudorandom Function | Cryptographic primitive used in reductions. |
| PRP | Pseudorandom Permutation | Block-cipher idealization primitive. |
| RCSJ | Resistively and Capacitively Shunted Junction | Standard Josephson environment model. |
| LLG | Landau–Lifshitz–Gilbert | Magnetization dynamics equation. |
| FMR | Ferromagnetic Resonance | Resonant precession of magnetization. |
| GUM | Guide to the Expression of Uncertainty in Measurement | Often referenced via JCGM. |
| JCGM | Joint Committee for Guides in Metrology | Maintains the GUM series. |

## Etymology & naming notes

- *Entropy* comes from Greek roots, often glossed as “in” + “turning,” which is helpful when you remember that maximizing entropy turns constraints into exponential-family distributions.
- *Quasi-* (as in *quasi-neutral*, *quasiparticle*) derives from Latin “as if,” which, in modeling, signals an approximation class that becomes exact in a limit.
- *Holonomy* (Berry phase) is literally a “whole-path” effect: you only know it after you go around the loop.
- *Rotor* in geometric algebra is intentionally parallel to “rotator,” emphasizing action by sandwiching rather than by coordinate matrices.

## Mostly open references

| Reference | URL |
| :--- | :--- |
| Ciani & DiVincenzo (2023). *Quantum Electrical Circuits* | https://doi.org/10.48550/arXiv.2312.05329 |
| Lasenby (2017). *Geometric Algebra as a Unifying Language for Physics and Engineering* | https://doi.org/10.1007/s00006-016-0700-z |
| Chew (2013). *Quantum Mechanics Made Simple* | https://engineering.purdue.edu/wcchew/course/QMAll20161206.pdf |
| D’Ariano, Chiribella, Perinotti (2017). *Quantum Theory from First Principles* | https://doi.org/10.1017/9781107338340 |
| Manenti & Motta (2023). *Quantum Information Science* | https://doi.org/10.1093/oso/9780198787488.001.0001 |
| Vaz & Rocha (2016). *Clifford Algebra, Geometric Algebra, and Applications* | https://doi.org/10.48550/arXiv.0907.5356 |
| MIT OCW (2006). *Mathematical Methods for Engineers II* (Calculus of Variations) | https://ocw.mit.edu/courses/18-086-mathematical-methods-for-engineers-ii-spring-2006/e94c05947ed036cd6ad0150102087062_am72.pdf |
| MIT OCW (2023). *Matrix Calculus for Machine Learning* | https://ocw.mit.edu/courses/18-s096-matrix-calculus-for-machine-learning-and-beyond-january-iap-2023/mit18_s096iap23_lec10.pdf |
| MIT OCW (2011). *Intro to PDEs* (Lagrangian Field Theories) | https://ocw.mit.edu/courses/18-152-introduction-to-partial-differential-equations-fall-2011/7ccea8a23acf9ae7130456f5da63b2ba_MIT18_152F11_lec_21_23.pdf |
| MIT Circuits (2023). *Thévenin/Norton Equivalents* | https://circuits.mit.edu/_static/S23/handouts/lec03b/lecture03b.pdf |
| NIST. *Quantum Locking Ranges* (Josephson Junction Frequency) | https://www.nist.gov/ctl/rf-technology-division/superconductive-electronics-group/quantum-locking-ranges |
| Behr et al. / NIST (2012). *Josephson Array Voltage Standards* | https://pmc.ncbi.nlm.nih.gov/articles/PMC4959396/ |
| NIST (2019). *Johnson Noise Thermometry* | https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=926958 |
| Georgia Tech (Mukherjee). *Drift–Diffusion Derivation* | https://alan.ece.gatech.edu/ECE6451/Lectures/StudentLectures/Mukherjee_6p3_DriftDiffusion.pdf |
| UMD (Goldsman & Darmody). *Device Physics: Diode Equation Derivation* | https://user.eng.umd.edu/~neil/enee704/Goldsman_Darmody_Intro_QM_Dev_Phys.pdf |
| Ly et al. (2017). *Tutorial on Fisher Information* | https://doi.org/10.48550/arXiv.1705.01064 |
| Ma et al. (2010). *Introduction to Quantum Fisher Information* | https://doi.org/10.48550/arXiv.1008.2417 |
| Sinova et al. (2015). *Spin Hall Effect* | https://doi.org/10.48550/arXiv.1411.3249 |
| Brizard (2020). *Improving Student Understanding of Electrodynamics: Differential Forms* | https://doi.org/10.48550/arXiv.2009.10356 |
| Topp et al. (2017). *Non-Abelian Geometric Phases Carried by the Spin Fluctuation Tensor* | https://doi.org/10.48550/arXiv.1702.08564 |
| van Erven & Harremos (2014). *Rényi Divergence and Kullback-Leibler Divergence* | https://doi.org/10.48550/arXiv.1206.2459 |
| Chiribella et al. (2013). *Microcanonical Origin of the Maximum Entropy Principle for Open Systems* | https://doi.org/10.48550/arXiv.1206.5888 |
| Rosanov (2020). *Transfer Matrix in Scattering Theory* | https://doi.org/10.48550/arXiv.2009.10507 |
| Chappell et al. (2022). *Rotations in Classical Mechanics Using Geometric Algebra* | https://doi.org/10.48550/arXiv.2210.16803 |
| Cohen (1960). *A Coefficient of Agreement for Nominal Scales* | https://doi.org/10.1177/001316446002000104 |
| Krippendorff (2011). *Computing Krippendorff’s Alpha-Reliability* | https://repository.upenn.edu/items/034a6030-c584-4d14-9d3d-7b7e8d16df20 |
| Byrnes (2016). *Multilayer Optical Calculations* | https://doi.org/10.48550/arXiv.1603.02720 |
| Liu et al. (2019). *Quantum Fisher Information Matrix and Multiparameter Estimation* | https://doi.org/10.1088/1751-8121/ab5d4d |
| Dixit et al. (2018). *Perspective: Maximum Caliber is a General Variational Principle* | https://doi.org/10.1063/1.5012990 |
| NIST (2016). *The NIST Uncertainty Machine* (TN 1900) | https://doi.org/10.6028/NIST.TN.1900 |
| Dingle (1956). *Notes on Fermi-Dirac Integrals* | https://doi.org/10.48550/arXiv.0811.0116 |
| Lax & Richtmyer (1956). *Survey of the Stability of Linear Finite Difference Equations* | https://doi.org/10.1002/cpa.3160090206 |
| MIT OCW (2018). *Adiabatic Approximation* (Quantum Physics III) | https://ocw.mit.edu/courses/8-06-quantum-physics-iii-spring-2018/resources/mit8_06s18ch6/ |

---

## Creative Commons Attribution 4.0 International

**Copyright © 2025 Onri Jay Benally**

This work is licensed under the Creative Commons Attribution 4.0 International License. 
To view a copy of this license, visit http://creativecommons.org/licenses/by/4.0/ or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

### You are free to:

* **Share** — copy and redistribute the material in any medium or format.
* **Adapt** — remix, transform, and build upon the material for any purpose, even commercially.

The licensor cannot revoke these freedoms as long as you follow the license terms.

### Under the following terms:

* **Attribution** — You must give appropriate credit to **Onri Jay Benally**, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
* **No additional restrictions** — You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.
