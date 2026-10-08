# Interfaces, Heterostructures, and Space Charge

> **Module:** Materials · **Prerequisites:** [Bulk Structures](../01-foundations/06-bulk-crystal-structures.md), [Surfaces](01-surfaces-and-slabs.md)  
> **Related:** [Diffusion and Ionic Transport](../03-transport/01-diffusion-and-msd.md)

## Learning goals

Understand coherent and incoherent interfaces, lattice mismatch, strain, interface formation energy, interfacial defects, electrostatic potential gradients, and how interfaces modify ion transport.

![Bulk surface interface comparison](../assets/figures/bulk-surface-interface.svg)

*Figure 1. A surface separates a material from its environment; an interface joins two distinct regions or phases.*

## 1. What is an interface?

An **interface** is the boundary between two materials, phases, grains, or structurally different regions. Examples include grain boundaries, crystalline–amorphous contacts, solid-electrolyte/electrode boundaries, and heteroepitaxial layers.

An ideal bulk calculation lacks such a boundary, while a single-surface slab borders vacuum or an environment. Interface models require two neighboring regions with explicitly defined chemistry and geometry.

## 2. Lattice mismatch and coherent strain

For an illustrative one-dimensional lattice matching problem, define a mismatch against substrate spacing $a_s$ as:

```math
f=\frac{a_f-a_s}{a_s}.
```

This is only one convention; the sign and reference must be stated. Real commensurate interface construction requires searching in-plane supercell matrices and considering possible rotations, misfit dislocations, and strain energy.

An artificially forced coherent match can change defect energies and ionic migration barriers.

## 3. Interface energy and adhesion

For a coherent model with suitable reference states, one possible interfacial formation-energy expression is:

```math
\gamma_{\mathrm{int}}=\frac{E_{\mathrm{cell}}-\sum_i N_i\mu_i}{n_{\mathrm{int}}A}.
```

The reference chemical potentials, strained bulk references, stoichiometry, and number $n_{\mathrm{int}}$ of equivalent interfaces must be defined explicitly. If interfaces are inequivalent, the total excess energy cannot generally be assigned to either interface without additional calculations.

**Work of adhesion** and **interface formation energy** are related but different quantities; do not interchange them.

## 4. Electrostatic potential and space-charge layers

Charged defects and redistribution of mobile ions can create an electrostatic potential gradient near an interface. In a continuum picture:

```math
\nabla\cdot[\varepsilon(\mathbf r)\nabla\phi(\mathbf r)]=-\rho(\mathbf r).
```

The potential $\phi$ and charge density $\rho$ must be consistent with electrostatic boundary conditions and the chosen dielectric description.

![Schematic potential near an interface](../assets/figures/interface-band-bending.svg)

*Figure 2. A qualitative interfacial potential profile. Actual sign, width, and shape are material- and defect-dependent.*

Potential variations can alter ion concentrations and migration barriers. A space-charge layer is not guaranteed: its existence and magnitude depend on chemistry, defect equilibria, dielectric response, and temperature.

## 5. Interface-specific transport mechanisms

Several distinct effects can coexist:

| Mechanism | Potential consequence |
| --- | --- |
| Local strain | Modifies bond lengths and migration barriers |
| Defect segregation | Changes the population of mobile carriers and traps |
| Chemical intermixing | Creates different local coordination environments |
| Space charge | Redistributes mobile ion concentrations |
| Structural disorder | Produces a distribution of local pathways |
| Poor contact / voids | Adds an extrinsic resistance that atomistic ideal interfaces may miss |

A low NEB barrier at one interface site is insufficient to demonstrate an overall high interfacial conductivity. Long-range connected pathways, carrier concentrations, and transport across—not just along—the boundary matter.

## 6. Practical model-building workflow

1. Identify the two phases, orientations, and stable terminations.
2. Search possible supercell matches and quantify imposed strain.
3. Construct several plausible registries and interface chemistries.
4. Relax with transparent constraints and convergence settings.
5. Assess interfacial energies, local coordination, defects, and electrostatic potential.
6. Sample interface-parallel and interface-normal transport separately.
7. Validate representative NEB pathways, but integrate their kinetics with populations and connectivity.

## 7. Relevance to solid-state ion conductors

For glass–crystal or electrolyte–electrode contacts, distinguish intrinsic interfacial ionic mobility from the experimentally measured interface resistance. Grain boundary chemistry, contact quality, and reaction layers may dominate measured impedance even if atomistic local hopping barriers are small.

## Review questions

1. How do interfaces differ from surfaces and grain boundaries?
2. Why can coherent matching change a migration barrier?
3. What additional information is required to calculate interface formation energy?
4. How might space charge change conductivity without changing the microscopic hop mechanism?
5. Why do ideal atomistic interfaces not capture contact resistance automatically?

**Next:** [Diffusion and Ionic Transport](../03-transport/01-diffusion-and-msd.md).
