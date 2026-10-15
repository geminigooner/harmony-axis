###############################################
#                                             #
#            THE HARMONY AXIS                  #
#               GEMINIGOONER                   #
#                                             #
###############################################

The Harmony Axis

Antipodal Representations and Latent-State Dynamics in Gemma

An exploratory mechanistic interpretability study of inverse steering, representational geometry, and computational state differentiation.

Research premise: Reversing an activation direction is mathematically straightforward. Determining whether that reversal produces a distinct computational effect requires controlled experimentation.

⸻

## Research Question

### Overview

The Harmony Axis investigates the computational consequences of reversing a pain-associated activation direction in a language model.

The project builds on the methodology introduced in The Pain Axis: LLMs Represent Self-Directed Harm and Act to Relieve It by Tagliabue, Dung, and Berg (2026).

The central question is whether the inverse of a pain-associated direction produces a reproducible pattern of representational and behavioral change that can be distinguished from the original direction, baseline behavior, and appropriate controls.

Let the pain-associated direction at layer (l) be:

[\mathbf{v}_{P}^{(l)} \in \mathbb{R}^{d}]

Its inverse is defined as:

[\mathbf{v}_{H}^{(l)} = -\mathbf{v}_{P}^{(l)}]

For a residual-stream activation (\mathbf{h}^{(l)}), the corresponding intervention is:

