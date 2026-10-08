# Forces, Energy Gradients, and Curvature

> **Prerequisite:** [Potential Energy Surfaces](01-potential-energy-surface.md)  
> **Next:** [Geometry Optimization](../02-methods/01-geometry-optimization.md)

## Learning objectives

Understand why forces point downhill on a PES, how gradients and Hessians differ, and why zero force is not sufficient to identify a stable structure.

## 1. From energy to forces

![Energy gradient and downhill force](../assets/figures/force-gradient.svg)

*Figure. Forces point opposite to the energy gradient in a one-dimensional potential well.*



For a configuration with atomic positions $\mathbf R$, the potential energy is $E(\mathbf R)$. The force on atom $i$ is the **negative gradient** with respect to its Cartesian position:

```math
\mathbf F_i=-\nabla_{\mathbf r_i}E(\mathbf R).
```

A gradient points toward the steepest local increase of energy. The force points in the opposite direction.

In one dimension:

```math
F_x=-\frac{dE}{dx}.
```

At the bottom of a smooth potential well, the slope is zero; on either side, the force tends to push the particle back toward the minimum.

## 2. Force and curvature are different

A force measures a **first derivative**. Curvature measures a **second derivative**:

```math
H_{ij}=\frac{\partial^2 E}{\partial R_i\,\partial R_j}.
```

The matrix $H$ is the Hessian. At a stationary structure, its eigenvalues reveal local stability (after accounting for constrained and trivial zero modes).

| Stationary configuration | Gradient | Curvature |
| --- | --- | --- |
| Local minimum | Zero | Positive in nontrivial directions |
| First-order saddle | Zero | One unstable direction |
| Local maximum | Zero | Negative in the considered directions |

**A vanishing force does not prove that the structure is a minimum.** This is important when assessing a transition state.

## 3. Harmonic approximation

Near a relaxed minimum $\mathbf R_0$, a Taylor expansion gives:

```math
E(\mathbf R_0+\Delta\mathbf R)\approx E(\mathbf R_0)+\frac12\Delta\mathbf R^{\mathrm T}H\Delta\mathbf R.
```

The linear term disappears at a stationary point. This approximation connects curvature to local vibrational motion, but strongly activated jumps usually travel beyond the harmonic region.

## 4. Why NEB uses projected forces

An NEB image experiences a force that can be decomposed relative to the tangent $\hat{\boldsymbol\tau}$:

```math
\mathbf F_{\parallel}=(\mathbf F\cdot\hat{\boldsymbol\tau})\hat{\boldsymbol\tau},\qquad \mathbf F_{\perp}=\mathbf F-\mathbf F_{\parallel}.
```

In regular NEB, the physical force **perpendicular** to the band relaxes the pathway, while spring forces **parallel** to it help distribute images. This separation prevents the artificial springs from distorting the physical route.

## 5. Numerical issues

Small force magnitudes can be misleading if energies and forces are noisy, the electronic structure has not converged, or constraints hide unstable directions. When comparing methods, check that forces are evaluated consistently.

## Check your understanding

1. What sign relates force and energy gradient?
2. Why can both a local minimum and a saddle point have zero net force?
3. What does the Hessian tell us that the gradient does not?
4. Why does NEB project forces parallel and perpendicular to its path?

**Next:** [Geometry Optimization and Convergence](../02-methods/01-geometry-optimization.md).
