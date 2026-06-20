# Spectral and Finite Element Analysis of the Neumann Wave Equation

A scientific computing project on finite element approximation, spectral analysis, and resonance phenomena for the heat equation and the Neumann wave equation on complex geometries.

The project combines Continuous Galerkin Finite Element Methods (CG-FEM), sparse linear algebra, generalized eigenvalue problems, modal decomposition, and numerical visualization to study how geometry influences diffusion, wave propagation, vibration modes, and resonance.

---

## Interactive Notebook

The full implementation, numerical experiments, and visualizations are available in Google Colab:

[Open in Colab](https://colab.research.google.com/drive/1OEPzWh7cVSVt88cT9V-XXMpkW8bZgQay?usp=sharing)

The notebook includes:

- finite element assembly
- heat equation simulation
- Neumann wave equation simulation
- spectral analysis of the Neumann Laplacian
- generalized eigenvalue problems
- resonance experiments
- frequency response curves
- modal decomposition
- visualization of eigenmodes and wave solutions

---

## Project Overview

This project studies two classical partial differential equations using the Continuous Galerkin Finite Element Method.

### Heat Equation

The transient heat equation is given by

```math
\frac{\partial u}{\partial t} - \Delta u = 0.
```

After finite element discretization, the semi-discrete system becomes

```math
M \frac{dU}{dt} + K U = 0,
```

where:

- `M` is the mass matrix
- `K` is the stiffness matrix
- `U` is the vector of finite element coefficients

The resulting system is integrated using an explicit Euler time-stepping scheme.

### Neumann Wave Equation

The main focus of the project is the forced wave equation

```math
u_{tt} - \Delta u = g(x,y)\cos(\omega t),
```

with homogeneous Neumann boundary conditions:

```math
\frac{\partial u}{\partial n} = 0.
```

After finite element discretization, the system becomes

```math
M \ddot{U} + K U = F(t).
```

The numerical solution is computed using a second-order central difference scheme.

---

## Spectral Analysis

A central part of the project is the spectral study of the Neumann Laplacian.

The natural vibration modes are obtained by solving the generalized eigenvalue problem

```math
K \phi = \lambda M \phi,
```

where:

- `K` is the stiffness matrix
- `M` is the mass matrix
- `lambda` are the eigenvalues
- `phi` are the eigenfunctions

The natural frequencies are then given by

```math
\omega_k = \sqrt{\lambda_k}.
```

These frequencies are used to identify resonant forcing regimes and analyze the dynamic response of the system.

---

## Numerical Methodology

### Finite Element Assembly

The project implements the construction of:

- mass matrix `M`
- stiffness matrix `K`
- load vectors
- sparse matrix representations

using Continuous Galerkin finite elements and numerical quadrature.

### Sparse Linear Algebra

Sparse matrix methods are used to make the computations efficient. In particular, sparse LU factorization is used to apply the inverse mass matrix:

```math
M^{-1}v.
```

### Stability and Spectral Radius

The largest eigenvalue of

```math
M^{-1}K
```

is estimated using power iteration. This is used to select stable time steps for explicit time integration.

### Resonance Analysis

The wave equation is solved for forcing frequencies close to the natural frequencies:

```math
\omega_k = \sqrt{\lambda_k}.
```

This allows the study of:

- resonance amplification
- dominant vibration modes
- frequency response behavior
- geometry-dependent wave propagation

### Modal Decomposition

The numerical solution can be interpreted through the expansion

```math
u(x,t) = \sum_{k=1}^{N} a_k(t)\phi_k(x),
```

where each coefficient `a_k(t)` describes the contribution of one vibration mode.

---

## Geometries Studied

### Circular Inclusion in a Square Domain

Used for heat equation simulations and diffusion experiments.

### Thin Dumbbell Domain

Used for spectral analysis and resonance studies of the Neumann wave equation.

### Thick Dumbbell Domain

Used to compare the influence of geometry on:

- eigenvalues
- eigenmodes
- resonant frequencies
- wave propagation
- mode localization

---

## Main Results

The project demonstrates:

- finite element approximation of heat diffusion
- construction of mass and stiffness matrices
- numerical solution of the forced Neumann wave equation
- computation of Neumann Laplacian eigenmodes
- solution of generalized eigenvalue problems
- identification of natural and resonant frequencies
- comparison between thin and thick dumbbell geometries
- visualization of vibration modes and wave propagation
- interpretation through modal decomposition

---

## Main Libraries

### Scientific Computing

- NumPy
- SciPy
- Matplotlib

### Numerical Linear Algebra

- `scipy.linalg.eigh`
- `scipy.sparse.linalg.splu`
- sparse matrix routines from `scipy.sparse`

### Finite Element Implementation

The project uses custom finite element routines for:

- mesh handling
- Continuous Galerkin discretization
- numerical quadrature
- local-to-global matrix assembly
- sparse matrix construction

---

## Scientific Topics

- Finite Element Methods
- Numerical PDEs
- Scientific Computing
- Sparse Linear Algebra
- Generalized Eigenvalue Problems
- Spectral Analysis
- Neumann Boundary Conditions
- Wave Propagation
- Resonance Phenomena
- Modal Decomposition

---

## Repository Structure

```text
.
├── FEM_PROJECT.ipynb
├── Project_Report.pdf
└── README.md
```

---

## Author

Abou Bakr Al Ajami  
M2 Mathematics, Modeling and Simulation  
