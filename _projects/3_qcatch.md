---
layout: page
title: QCatch
description: Automated cell calling and interactive HTML quality-control reports for the alevin-fry ecosystem, standardized to H5AD.
img: assets/img/proj/qcatch.svg
importance: 1
category: tools
github: https://github.com/COMBINE-lab/QCatch
related_publications: true
---

### Why it exists

A quantification tool is only useful if you can tell when it has gone wrong. `alevin-fry` is fast and accurate, but reading its output meant assembling your own diagnostics — which in practice meant most users did not, and silently accepted whatever came out.

### What it does

{% cite gao2026qcatch %} is a Python diagnostic framework that sits on top of the alevin-fry ecosystem and:

- performs **automated cell calling**, so the empty-droplet cutoff is a decision the tool defends rather than one the user guesses;
- generates a **self-contained interactive HTML report** — knee plots, mitochondrial fraction, complexity, per-sample summaries — that can be handed to a collaborator without a Python environment;
- standardizes outputs into the widely adopted **H5AD** format, so QC results drop directly into Scanpy-based workflows instead of requiring a conversion detour.

The design goal was accessibility: the shortest path between "I ran the pipeline" and "I can see whether to trust it."

### My role

Co-first author. Designed and implemented the framework, the cell-calling logic, and the report generator. Published in *Bioinformatics* 42(5), 2026.

**Stack:** Python, AnnData/H5AD, interactive HTML reporting
