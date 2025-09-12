---
layout: project
type: project
image: 
title: "EFMO Validation"
date: 2025
published: true
labels:
  - Python
  - Bash/Unix
  - HPC
summary: "My Spring 2025 Research Project"
---
# Validation of the Effective Fragment Molecular Orbital Method for Modeling Protein–Ligand Systems

## Overview

This project evaluated the **Effective Fragment Molecular Orbital (EFMO) method** as a tool for modeling protein–ligand interactions. EFMO combines the Fragment Molecular Orbital (FMO) method, which divides large systems into smaller fragments, and the Effective Fragment Potential (EFP) method, which applies force fields derived from second-order perturbation theory. The goal was to test whether EFMO could deliver accurate results while reducing the high computational cost of full quantum mechanical (QM) calculations.  

---

## Methods

The project focused on building and testing automated workflows for EFMO calculations:

- **Workflow Automation:** Python and Bash scripting were used to set up and run EFP and EFMO simulations in a reproducible way.  
- **Basis Set Selection:** EFP calculations on small organic molecules were carried out first to identify efficient basis sets before applying EFMO to larger biomolecular systems.  
- **Computational Resources:** All simulations were performed on the University of Hawaii’s **KOA supercomputer**, which allowed testing across a range of system sizes.  
- **Validation:** EFMO results were compared against established protein–ligand interaction datasets, measuring accuracy, runtime, and computational performance.  

---

## Outcomes

- Built an end-to-end automated workflow for EFMO calculations.  
- Used EFP benchmarks to guide the selection of efficient and accurate basis sets.  
- Tested EFMO on larger biomolecular systems with consistent and reliable results.  
- Demonstrated that EFMO can balance **accuracy** and **computational efficiency** for modeling protein–ligand interactions.  

---

## Final Presentation

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSWgB0ElFgOUUcbeYuiM21PYGhS4Fpohv26HNiEeKzDBfOYNhMa_dZyqt8jGuLdbH620pZwHA2rEGq3/pubembed?start=false&loop=false&delayms=15000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>