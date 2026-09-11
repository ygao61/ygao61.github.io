---
layout: about
title: about
permalink: /
subtitle: Ph.D. Candidate in Computational Biology, <a href="https://www.cs.umd.edu/">University of Maryland</a>. Advised by <a href="https://www.cs.umd.edu/people/rob">Rob Patro</a> in the <a href="https://combine-lab.github.io/">COMBINE Lab</a>.

profile:
  align: right
  image: prof_pic.svg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>COMBINE Lab, Department of Computer Science</p>
    <p>University of Maryland</p>
    <p>College Park, MD 20742</p>
    <p><a href="mailto:ygao61@umd.edu">ygao61@umd.edu</a></p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I build methods that make single-cell and spatial measurements **trustworthy enough to draw conclusions from** — and ship them as tools other people actually run.

Most of my work sits at one specific failure point: the step between raw sequencing reads and the count matrix everyone downstream treats as ground truth. That step quietly discards a lot. Reads that map to several genes get thrown away, spliced and unspliced origins get conflated, and whole gene families — the overlapping *MS4A* locus, antioxidant regulators like *GPX1* — disappear into "unresolvable noise." My thesis work replaces those heuristics with a mechanistic probabilistic model: [Forseti](/publications/) predicts the splicing status of a read from first principles, and `alevin-fry-forseti` folds that model directly into graph-based UMI deduplication — 2.5× more long-read-confirmed multi-mapping assignments than a parsimony-EM baseline, and 75× faster after a rewrite in Rust.

The same instinct carries into imaging. At **Genentech gRED** I designed [BarCall](/publications/), a deep-learning base caller for optical pooled screens that performs spot detection and base calling jointly instead of as a decoupled multi-stage pipeline. Being end-to-end is what makes self-supervision possible — and it recovered ~18.5% more usable cells, with the improvement holding across plates.

I care about the unglamorous half of methods work: [QCatch](/publications/) exists because a quantification tool is only useful if you can tell when it went wrong, and a Django/D3.js [visualization platform](/projects/) exists because a cell-lineage hierarchy is much easier to reason about when you can actually zoom through it.

**I am finishing my Ph.D. in December 2026 and looking for industry roles** in computational biology, ML for genomics, or scientific tooling. If that sounds like a fit, [get in touch](mailto:ygao61@umd.edu) — or start with my [CV](/cv/) and [projects](/projects/).
