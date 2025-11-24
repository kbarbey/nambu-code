# Nambu-code

A research-oriented **3D magnetohydrodynamics (MHD)** code based on the **Nambu bracket** formulation of ideal MHD, with optional **dissipative** (metriplectic) extensions.

This project aims to explore **structure-preserving discretizations** of the MHD equations using the Hamiltonian–Casimir–Nambu framework described in Fukumoto & Zou (2023). The long-term goal is a numerical scheme that:

- preserves the **Hamiltonian** (energy) and ideal **Casimirs** (mass, entropy, magnetic helicity, cross-helicity) in the ideal limit,
- allows controlled **viscous** and **resistive** dissipation,
- provides a testbed for new geometric integrators,
- functions as a clean, inspectable research code (not yet a production solver).

---

## ✨ Features (current & planned)

### ✔️ Current skeleton
- Lightweight Python package structure (`src/nambu_mhd3d`)
- 3D periodic cubic domain
- Spectral differential operators: `grad`, `div`, `curl`, `laplacian`
- Field container for `ρ`, `s`, `v`, `B`
- Hamiltonian + Casimir diagnostics
- Dissipative operator stubs (ν, η)
- RK4 time integration
- Clean project layout for future expansion

### 🚧 In progress
- Standard ideal MHD right-hand side (RHS)
- Discrete Nambu brackets reproducing ideal MHD
- Magnetic vector potential calculation (for magnetic helicity)
- Tests: Orszag–Tang, Alfvén waves, random-box turbulence

### 🎯 Future (research goals)
- Full discrete Nambu bracket for \((M, \rho, s, B)\)
- Metriplectic extension for physical dissipation
- Energy-preserving / helicity-preserving time integrators
- Domain decomposition + MPI for parallel runs
- Diagnostics: spectra, invariants, structure functions

---

## 📁 Project Structure
nambu_mhd3d/
├── pyproject.toml
├── README.md
├── src/
│ └── nambu_mhd3d/
│ ├── config.py
│ ├── grid.py
│ ├── fields.py
│ ├── operators.py
│ ├── hamiltonian.py
│ ├── nambu.py
│ ├── dissipative.py
│ ├── rhs.py
│ ├── time_integrators.py
│ └── diagnostics.py (planned)
└── examples/
├── run_random_box.py
└── run_orszag_tang.py (planned)


---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOURNAME/nambu_mhd3d.git
cd nambu_mhd3d
pip install -e .
python examples/run_random_box.py

