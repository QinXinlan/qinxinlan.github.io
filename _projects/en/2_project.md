---
page_id: project_2
layout: page
title: Algorithms
description: An endless labyrinth of possibilities
img: assets/img/Brain_source_localization.jpg
importance: 2
category: work
#giscus_comments: true
related_publications: true
bibliography: other_papers.bib
---


## 🎓 What we know 🎓

### The best pipeline (so far)

So many algorithms, so little time. 

So far, the results I obtained rank in terms of accuracy for the following steps in the pipeline: 
- Blink correction:
1. ABCD (Adaptive Blink Correction and De-drifting) [{% cite guttmannflury2023thesis %}, {% cite guttmannflury2019abc %}, {% cite guttmannflury2019prabc %}  ]
2. ASR (Artifact Subspace Reconstruction)
3. ICA (Independent Component Analysis)

- Re-referencing:
1. Large Laplace
2. Small Laplace
3. CAR (Common Average Reference)

- Filtering (depending on the band):
1. Butterworth
2. Chebyshev
3. Elliptic

- Feature extraction:
1. SLST (Source Localized Spatio-Temporal) [{% cite guttmannflury2023thesis %}]
2. CSP (Common Spatial Pattern)
3. Civaruabce natrux

- Classification:
1. Dual classifier [{% cite guttmannflury2023thesis %}]
2. LDA (Linear Discriminant Analysis)
3. SVM (Support Vector Machine)
4. TS (Tangent Space)
5. MDRM (Minimum Distance to Riemannian Mean)

There are many more to test.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/Pipeline.png" title="Pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example of pipeline
</div>

### Timing is everything
If you are playing "Where's Waldo" with 2000 people, he will be harder to spot than if you are only playing with 2 people.

The same principle applies to the analysis of brain signals related to a specific task. Trying to extract meaningful brain information from long time intervals (> 200 ms) will be challenging and likely yield unsatisfactory results.



## 🤔 What we don't know (yet) 🤔

### Which combination is the best?
A systematic analysis (or even better, a meta-analysis) of every possible combination will help identify (1) every step of the pipeline and (2) which ones give similar results with other recording modalities.

### Is source localization the real truth?
Yay for multi-modal brain signals analysis! 

If the same results are obtained with EEG and fNIRS (functional Near-Infrared Spectroscopy) or MEG (magnetoencephalography), then they are more likely to have been adequately processed by whatever methods were enforced.

### Can SLST be used for diagnosis?
SLST identifies recurrent brain sources across multiple trials for specific tasks. With a well-thought-out experiment, it might also be able to identify brain regions systematically activated by a specific disease.

---
