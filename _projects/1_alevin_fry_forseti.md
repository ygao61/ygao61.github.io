---
layout: page
permalink: /projects/alevin-fry-forseti/
title: alevin-fry-forseti
description: Mechanism-aware single-cell quantification — 2.5× more long-read-confirmed multimapping assignments, and 75× faster after a rewrite in Rust.
img: assets/img/proj/forseti.svg
importance: 1
category: methods
github: https://github.com/COMBINE-lab/alevin-fry
related_publications: true
---

### The problem

Every single-cell analysis starts from a count matrix that is treated as ground truth. Getting there requires answering two questions for each read — *which gene did this come from?* and *was the molecule spliced?* — and conventional pipelines answer both with heuristics. Reads that map to more than one gene are discarded or split by parsimony; splicing status is inferred from where the read lands rather than from how the library was built.

That discards signal exactly where genes overlap. Members of the *MS4A* family sit on top of one another. So do many functional markers. They do not vanish because the biology is absent; they vanish because the pipeline has no principled way to decide.

### The approach

`alevin-fry-forseti` integrates a mechanistic probabilistic model of splicing status directly into graph-based UMI deduplication, rather than applying it as a post-hoc tie-break. The model — {% cite he2024forseti %} — couples a predictive model of the fragment-length distribution with a learned model of priming-site affinity, so each read carries a calibrated probability instead of a hard label, and that probability participates in deduplication itself.

### What it bought

- **2.5×** higher long-read confirmation of multimapping reassignments than a parsimony-EM baseline, validated against matched long-read data from the same samples.
- **2.7×** more recovered calls than Cell Ranger — 288K vs. 106K.
- Rescued biomarkers that mechanism-unaware heuristics routinely drop as noise, including the antioxidant regulator *GPX1* in dendritic cells.
- Highest clustering agreement (NMI/ARI) with expert-curated cell types on a human MTG snRNA-seq atlas (9,103 cells, 19 subclasses) — significantly better than Cell Ranger (p = 0.006), and matching the reference ceiling.
- **75×** end-to-end speedup from systematic performance work in Rust.

### My role

Architected the tool end to end: probabilistic model integration, the deduplication algorithm, the Rust implementation and its optimization, and the orthogonal long-read validation. Manuscript under review.

**Stack:** Rust, Python, Nextflow
