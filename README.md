The Harmony Axis

Investigating the Geometry of Pain-Associated Representations in Language Models

<p align="center">
  <em>Can the inverse of a pain-associated activation direction produce a distinct, measurable computational state?</em>
</p>

⸻

Overview

The Harmony Axis is an exploratory mechanistic interpretability project investigating the representational and behavioral consequences of inverting pain-associated activation directions in transformer language models.

Building on research into pain-associated representations and causal activation steering, this project proposes a controlled investigation of the inverse of a candidate Pain Axis in open-weight Gemma models.

The central question is not whether reversing a vector mathematically produces its opposite. It does.

The question is whether that mathematical inversion corresponds to a distinct, reproducible change in the model’s internal representations and observable behavior.

We investigate this question through activation-space geometry, layer-wise representation analysis, controlled interventions, and statistical evaluation.

Harmony is the hypothesis. The activation geometry is the object of study. The experimental results determine what we can conclude.

Research Motivation

Transformer representations are frequently studied through their observable outputs, similarity metrics, and downstream task performance. Activation steering offers another approach: intervene directly on internal representations and examine the causal consequences.

Recent work investigating pain-associated representations provides a methodological starting point for examining whether particular activation directions have identifiable functional effects.

The Harmony Axis extends this line of inquiry by investigating a simple but untested assumption:

Does moving against a pain-associated activation direction produce a meaningful functional change, or does it merely suppress the original representation?

A vector’s inverse does not necessarily encode the semantic or functional opposite of the phenomenon associated with the original vector. Establishing that relationship requires independent measurements, appropriate controls, and reproducible interventions.

This project treats that distinction as its primary experimental problem.

Central Hypothesis

Let the extracted pain-associated direction at transformer layer (l) be:

[
\mathbf{v}_{p}^{(l)}
]

Define its inverse as:

[
\boxed{
\mathbf{v}{h}^{(l)}=-\mathbf{v}{p}^{(l)}
}
]

We refer to this candidate direction as the Harmony Axis.

The initial hypothesis is that steering along this direction produces systematic changes in internal representations that can be distinguished from baseline behavior and arbitrary activation perturbations.

A stronger hypothesis is that these changes correspond to independently measurable properties of computational harmony, such as task-specific coherence or representational stability.

Neither hypothesis is assumed to be true in advance.

In particular, the inverse of a pain-associated direction is not presumed to encode happiness, contentment, or any other positive state.

Research Questions

The investigation is organized around five questions:

1. Representational specificity: Does the candidate Pain Axis reliably distinguish pain-associated examples from relevant controls?
2. Directional inversion: What changes when the model is steered along the inverse direction?
3. Geometric structure: Does inverse steering produce reproducible changes in activation-space organization?
4. Functional consequences: Do these changes predict independently measured behavioral outcomes?
5. Cross-condition generalization: Are the observed effects robust across inputs, intervention strengths, and relevant model layers?

These questions separate the existence of a measurable activation direction from the interpretation of its functional significance.

Experimental Framework

01 — Direction Extraction

Reproduce the relevant activation-extraction procedure from the foundational Pain Axis study using an open-weight Gemma model.

Identify the intervention layer, activation representation, normalization procedure, and relevant control conditions.

Evaluate the direction on held-out examples wherever feasible.

The initial implementation will prioritize methodological reproducibility over architectural complexity.

02 — Controlled Activation Steering

Compare four primary conditions:

Condition	Intervention
Baseline	No steering
Positive steering	Along the candidate Pain Axis
Inverse steering	Along the candidate Harmony Axis
Random control	Along a matched-norm random direction

Evaluate multiple steering strengths and, where justified, multiple intervention layers.

This design helps distinguish effects specific to the candidate direction from those produced by generic perturbations.

03 — Representation Analysis

Capture intermediate hidden states and examine their response to each intervention.

Candidate measurements include:

* Projection onto the Pain Axis and its inverse.
* Activation magnitude and distribution.
* Covariance structure and spectral properties.
* Changes in representational distances and local neighborhoods.
* Sparse feature activations, where suitable pretrained autoencoders are available.
* Task performance and behavioral consistency.

