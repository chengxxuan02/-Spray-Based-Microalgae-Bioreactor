# Microalgae-Bioreactor

A computational model of a multi-stage microalgae photobioreactor coupling droplet hydrodynamics, light transport, photosynthetic dynamics and biomass growth.

The model investigates how hydrodynamic and optical conditions influence light availability and microalgae growth throughout a five-stage reactor system. It combines a mechanistic description of droplet behaviour with Mie scattering, a two-flux radiative transfer model and nonlinear ordinary differential equations describing photosystem and biomass dynamics.

# Model Architecture

flowchart TD A[Model Inputs<br/>Reactor geometry<br/>Flow rates<br/>Light intensity<br/>Biomass properties] A --> B[Droplet Hydrodynamics] B --> B1[Droplet velocity] B --> B2[Residence time] B --> B3[Droplet concentration] B --> C[Optical Model] C --> C1[Mie Scattering] C1 --> C2[Extinction Coefficient] C1 --> C3[Scattering Coefficient] C2 --> D[Two-Flux Radiative Transfer] C3 --> D D --> E[Local Light Intensity] E --> F[Photosynthetic Model] F --> F1[PSII States<br/>A, B, C] F --> F2[NPQ<br/>alpha] F --> F3[Photoacclimation<br/>Ig] F --> G[Local Biomass Growth Rate] G --> H[Radial Integration] H --> I[Average Stage Growth Rate] I --> J[Five-Stage Reactor Model] J --> J1[Stage 1] J1 --> J2[Stage 2] J2 --> J3[Stage 3] J3 --> J4[Stage 4] J4 --> J5[Stage 5] J5 --> K[Dark Storage Tank] K --> L{Recycle} L -->|80% recycle| J1 L -->|Product / outlet| M[Reactor Output] J --> N[ODE Solver] N --> O[Simulation Results<br/>Biomass<br/>PSII states<br/>Light profiles]