[\mathbf{h}'^{(l)} = \mathbf{h}^{(l)} + \alpha\,\mathbf{v}_{H}^{(l)}]

where (\alpha) controls steering magnitude.

The inverse direction is not an independently discovered representation. It is the sign-reversed form of the original vector. Whether it produces a distinct functional or representational pattern is an empirical question.

## Project Aims

1. Characterize directional inversion. Determine how positive and inverse steering alter activation patterns across model layers, intervention strengths, and experimental conditions.
2. Establish representational specificity. Test whether inverse steering produces measurable effects beyond those explained by baseline variation, generic activation perturbation, or matched control directions.
3. Evaluate functional consequences. Investigate whether representational changes correspond to reproducible differences in model outputs, and assess the robustness of those effects across contexts.

## Research Hypotheses

The project investigates several competing possibilities:

* Directional symmetry: Opposing directions produce approximately corresponding effects.
* Directional asymmetry: The model responds differently to positive and inverse steering despite equal intervention magnitudes.
* Representational differentiation: Inverse steering produces an activation pattern distinguishable from baseline and control conditions.
* Nonspecific perturbation: Observed changes are adequately explained by generic steering effects rather than direction-specific structure.
* Context dependence: Effects vary substantially across prompts, layers, or task conditions.

These possibilities are not mutually exclusive. The experimental design should allow the evidence to distinguish between them.

## Operational Definition of Harmony

Harmony is a provisional name for the inverse-steering condition under investigation.

It is not assumed to represent happiness, well-being, the universal opposite of pain, or a naturally occurring model state.

The project distinguishes three levels of evidence:

Level | Object of analysis | Research objective
---|---|---
Geometric | Activation directions and distances | Characterize directional relationships
Representational | Residual-stream patterns and features | Identify measurable structural differences
Functional | Generated outputs and task performance | Evaluate intervention-dependent behavior

Evidence at one level does not automatically establish conclusions at another.

⸻

## Methods

1. Reference Method and Direction Reconstruction

The foundational reference is the original Pain Axis study and its published implementation.

The paper derives activation directions by comparing pain-related inputs with matched controls, then applies a variance-reduction procedure to reduce control-related variation. Its evaluation includes representational discrimination, comparisons with other semantic dimensions, unembedding analyses, and steering interventions.

The initial target for this project is Gemma 2 2B, providing a practical starting point for inspecting activation behavior across model layers.

The reconstruction will document:

* Model checkpoint and tokenizer.
* Residual-stream location and candidate layers.
* Prompt datasets and control conditions.
* Token-position selection and activation aggregation.
* Direction extraction and variance-reduction procedures.
* Normalization and validation.
* Training and evaluation separation.

The initial objective is to reproduce the reference methodology as closely as practical before introducing experimental modifications.

2. Controlled Directional Intervention

Positive and inverse steering will be evaluated under matched conditions.

Condition | Intervention | Purpose
---|---|---
Baseline | No intervention | Establish reference behavior
Positive steering | (+\alpha\mathbf{v}_{P}) | Characterize effects along the original direction
Inverse steering | (−\alpha\mathbf{v}_{P}) | Characterize effects along the inverse direction
Random-direction control | Matched-norm random vector | Estimate nonspecific perturbation effects
Alternative-direction control | Independently derived control vector | Test directional specificity

The experiment will vary steering magnitude and, where feasible, intervention layer.

Matched intervention norms are essential: otherwise, differences may reflect perturbation magnitude rather than direction.

Prompt sets, decoding parameters, and evaluation procedures should remain consistent across conditions.

3. Representational Geometry

The representational analysis will investigate how steering changes the structure of model activations.

Candidate measurements include:

* Signed projection onto the original activation direction.
* Cosine similarity between condition-level representations.
* Activation displacement and pairwise distances.
* Principal component analysis of activation differences.
* Layerwise activation distributions.
* Feature-level comparisons using suitable sparse autoencoders.
* Unembedding analyses as a diagnostic of token-associated readout.

Comparisons should include both absolute activations and changes relative to the same unsteered baseline.

A reduction in projection onto the original direction is not sufficient to establish a distinct representational state. Complementary measurements and appropriate controls are required.

4. Functional Evaluation

Model outputs will be evaluated under baseline, positive-steering, inverse-steering, and control conditions.

Potential measurements include:

* Output-category frequencies.
* Semantic and lexical shifts.
* Task performance.
* Response consistency across repeated trials.
* Sensitivity to prompt formulation.
* Behavioral differences across intervention magnitudes.

Evaluation criteria should be defined before inspecting final results wherever practical.

Automated judgments should use transparent criteria and be validated when appropriate. Changes in wording alone should not be interpreted as evidence of a corresponding internal state.

5. Robustness Analysis

The project will test whether observed effects persist across:

* Prompt wording and category.
* Sampling configurations and repeated trials.
* Steering magnitude.
* Intervention layer.
* Evaluation method.
* Model checkpoints, where resources permit.

Exploratory observations will be distinguished from confirmatory findings. Null results, unstable effects, and failures to reproduce will be documented alongside positive results.

6. Planned Figure Atlas

The following figure names define a consistent visualization framework. They describe planned analyses, not completed experiments or established findings.

Figure | Title | Primary analysis
---|---|---
I | The Antipodal Response | Output and activation responses under positive versus inverse steering
II | Directional Symmetry | Similarity and asymmetry between opposing intervention effects
III | Layerwise Emergence | Changes in measured effects across model layers
IV | The Harmony–Pain Separation Map | Low-dimensional visualization of condition-level representations
V | The Residual-State Portrait | Activation distributions and intervention-induced changes
VI | Intervention Topology | Dose-response relationships across steering magnitudes
VII | The Control Atlas | Comparison against random and alternative directions
VIII | Cross-Context Robustness | Variation in effects across prompt conditions
IX | Representational Specificity | Changes in features associated with the reference direction

### Visualization principles

The Antipodal Response will test whether reversing the steering direction reverses, changes, or fails to reproduce the original effect.

Directional Symmetry will compare effect sizes and activation changes under matched positive and negative interventions.

Layerwise Emergence will trace a consistent measurement across model layers to determine where effects become detectable and whether they persist downstream.

The Harmony–Pain Separation Map will visualize baseline, positive-steering, inverse-steering, and control representations in a shared low-dimensional space. Visual separation will be accompanied by quantitative evaluation; a projection is not a complete representation of the model’s internal geometry.

The Residual-State Portrait will distinguish directional changes from broader shifts in activation magnitude or variance.

Intervention Topology will characterize dose-response relationships, including possible asymmetry, saturation, thresholds, or instability.

The Control Atlas will compare the reference direction against multiple matched-norm controls where feasible.

Cross-Context Robustness will report effect sizes and uncertainty across prompt categories.

Representational Specificity will distinguish reduced projection onto the original direction from changes in associated features or the emergence of a reproducible pattern.

⸻

## Status

Current phase: Research design and experimental implementation.

Starting model: Gemma 2 2B.

Reference study: The Pain Axis (2026).

Primary intervention: Sign inversion of a pain-associated activation direction.

Primary objective: Determine whether inverse steering produces a reproducible, distinguishable computational effect beyond the expected consequences of a generic directional perturbation.

## Milestones

* [ ] M1 — Reconstruct: Implement and validate the reference direction-extraction procedure.
* [ ] M2 — Invert: Implement matched positive and inverse steering with baseline and control conditions.
* [ ] M3 — Characterize: Measure directional projections, activation changes, and layerwise effects.
* [ ] M4 — Visualize: Generate the initial figure atlas from measured data.
* [ ] M5 — Evaluate: Test output-level consequences using predefined metrics.
* [ ] M6 — Stress-test: Investigate robustness across contexts, intervention strengths, and alternative explanations.
* [ ] M7 — Replicate: Document which findings generalize and which remain configuration-dependent.

## Current Limitations

No empirical findings are claimed at this stage.

The proposed framework does not assume that:

* The inverse direction corresponds to a naturally occurring model state.
* Geometrically opposite vectors produce semantically opposite effects.
* A change in token probabilities establishes a distinct internal state.
* A visually separated cluster establishes a semantic category.
* A behavioral effect identifies its unique representational cause.
* Results from one checkpoint generalize to other models.

An independent replication and extension of the Pain Axis raises methodological questions about interpreting relief-seeking behavior in the original experimental setup. Its findings motivate controls for timing, task structure, and alternative explanations.

The Harmony Axis will treat these as experimental design considerations rather than assume a particular outcome.

⸻

## Reproducibility

### Experimental Configuration

Each experiment should record:

* Model identifier, checkpoint, and tokenizer version.
* Software dependencies and relevant hardware.
* Dataset version and prompt identifiers.
* Extraction layer and residual-stream location.
* Direction vector and normalization procedure.
* Intervention magnitude and application point.
* Decoding parameters and random seed, where applicable.
* Evaluation metrics and analysis configuration.

### Data and Artifact Organization

The proposed repository structure is:

```
harmony-axis/
├── README.md
├── configs/
│   ├── model.yaml
│   ├── extraction.yaml
│   └── interventions.yaml
├── data/
│   ├── prompts/
│   └── controls/
├── src/
│   ├── extraction/
│   ├── directions/
│   ├── interventions/
│   ├── representations/
│   └── evaluation/
├── experiments/
│   ├── 01_direction_reconstruction/
│   ├── 02_antipodal_intervention/
│   ├── 03_layerwise_emergence/
│   ├── 04_representational_geometry/
│   └── 05_robustness/
├── results/
│   ├── metrics/
│   ├── figures/
│   └── reports/
├── tests/
└── requirements.txt
```

This is a proposed organization, not a claim that every component has been implemented.

### Reporting Standards

Results should include:

1. Baseline comparisons: Establish the behavior and activation statistics of the unsteered model.
2. Control comparisons: Report matched-norm random and alternative-direction controls where appropriate.
3. Effect sizes and uncertainty: Include sample counts and suitable uncertainty estimates.
4. Configuration details: Preserve the parameters needed to reproduce each intervention.
5. Negative results: Record null findings, unstable effects, and unsuccessful replications.
6. Exploratory distinctions: Clearly identify analyses performed after observing the data.
7. Artifact provenance: Associate figures and summary metrics with their underlying experiment configurations.

Large checkpoints and activation caches should be managed separately from ordinary source files.

### Interpretation Standard

The project distinguishes three claims that require different evidence:

* Directional effect: The intervention changes a measured activation or output.
* Representational differentiation: The resulting pattern is distinguishable from baseline and appropriate controls.
* Functional significance: The difference corresponds to a reproducible change in model behavior under a defined evaluation.

Establishing the first claim does not automatically establish the second or third.

⸻

## References

### Foundational study

Tagliabue, V., Dung, L., & Berg, C. (2026). The Pain Axis: LLMs Represent Self-Directed Harm and Act to Relieve It.

* Paper: https://arxiv.org/abs/2609.16247
* Original implementation: https://github.com/valen-research/Pain-axis

### Independent replication and extension

Allchin, J. E., Allchin, A. E., & Allchin, J. J. (2026). Relief-seeking or steering? A replication and extension of The Pain Axis.

* Repository: https://github.com/treeline-lab/pain-axis-replication

⸻

<p align="center">
  <em>Opposition is a property of geometry. Meaning is a property to be investigated.</em>
</p>

---

Contact: Amanda Hatley — amanda@keito.uk
