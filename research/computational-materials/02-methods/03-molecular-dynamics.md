# Molecular Dynamics (MD) Fundamentals

> **Module:** Methods · **Prerequisites:** [PES](../01-foundations/01-potential-energy-surface.md), [Forces](../01-foundations/02-forces-and-gradients.md), [PBC](../01-foundations/04-periodic-boundary-conditions.md)  
> **Next:** [Statistical Ensembles](05-statistical-ensembles.md) · [Diffusion and MSD](../03-transport/01-diffusion-and-msd.md)

## Learning goals

Understand Newtonian trajectories, timesteps, Velocity Verlet, temperature, equilibration, and how to interpret simulated motion versus diffusion.

![Molecular dynamics particle trajectory](../assets/figures/md-integration.svg)

*Figure 1. Schematic time series of a particle coordinate. MD integrates equations of motion rather than optimizing a static pathway.*

## 1. Equations of motion

In classical MD, atoms evolve under forces derived from a potential energy function:

```math
m_i\frac{d^2\mathbf r_i}{dt^2}=\mathbf F_i=-\nabla_{\mathbf r_i}E(\mathbf R).
```

Positions $\mathbf r_i(t)$ and velocities $\mathbf v_i(t)$ are updated at discrete intervals $\Delta t$.

## 2. Velocity Verlet

A common integrator is:

```math
\mathbf r(t+\Delta t)=\mathbf r(t)+\mathbf v(t)\Delta t+\frac{\mathbf F(t)}{2m}\Delta t^2.
```

After recomputing force at the new position:

```math
\mathbf v(t+\Delta t)=\mathbf v(t)+\frac{\mathbf F(t)+\mathbf F(t+\Delta t)}{2m}\Delta t.
```

This is a reversible, symplectic-style integration scheme for ordinary conservative dynamics; thermostats and constraints can modify its behavior.

## 3. Choosing the timestep

The timestep should resolve the fastest relevant atomic motion. Hydrogen-containing systems often require shorter timesteps than heavy-atom systems. Too-large steps lead to integration error or instability; tiny steps increase cost without necessarily improving sampling efficiency.

Check total-energy drift in a representative NVE trajectory, in addition to physically sensible structural dynamics.

## 4. Temperature and kinetic energy

The instantaneous kinetic temperature is estimated from kinetic energy:

```math
T=\frac{2K}{f k_{\mathrm B}},\qquad K=\sum_i\frac12m_i|\mathbf v_i|^2.
```

Here $f$ is the number of active quadratic kinetic degrees of freedom, corrected for applicable constraints and removed motions. A finite system's instantaneous temperature fluctuates.

## 5. Equilibration versus production

**Equilibration** allows a system to approach an appropriate stationary distribution under selected conditions. **Production** collects trajectories used for analysis. Duration requirements depend on the property: stable temperature is not evidence that rare diffusion events have been sampled adequately.

## 6. MD outputs are observables only after analysis

| From trajectories | Analysis |
| --- | --- |
| Unwrapped positions | MSD and self-diffusion |
| Pair distances | RDF and coordination statistics |
| Velocities | Velocity autocorrelation |
| Atomic fluctuations | Vibrational and structural information |
| Charge-weighted displacements | Collective conductivity estimates |

## 7. AIMD versus MLIP-MD

AIMD usually obtains forces from electronic structure repeatedly, while MLIP-MD evaluates a trained force model. MLIPs allow longer trajectories but require validation for the relevant compositions, temperatures, and local environments.

## Pitfalls

- Calculating MSD from wrapped coordinates.
- Mistaking a short trajectory with no jumps for zero true diffusivity.
- Fitting MSD before reaching the diffusive regime.
- Ignoring thermostat effects and inadequate sampling.

## Review questions

1. What is the difference between a numerical timestep and an ion-hop waiting time?
2. Why should one test energy drift in NVE?
3. How can a trajectory have accurate forces but inadequate diffusion statistics?
4. Why can an MD simulation at high temperature fail to represent room-temperature transport?

**Next:** [Statistical Ensembles](05-statistical-ensembles.md).
