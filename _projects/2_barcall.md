---
layout: page
permalink: /projects/barcall/
title: BarCall
description: End-to-end deep learning for Optical Pooled Screens — spot detection and base calling in one model, recovering ~18.5% more usable cells.
img: assets/img/proj/barcall.svg
importance: 2
category: methods
related_publications: true
---

### The problem

In situ sequencing for Optical Pooled Screens (OPS) is conventionally decoupled: one stage finds spots in the image, a second stage reads out bases from the intensities at those spots. The split is convenient, but it caps accuracy — the base caller can only work with spots the detector already found, and detection errors are unrecoverable downstream. It also rules out self-supervision, because there is no single objective to train against.

### The approach

{% cite kontogiorgosheintz2026barcall %} performs spot detection and base calling **jointly**, in one end-to-end framework. Being end-to-end is not a stylistic preference here: it is the thing that makes self-supervised learning possible for OPS, where ground-truth labels are expensive and plate-specific.

### What it bought

- Recovered substantially more usable cells — **~18.5%** — for downstream analysis.
- Strong cross-plate generalizability, so the gain survives the plate-to-plate variation that usually forces retuning.
- Directly increases the effective yield of high-throughput OPS: more cells surviving to analysis, from the same experiment.

### My role

Research intern at **Genentech gRED** (June–October 2025), mentored by Dr. Monica Ge, Joshua Gould, and Dr. Bo Li in BRAID. I led pipeline design, training-data curation, model training, and evaluation. Accepted to ISMB 2026.

**Stack:** PyTorch, Python, model fine-tuning, pseudo-labeling
