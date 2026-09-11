---
layout: about
title: About
permalink: /

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>COMBINE Lab, Department of Computer Science</p>
    <p>University of Maryland</p>
    <p>College Park, MD 20742</p>
    <p>ygao61 [at] umd [dot] edu</p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I am a Ph.D. candidate in **Computational Biology** at the **University of Maryland**, advised by [Dr. Rob Patro](https://www.cs.umd.edu/people/nomad) in the [COMBINE Lab](https://combine-lab.github.io).

Previously, I obtained my M.S. in Bioinformatics from **The George Washington University**. From 2022 to 2024 I worked at the **National Cancer Institute, NIH** with [Dr. Peng Jiang](https://ccr.cancer.gov/staff-directory/peng-jiang), and before my Ph.D. I worked at **Children's National Hospital** with [Dr. Wei Li](https://weililab.org/).

I interned at **Genentech gRED** (w/ [Dr. Monica Ge](https://www.linkedin.com/in/xing-yue-monica-ge-592879a0/), [Joshua Gould](https://github.com/joshua-gould), and [Dr. Bo Li](https://www.gene.com/scientists/our-scientists/bo-li) in BRAID).

I develop **algorithms, statistical models, and machine learning methods for large-scale biological measurement** — the probabilistic model of how an assay generates its data, the algorithm that resolves what the model leaves ambiguous, and the deep networks that read the raw signal. My recent work explores:

- **Algorithm Development:** graph-based UMI deduplication and multi-mapping resolution for single-cell quantification — ambiguity resolved inside the algorithm rather than bolted on as a post-hoc tie-break.
- **Deep Learning for Biological Imaging:** end-to-end encoder–decoder architectures with a recurrent bottleneck for joint object detection and sequence decoding in in situ sequencing; self-supervised training and pseudo-labeling where ground-truth labels are scarce.
- **Statistical & Probabilistic Modeling:** mechanistic models of the data-generating process — fragment-length distributions, learned priming-site affinity — that replace hand-tuned heuristics with calibrated posteriors, validated against orthogonal long-read measurements.
- **ML for Drug Discovery:** tree-ensemble models over transcriptomic profiles spanning 578 cancer cell lines and 4,518 compounds, for drug-response prediction and mechanism-of-action biomarker discovery.
- **ML Systems & Tooling:** training-data curation, evaluation pipelines, and inference at scale — including a 75× speedup from systematic optimization in Rust, and open-source tooling used across the alevin-fry ecosystem.

<span style="color: var(--global-theme-color); font-weight: 600;">I'm graduating in December 2026 and currently on the industry job market — feel free to reach out at the address above.</span>
