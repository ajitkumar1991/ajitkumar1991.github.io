# Changelog

All notable changes to the website are documented here.

---

## [2026-03-23] — Worm Algorithm Section Rewrite

### Rewritten (research.qmd)
- **"Superfluidity in the 3D Lattice Bose Gas"**: Added full Hamiltonian, precise model description with limiting cases, observable definitions
- **"Monte Carlo Worm Algorithm for Long-Range Interactions"** → renamed **"Worm and Cluster Algorithms for Long-Range Interactions"**: Complete rewrite based on paper draft. Now includes:
  - The high-temperature expansion and Q(k) factorization for the standard worm algorithm
  - Why Q(k) breaks down for long-range interactions (N-dimensional integral, no factorization)
  - The mixed representation solution: amplitudes as explicit MC variables
  - Separation of fast (phase/bond) and slow (amplitude/density) degrees of freedom
  - Cluster algorithm with density-invariance under Wolff reflections
  - Benchmark results table (autocorrelation times, z ≲ 0.2)
  - ASCII schematic comparing standard vs. mixed-representation approaches
  - Computational cost analysis (O(1) worm moves, O(N) modulus updates)

### Rewritten (notes/monte-carlo.qmd)
- Replaced generic "Long-Range Interactions" section with detailed exposition of:
  - Why the standard approach fails (Q-function breakdown)
  - The mixed representation and stochastic amplitude sampling
  - Cluster algorithm and density invariance
  - Computational considerations and Ewald summation

### Updated (index.qmd)
- Homepage card renamed and rewritten to highlight algorithmic contributions

---

## [2026-03-23] — Project Name Corrections and Restructuring

### Renamed Projects (research.qmd and index.qmd)
- "Lagrangian Descriptions of Non-Lagrangian N=2 SCFTs" → **"The Art of Brane Bending: Lagrangians for Non-Lagrangian SCFTs"**
- "N=1 Flavor Orientifolds: Discrete Data and S-Duality" → **"Flavor Orientifolds and S-Duality"**
- "Quad-CFTs and Infrared Phases of Tensor Matter Theories" → **"The IR Dynamics of N=1 Gauge Theories Using Quad-CFTs"**
- "Mirror Geometry and Moduli-Space Structure" → **"Mirror Symmetry in Quad-CFTs"**
- "Symmetry-Enriched Criticality in Interacting Majorana Chains" → **"Topological Symmetry and Boundary RG Flow in Ising Criticality"**
- "Monte Carlo for Superfluidity with Long-Range Interactions" → Split into **"Superfluidity in the 3D Lattice Bose Gas"** and **"Monte Carlo Worm Algorithm for Long-Range Interactions"**

### Added Projects
- **"DMRG Using Tensor Networks"** — Elevated from implicit method to explicit project entry
- **"Mirror Symmetry in Quad-CFTs"** — Added as homepage card (was only on research page)

### Expanded Descriptions
- Added brane bending schematic diagram to the Lagrangian SCFTs section
- Added naive-vs-correct deconfinement schematic to the quad-CFT section
- Added phase diagram with boundary conditions to the Majorana chain section
- Added |ψ|⁴ lattice action to the superfluidity section
- All high-energy projects now include physical framework, significance, and future directions

---

## [2026-03-23] — Research Description Corrections

### Fixed (from research statement audit)
- `website/research.qmd` — **Major rewrite.** Corrected the framing of all high-energy projects:
  - Fixed the Lagrangian construction description (was backwards: described "deconfining N=2 to produce N=1" when the actual work flows from N=1 quivers to N=2 fixed points)
  - Added five missing projects: flavor orientifolds, quad-CFTs, mirror geometry, 2D CFT/WGC, future directions on generalized symmetries
  - Removed Machine Learning and Tensor Networks as standalone research sections (these are computational methods, not primary research directions)
  - Each project now has: problem statement, methods, results, significance, future directions
- `website/index.qmd` — Rewrote bio and research highlights to match actual projects. Six project cards replace four generic topic cards. Removed "machine learning" as a research pillar.
- `website/publications.qmd` — Fixed authors (added Heidenreich to paper 1), fixed titles, corrected collaborators on all papers, added five missing papers/preprints
- `website/about.qmd` — Updated research interests to list actual projects

### Removed
- `website/topics/` directory — Orphaned pages causing build errors, superseded by notes section

### Changed (organization)
- Homepage redesigned: profile photo as small sidebar, research projects dominate the page
- Blog sidebar improved with "Browse by Topic" links
- Fixed blog listing on homepage

---

## [2026-03-23] — Content Expansion

### Expanded Notes Pages
- All 8 notes pages expanded with additional mathematical detail, ASCII diagrams, code examples, and worked examples
- `tensor-networks.qmd`: ASCII diagrams for MPS, DMRG, MERA; expanded TCI with full algorithm and Julia code
- `monte-carlo.qmd`: Swendsen-Wang implementation, worldline and worm diagrams
- `brane-tilings.qmd`: Conifold tiling diagram, quiver diagram, urban renewal diagram
- `2d-cft-swampland.qmd`: Free boson partition function, Narain lattice, minimal models table
- `quantum-information.qmd`: QEC section, teleportation, no-deleting theorem, worked Helstrom example
- `group-theory-qm.qmd`: Wigner-Eckart theorem, S3 character table, selection rules, expanded crystal field
- `mirror-symmetry.qmd`: CY primer, expanded quintic, enumerative geometry, SYZ singular fibers, mirror curves

---

## [2026-03-23] — Site Architecture Overhaul

### Added
- `PLAN.md` — Website architecture and editorial strategy document
- `CHANGES.md` — This changelog
- `CONTENT_ROADMAP.md` — Topic pages, subtopics, and dependencies
- `TODO.md` — Prioritized implementation list
- `website/notes/` directory — Substantive technical expositions
- `website/tools/` directory — Computational methods and workflows
- `website/publications.qmd` — Dedicated publications page
- `website/contact.qmd` — Contact and CV page

### Changed
- `website/_quarto.yml` — New navbar with dropdowns, multiple named sidebars
- `website/about.qmd` — Placeholder cleanup, content extracted to publications/contact pages
- `website/research.qmd` — Streamlined to link to Notes pages

### Content Added
- `notes/tensor-networks.qmd` — Expanded from blog post: MPS, DMRG, TCI, quantics, entanglement
- `notes/monte-carlo.qmd` — Expanded from blog post: Metropolis, cluster, worm, error analysis
- `notes/brane-tilings.qmd` — Expanded from blog post: SCFTs, brane bending, S-duality
- `notes/machine-learning.qmd` — Expanded from blog post: neural nets, transformers, grokking
- `notes/quantum-information.qmd` — New: no-cloning, state discrimination, entanglement
- `notes/mirror-symmetry.qmd` — New: mirror symmetry, T-duality, SYZ
- `notes/2d-cft-swampland.qmd` — New: Virasoro, orbifolding, swampland conjectures
- `notes/group-theory-qm.qmd` — New: representations, symmetry, degeneracy
- `tools/julia-tensor-networks.qmd` — ITensor.jl practical guide
- `tools/monte-carlo-errors.qmd` — Bootstrap, jackknife, blocking
- `tools/data-analysis.qmd` — Autocorrelation, binning, workflows
