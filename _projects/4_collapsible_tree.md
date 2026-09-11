---
layout: page
permalink: /projects/collapsible-tree/
title: Collapsible tree
description: A Django/D3.js platform for zooming through cell-lineage hierarchies at any resolution.
img: assets/img/proj/collapsible-tree.svg
importance: 2
category: tools
related_publications: true
---

### Why it exists

Cell-type annotations are hierarchical — broad lineages branching into progressively finer subtypes — but expression is usually inspected at one flat resolution. You either look at "T cells" or at nineteen subclasses, and switching between them means regenerating the analysis.

### What it does

{% cite gao2024collapsibletree %} is a full-stack visualization platform that turns high-dimensional scRNA-seq count matrices into **interactive, collapsible cell-lineage trees** built on hierarchical ontologies. Branches expand and collapse in place, and expression is recomputed at whatever resolution you are currently looking at — so moving from a broad lineage to a specific subtype is a click, not a new analysis.

The interaction is the point: a hierarchy you can move through is a hierarchy you can actually reason about.

### My role

First author. Architected the platform end to end — data model, backend, and the D3 visualization. Built at the **National Cancer Institute, NIH**, advised by Dr. Peng Jiang. Published in *Bioinformatics* 40(11), 2024.

**Stack:** Django, D3.js, Node.js, Python
