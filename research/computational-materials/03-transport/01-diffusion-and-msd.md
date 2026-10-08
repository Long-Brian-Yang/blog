# Diffusion, Mean-Squared Displacement, and Ionic Transport

> **Prerequisite:** [Potential Energy Surfaces](../01-foundations/01-potential-energy-surface.md)  
> **Related:** [NEB](../02-methods/02-neb.md)

## 1. Diffusion describes statistical motion

A migration barrier characterizes a **specific microscopic pathway**. A diffusion coefficient measures how the spread of particle positions grows over time after suitable averaging.

For particle $i$, define its displacement over lag time $t$:

```math
\Delta\mathbf r_i(t;t_0)=\mathbf r_i(t_0+t)-\mathbf r_i(t_0).
```

For a set of equivalent mobile ions, the time-origin- and particle-averaged mean-squared displacement (MSD) is:

```math
\mathrm{MSD}(t)=\left\langle |\Delta\mathbf r_i(t;t_0)|^2\right\rangle_{i,t_0}.
```

The displacement must be computed using **unwrapped positions** across periodic boundaries.

## 2. Einstein relation

For normal, isotropic three-dimensional diffusion in the long-time diffusive regime:

```math
D=\lim_{t\to\infty}\frac{\mathrm{MSD}(t)}{6t}.
```

If MSD has a linear regime, its slope is $6D$. The factor changes with dimensionality: $2dD$ for isotropic diffusion in $d$ dimensions.

**Never fit the initial ballistic or vibrational region and call the result a diffusion coefficient.** Assess whether an actual linear diffusive regime has emerged.

## 3. Directional diffusion

At a surface or interface, in-plane and surface-normal transport may differ:

```math
D_{\parallel}=\lim_{t\to\infty}\frac{\langle\Delta x^2+\Delta y^2\rangle}{4t},\qquad D_{\perp}=\lim_{t\to\infty}\frac{\langle\Delta z^2\rangle}{2t}.
```

These expressions apply when the corresponding directions exhibit normal diffusion. A confined direction can show a plateau rather than long-time unbounded diffusion.

## 4. From self-diffusion to conductivity

The Nernst–Einstein (NE) estimate for identical mobile ions is:

```math
\sigma_{\mathrm{NE}}=\frac{nq^2 D_{\mathrm{self}}}{k_{\mathrm B}T},
```

where $n$ is the carrier number density and $q$ is the ionic charge. NE neglects distinct-ion displacement correlations.

Actual collective conductivity includes correlated motion; for a charge-neutral periodic system an Einstein–Helfand-type formulation is:

```math
\sigma=\lim_{t\to\infty}\frac{1}{6Vk_{\mathrm B}Tt}\left\langle\left|\sum_i q_i\Delta\mathbf r_i(t)\right|^2\right\rangle.
```

Care is required in defining transported charge and unwrapped trajectories for multi-species systems. For correlated transport, $\sigma/\sigma_{\mathrm{NE}}$ need not equal one.

## 5. Why NEB does not directly output $D$

In a simple uncorrelated hopping model with equivalent sites and hop length $\ell$:

```math
D\approx\frac{z\ell^2\nu}{6}\exp\left(-\frac{E_m}{k_{\mathrm B}T}\right).
```

Here $z$ is the number of equivalent destinations and $\nu$ an attempt frequency. This is an **illustrative kinetic approximation**, not a general conversion from NEB barrier to conductivity. Site occupancy, trapping, network connectivity, entropy, and correlations matter.

## 6. Practical validation

- Plot MSD against time and show the selected fitting interval.
- Compare slopes across independent trajectories or glass realizations.
- Use appropriate lag-time averaging and uncertainty estimates.
- Separate diffusion along inequivalent axes.
- Check whether mobile species other than the target ion contribute to charge transport.
- Do not confuse proton transfer event frequency with a macroscopic proton diffusivity.

## Review questions

1. What is the difference between a hop barrier and a diffusion coefficient?
2. Why is position unwrapping essential under periodic boundary conditions?
3. Why can $\sigma_{\mathrm{NE}}$ and the collective conductivity differ?
4. What happens to the surface-normal MSD if ions remain confined?

**Related:** [NEB and migration barriers](../02-methods/02-neb.md).
