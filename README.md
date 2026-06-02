# TiO₂ Dielectric Metalens Unit Cell Optimization

This project contains a simulation of a dielectric metasurface unit cell that works at visible light wavelength (λ = 532 nm). It is done using Ansys Lumerical FDTD.

---

## Design Specifications

The structure is a Titanium Dioxide (TiO₂) nanopillar placed on a glass substrate. It works like a small waveguide that controls the phase of light by changing the pillar radius.

| Parameter | Value | Reason |
| --- | --- | --- |
| **Wavelength (λ)** | 532 nm | Green laser light |
| **Lattice Period (P)** | 350 nm | Smaller than wavelength to avoid unwanted diffraction |
| **Pillar Height (H)** | 600 nm | Needed to get full phase shift (0 to 2π) |
| **Pillar Radius (R)** | 50 nm to 150 nm | Changed during simulation |
| **Substrate Index (n)** | 1.46 | Glass |
| **Pillar Index (n)** | 2.45 | High index material |

---

## Simulation Setup

The simulation is done using a Lumerical script (`.lsf`).

- **Boundary conditions:** Periodic in X and Y, PML in Z
- **Source:** Plane wave coming from the substrate
- **Monitors:** One monitor above the pillar to measure transmission and phase

---

## Key Results

### 1. Phase and Transmission

- **Good range (50 nm – 116.7 nm):**  
  Phase changes smoothly from 0° to 360°. Transmission stays high (>90%). This is the working region.

- **At 100 nm radius:**  
  Transmission drops very low (3.4%). Reflection becomes very high. This is a resonance effect, so it is not usable.

- **Large radius (>133 nm):**  
  Pillars are too close. The structure stops acting like separate waveguides, so performance drops.

---

### 2. Data Table

| Radius (nm) | Transmission | Reflection | Phase (deg) | Note |
| --- | --- | --- | --- | --- |
| 50.0  | 0.987 | 0.012 | 0°    | Good start |
| 75.0  | 0.974 | 0.026 | 122°  | Good |
| 100.0 | 0.034 | 0.935 | 217°  | Bad (resonance) |
| 116.7 | 0.962 | 0.037 | 359°  | Best case |
| 150.0 | 0.129 | 0.870 | 471°  | Too dense |

---

## How to Run

1. Clone this repo
2. Open Ansys Lumerical FDTD
3. Run `metalens_simu_expanded.lsf`
4. The script will:
   - Build the structure
   - Run the sweep
   - Save results to a file
   - Show plots