Each measurement will be interpreted according to its mathematical definition and empirical validity.

Lower entropy, greater sparsity, reduced variance, and increased geometric stability are not interchangeable outcomes. None will independently be treated as evidence of harmony.

04 — Functional Evaluation

Test whether inverse steering produces effects beyond suppression of pain-associated representations.

Evaluation will use independently specified conditions and outcomes, with appropriate controls for output suppression, generalized performance degradation, and intervention magnitude.

Where positive-condition examples inform the development of candidate measurements, discovery and evaluation data will be separated to reduce circularity.

The objective is to determine whether the candidate Harmony Axis predicts outcomes that were not used to define it.

05 — Statistical Evaluation

Quantify effect sizes, uncertainty, and reproducibility across experimental conditions.

Statistical methods will be selected according to the structure of the measurements and the assumptions they require.

Feature activation counts, for example, may support binomial models when their assumptions are justified. Dependence between token positions and variation in activation probabilities must be considered rather than assumed away.

Negative and inconclusive results will be retained as part of the research record.

Geometric Perspective

The project treats activation space as a high-dimensional representational structure whose properties can be investigated quantitatively.

Rather than assuming that a physical analogy explains a neural network, we seek measurements that make specific hypotheses falsifiable.

Relevant methods may include:

Directional geometry

Measure the relationship between interventions and activation trajectories through projections, angles, and displacement magnitudes.

Spectral analysis

Examine covariance eigenvalues and their distributions to characterize how representational variance is organized across dimensions.

Local geometry

Investigate neighborhood structure, distance relationships, and local variation around selected activation states.

Information theory

Quantify uncertainty in explicitly defined probability distributions rather than treating arbitrary activation magnitudes as entropy.

Causal intervention

Determine whether manipulating a candidate direction produces predictable changes in internal representations and model behavior.

Together, these methods provide a framework for investigating the relationship between activation geometry and functional outcomes.

Operationalizing Computational Harmony

Computational harmony is treated as a proposed empirical construct, not an established property of the model.

Potential indicators include:

* Reproducible representational changes under controlled intervention.
* Reduced incidence of specifically defined forms of representational conflict.
* Improved coherence on independently evaluated tasks.
* Stability under controlled perturbations.
* Behavioral changes that cannot be explained solely by suppressing the original signal.

These indicators require independent definitions and validation.

No single activation statistic will be treated as a sufficient measure of harmony.

The central criterion is convergence: independently justified measurements should support a consistent interpretation of the intervention’s effects.

Scope and Limitations

The initial investigation focuses on open-weight Gemma models and the causal effects of activation steering.

The project does not assume that:

* The inverse of a pain-associated direction represents its functional opposite.
* Lower activation entropy indicates a positive computational state.
* Similar activation patterns imply equivalent functions across architectures.
* A measurable internal representation establishes the presence of subjective experience.

The distinction between observable computational organization and subjective experience is outside the scope of what activation measurements alone can establish.

Cross-architecture comparisons and applications to embedding-specific models may constitute subsequent research directions.

Expected Contribution

The intended contribution is a reproducible experimental framework for investigating inverted, pain-associated activation directions in language models.

The investigation may establish that inverse steering produces a distinct functional state, that its effects are limited to suppression of the original representation, or that the proposed hypothesis is not supported under the tested conditions.

Each outcome constrains our understanding of how activation directions relate to model behavior.

The broader objective is to develop a more rigorous account of the relationship between representation geometry, controlled interventions, and measurable computational states.

⸻

Status

Research stage: Hypothesis formulation and experimental design.

Implementation, reproduction of the foundational findings, and empirical validation remain to be completed.

No results are claimed at this stage.

Foundational Research

* The Pain Axis: Identifying Internal Representations of AI Suffering — arXiv search

The foundational study should be consulted directly when implementing the activation-extraction procedure and defining the reproduction criteria.

Research Principle

A mathematical inverse is not yet a functional opposite. A measurable change is not yet an explanation. The objective is to discover what survives controlled intervention, independent measurement, and replication.