# Content Roadmap

## Notes & Expositions

### String Theory & Geometry

#### 1. Brane Tilings and 4D Supersymmetric Field Theory
**Level:** Advanced / Research-level
**Status:** Absorbs `blog/2025-01-15-brane-tilings.qmd`
**Subtopics:**
- Brane tilings as bipartite graphs on T^2
- Quiver gauge theories from dimer models
- Perfect matchings and moduli spaces
- Orientifold projections (fixed-point and fixed-line)
- 4D N=1 SCFTs from geometric engineering
- Deconfining N=2 theories via brane bending
- S-duality and Seiberg duality
- Connections to Heidenreich's work
**Dependencies:** Benefits from mirror-symmetry.qmd and 2d-cft-swampland.qmd for cross-references

#### 2. Mirror Symmetry and T-Duality
**Level:** Advanced
**Status:** New
**Subtopics:**
- Calabi-Yau mirror pairs and Hodge diamond exchange
- T-duality: R -> 1/R
- SYZ conjecture (T-duality fibration)
- Type IIA vs IIB, D-branes wrapping cycles
- Enumerative geometry applications
- Connections to brane tilings
**Dependencies:** None (self-contained, but cross-links to brane-tilings.qmd)

#### 3. 2D CFT, Orbifolding, and the Swampland
**Level:** Advanced / Research-level
**Status:** New (absorbs zeta regularization content from `blog/2025-11-15-zeta-regularization.qmd`)
**Subtopics:**
- Virasoro algebra and representation theory
- Primary operators, OPE, conformal blocks
- Modular invariance of the partition function
- Orbifolding: gauging discrete symmetries
- Twisted sectors and modular orbits
- Zeta regularization and vacuum energy (from existing blog post)
- Swampland program: key conjectures
- Connections between modular invariance and swampland constraints
**Dependencies:** group-theory-qm.qmd provides background on representations

### Many-Body & Computation

#### 4. Tensor Networks
**Level:** Advanced
**Status:** Absorbs `blog/2025-01-01-tensor-networks.qmd`
**Subtopics:**
- Tensor diagrams and contractions
- Matrix Product States (MPS)
- Area law and entanglement structure
- DMRG algorithm
- Entanglement entropy (von Neumann, Renyi)
- Correlation functions from MPS
- Extracting CFT data
- Boundary CFT and boundary entropy
- TCI (tensor cross interpolation)
- Quantics tensor methods
- Connections to holography
- Limitations and where methods break down
**Dependencies:** Cross-links to tools/julia-tensor-networks.qmd, quantum-information.qmd

#### 5. Monte Carlo and Computational Statistical Physics
**Level:** Advanced
**Status:** Absorbs `blog/2025-01-08-worm-algorithm.qmd`
**Subtopics:**
- What Monte Carlo is: sampling and integration
- Metropolis algorithm
- Cluster algorithms (Swendsen-Wang, Wolff)
- Worm algorithm
- Ising model as running example
- Error analysis: bootstrap, jackknife, blocking
- Autocorrelation and integrated autocorrelation time
- Time-series analysis of MC data
- Applications to classical statistical models
**Dependencies:** Cross-links to tools/monte-carlo-errors.qmd, tools/data-analysis.qmd

#### 6. Quantum Information and Computation
**Level:** Advanced
**Status:** New
**Subtopics:**
- No-cloning theorem (proof and implications)
- Quantum state discrimination and Helstrom bound
- Entanglement: Bell states, entropy, monogamy
- Quantum channels and completely positive maps
- Connections to tensor networks
- MPS as quantum error-correcting codes
**Dependencies:** tensor-networks.qmd for cross-references

### Methods & Foundations

#### 7. Machine Learning and Neural Networks
**Level:** Advanced
**Status:** Absorbs `blog/2024-12-20-diffusion-models.qmd`
**Subtopics:**
- Neural network fundamentals
- Universal approximation and loss landscapes
- Diffusion models and score-based generative models
- Normalizing flows
- Transformers and attention mechanisms
- Grokking and mechanistic interpretability
- Manifold learning
- Physics-ML connections
**Dependencies:** None

#### 8. Group Theory in Quantum Mechanics
**Level:** Introductory / Advanced
**Status:** New
**Subtopics:**
- Groups, representations, irreducibility
- Schur's lemma and character theory
- Symmetry and degeneracy in quantum mechanics
- SU(2): angular momentum and spin
- Tensor products and Clebsch-Gordan coefficients
- Point groups (brief)
- Worked examples
**Dependencies:** None (foundational, supports other notes)

---

## Computational Tools

#### T1. Julia Tensor Network Workflows
**Status:** New
**Content:** ITensor.jl installation, site definitions, MPO construction, DMRG parameters, measuring observables
**Dependencies:** Extracted from tensor-networks.qmd code examples

#### T2. Monte Carlo Error Analysis
**Status:** New
**Content:** Bootstrap, jackknife, blocking methods with Python/Julia code
**Dependencies:** Companion to monte-carlo.qmd

#### T3. Data Analysis for Monte Carlo
**Status:** New
**Content:** Autocorrelation estimation, binning, practical workflow from raw data to error bars
**Dependencies:** Companion to monte-carlo.qmd

---

## Content Dependencies Graph

```
group-theory-qm ──────────────► 2d-cft-swampland
                                      │
quantum-information ◄──► tensor-networks ──► tools/julia-tensor-networks
                                      │
mirror-symmetry ◄──────► brane-tilings

monte-carlo ──────────► tools/monte-carlo-errors
         │              tools/data-analysis
         │
machine-learning (independent)
```
