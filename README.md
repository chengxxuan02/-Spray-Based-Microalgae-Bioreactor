# Microalgae-Bioreactor

A computational model of a multi-stage microalgae photobioreactor coupling droplet hydrodynamics, light transport, photosynthetic dynamics and biomass growth.

The model investigates how hydrodynamic and optical conditions influence light availability and microalgae growth throughout a five-stage reactor system. It combines a mechanistic description of droplet behaviour with Mie scattering, a two-flux radiative transfer model and nonlinear ordinary differential equations describing photosystem and biomass dynamics.

# Model Architecture

The current model contains five reactor stages followed by a storage/recycle tank.

 Fresh Feed
     │
     ▼
┌─────────┐
│ Stage 1 │◄──────────── Recycle
└────┬────┘                  │
     ▼                       │
┌─────────┐                  │
│ Stage 2 │                  │
└────┬────┘                  │
     ▼                       │
┌─────────┐                  │
│ Stage 3 │                  │
└────┬────┘                  │
     ▼                       │
┌─────────┐                  │
│ Stage 4 │                  │
└────┬────┘                  │
     ▼                       │
┌─────────┐                  │
│ Stage 5 │                  │
└────┬────┘                  │
     ▼                       │
┌──────────────┐             │
│ Storage Tank │─────────────┘
└──────────────┘

Each illuminated stage tracks seven state variables:

Variable	Description
X	Live biomass concentration
Xd	Non-active / dead biomass concentration
A	Active PSII fraction
B	Occupied PSII fraction
C	Damaged PSII fraction
alpha	NPQ / photoacclimation state
Ig	Acclimation irradiance
