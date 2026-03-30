<div align="center">
  <h1>⚛️ Micro-Reactor Core Neutronic Design & Simulation</h1>
  <h3>Computational analysis of a Heat Pipe-cooled Micro-Reactor using MCNP5</h3>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Code-MCNP5-000000?style=for-the-badge&logo=linux&logoColor=white" />
  <img src="https://img.shields.io/badge/Focus-Neutronics_%26_Criticality-3776AB?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Domain-Nuclear_Engineering-0076A8?style=for-the-badge" />
</p>

---

## 📝 Project Overview

This repository contains the full MCNP5 (Monte Carlo N-Particle) input deck and simulation parameters for a **Heat Pipe-cooled Micro-Reactor Core**. The project demonstrates the modeling of complex lattice geometries, advanced nuclear material assignments, and neutronic criticality optimization.

This type of reactor design is highly relevant for remote terrestrial power applications and space exploration, prioritizing passive safety, compact geometry, and high-temperature operation.

## 🏗️ Core Architecture & Geometry

The reactor core is modeled using a complex 15x15 lattice structure (`lat=2`) mapping the fuel pins, heat pipes, and matrix structure. 

* **Core Dimensions:** Height ~ 34 cm | Radius ~ 31 cm.
* **Lattice Configuration:** Defined using detailed universe structures (`u=1`, `u=2`) integrated into a full hex/square boundary lattice array.
* **Surfaces Used:** Right Circular Cylinders (`rcc`) and Right Hexagonal Prisms (`rhp`) were heavily utilized to define the exact boundaries of the core layers, cladding, and reflector.

## 🧪 Material Specifications

The model accurately simulates high-performance advanced materials suited for micro-reactors:

| Component | Material Composition | MCNP Card | Description |
| :--- | :--- | :--- | :--- |
| **Nuclear Fuel** | **UN** (Uranium Nitride) | `m1` | Highly Enriched Uranium (70% U-235, 30% U-238) paired with Nitrogen-14 for high-density power output. |
| **Solid Matrix** | **Nb-Zr Alloy** | `m2` | Niobium (99%) and Zirconium (1%) alloy providing structural integrity at extreme temperatures. |
| **Coolant (Heat Pipe)** | **Liquid Lithium** | `m3` | Lithium-7 (`3007`) used as the primary phase-change working fluid for passive heat removal. |
| **Cladding / Pipe** | **Mo-Re Alloy** | `m4` | Molybdenum (86%) and Rhenium (14%) alloy for extreme corrosion resistance against liquid lithium. |
| **Reflector** | **BeO** (Beryllium Oxide) | `m5` | Excellent neutron reflector (`4009`, `8016`) to maintain core criticality in a compact volume. |

## 📊 Analytics & Tallies

The simulation is configured to perform deep neutronic evaluations using 100,000 particles per cycle:
* **Criticality Evaluation (`kcode`):** Evaluates the effective neutron multiplication factor ($k_{eff}$) to ensure stable operational criticality.
* **Energy Deposition (`F6` & `F7` Tallies):** Maps the energy deposition (MeV/g) across the core cells to analyze heat generation distribution, crucial for the thermal-hydraulic validation of the heat pipes.
* **Source Definition (`sdef`):** Volume-distributed spatial neutron source generation.

---

> **Note:** The raw MCNP input deck is provided in this repository. To visualize the geometry, run the deck through the MCNP Visual Editor (VISED) or process the output tallies utilizing Python/MATLAB scripts.
