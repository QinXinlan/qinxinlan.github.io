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
---


## 🎓 What we know 🎓

### The best pipeline (so far)

So many algorithms, so little time. 

So far, the results _I_ obtained rank in terms of accuracy for the following steps in the pipeline (with a top accuracy of ~94% on my dataset % cite guttmannflury2024dataset): 
- Blink correction:
1. ABCD (Adaptive Blink Correction and De-drifting) [{% cite guttmannflury2023thesis guttmannflury2019abc guttmannflury2019prabc %}  ]
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
3. Covariance matrix

- Classification:
1. Dual classifier [{% cite guttmannflury2023thesis %}]
2. LDA (Linear Discriminant Analysis)
3. SVM (Support Vector Machine)
4. TS (Tangent Space)
5. MDRM (Minimum Distance to Riemannian Mean)

There are many more to test. And more importantly, why one is better than the other in a given context?

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

 The same idea applies to analyzing brain signals related to specific tasks. Extracting meaningful brain information from long time intervals (over 200 ms) can be like searching for a needle in a haystack.

The signal of interest (SOI) is often smaller than the background noise. That's why we need to try to precisely target _when_ the SOI is supposed to happen. Essentially, we are searching for time-adaptive repeated patterns (within some variability), meaning Event-Related Potentials (ERP) that may have specific functional and spectral characteristics. It seems reasonable to assume that several brain regions will be activated by a task, and probably at different times.

---

## 🤔 What we don't know (yet) 🤔

### What’s the Best Combination?
A systematic analysis — or even better, a meta-analysis — of all possible combinations will help identify 
(1) every step of the pipeline
(2) which ones give similar results across different recording modalities
(3) _why_ a given combination performs better than another.

### Is source localization the real truth?
Yay for multi-modal brain signals analysis! 

If we can achieve consistent results using different modalities like EEG, fNIRS (functional Near-Infrared Spectroscopy), or MEG (magnetoencephalography), it’s more likely that the methods used have identified and processed the signals correctly.

### Can SLST be used for diagnosis?
SLST identifies recurrent brain patterns across multiple trials for specific tasks. With a well-thought-out experiment,  it could potentially identify brain regions or patterns that are consistently activated by specific diseases.

---
