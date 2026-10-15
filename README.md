# The Harmony Axis

Investigating Antipodal Representations and Latent-State Dynamics in Gemma

An exploratory mechanistic interpretability project examining the representational and behavioral consequences of inverting a pain-associated activation direction.

<p align="center">
  <em>When a direction associated with pain is reversed, what changes—and what remains invariant?</em>
</p>

---

## Overview

The Harmony Axis investigates the computational consequences of reversing a pain-associated representation in a language model.

Building on methods introduced in "The Pain Axis: LLMs Represent Self-Directed Harm and Act to Relieve It", this project examines whether the inverse of a pain-associated activation direction produces a distinguishable, reproducible pattern of representational and behavioral change.

The central intervention is mathematically simple:

$$
\mathbf{v}_H = -\mathbf{v}_P
$$

Its interpretation is not.

A vector and its negative occupy opposite directions in activation space, but geometric opposition does not guarantee functional opposition. The inverse may suppress features associated with the original direction, activate different features, produce asymmetric behavioral effects, or yield no meaningful effect under certain conditions.

The objective is to measure these possibilities rather than assume any of them.

The project begins with Gemma and develops a controlled experimental framework for investigating directional inversion, representational geometry, layerwise dynamics, and intervention-dependent behavior.

## Research Questions

### Primary question

Does reversing a pain-associated activation direction produce a computationally distinguishable state, and how does that state differ from the original direction and appropriate controls?

### Secondary questions

1. Directional symmetry: Are the effects of positive and negative steering approximately symmetric, or does the model respond differently to each direction?
2. Representational specificity: Does inverse steering selectively alter features associated with the original direction, or does it produce broader changes in activation structure?
3. Layerwise emergence: At which layers do these effects become detectable, and how do they evolve through the network?
4. Contextual stability: Do the observed effects persist across prompt formulations, linguistic contexts, and task conditions?
5. Behavioral correspondence: Do representational changes correspond to measurable differences in model outputs, beyond changes attributable to generic steering or distribution shift?
6. Geometric structure: Can the relationship between the original direction, its inverse, and control conditions be characterized using projection, similarity, and local representational geometry?
7. Dose response: How do these effects vary with steering magnitude, and do they exhibit thresholds, saturation, or nonlinear transitions?

These questions concern observable computational behavior and representations. They do not presuppose a particular interpretation of the resulting states.

---

## Theoretical Framework

### 1. The Pain-Associated Direction

The foundational reference is the Pain Axis work by Tagliabue, Dung, and Berg (2026).

Their methodology derives activation directions from differences between mean residual-stream activations associated with pain-related inputs and matched controls, with additional processing to reduce control-related variance.

The original paper evaluates these directions through representational discrimination, comparisons with other semantic dimensions, unembedding analyses, and steering interventions.

This project uses that work as a methodological starting point—not as evidence that an inverse direction must represent harmony.

**Reference:** The Pain Axis — arXiv

**Original implementation:** valen-research/Pain-axis

### 2. The Inverse Direction

Let the original pain-associated direction at layer l be:

$$
\mathbf{v}_P^{(l)} \in \mathbb{R}^d
$$

where d is the residual-stream dimensionality.

Define the inverse direction:

$$
\mathbf{v}_H^{(l)} = -\mathbf{v}_P^{(l)}
$$

For a residual-stream activation $\mathbf{h}^{(l)}$, a directional intervention can be expressed as:

$$
\mathbf{h}'^{(l)} = \mathbf{h}^{(l)} + \alpha\,\mathbf{v}_H^{(l)}
$$

where $\alpha$ controls intervention magnitude.

The corresponding positive-direction intervention is:

$$
\mathbf{h}'^{(l)} = \mathbf{h}^{(l)} + \alpha\,\mathbf{v}_P^{(l)}
$$

These interventions provide a controlled comparison between opposing directions.

The inverse vector is not a separately discovered representation. It is defined by reversing the sign of the original vector. Whether that operation produces a meaningful and distinctive computational effect is an empirical question.

### 3. Operationalizing Harmony

In this project, "harmony" is a provisional name for the experimental condition produced by inverse steering.

It is not assumed to be:

- A naturally occurring model state.
- A representation of happiness or well-being.
- A general-purpose positive-valence direction.
- The opposite of every phenomenon associated with pain.
- A unified latent variable shared across models.
- An established property of the model’s internal organization.

The term becomes scientifically useful only insofar as the proposed condition can be operationalized, measured, distinguished from controls, and independently reproduced.

The project therefore separates three levels of analysis:

- Geometric — Activation directions: What changes when the direction is reversed?
- Representational — Features and activation patterns: Which measurable properties change?
- Functional — Model outputs and task performance: Do representational changes correspond to behavioral effects?

Evidence at one level does not automatically establish conclusions at another.

---

## Experimental Architecture

The initial experimental system is organized into five stages.

### Stage I — Direction Reconstruction

Reproduce the reference method for extracting the pain-associated direction in a selected Gemma model.

The reconstruction should document:

- Model checkpoint and tokenizer.
- Layer selection and residual-stream location.
- Dataset composition and prompt templates.
- Token-position selection.
- Activation aggregation.
- Control conditions and variance-reduction procedure.
- Direction normalization.
- Train/test separation and validation strategy.

The initial target is Gemma 2 2B, a practical starting point for inspecting layerwise activation behavior.

The implementation should first reproduce the direction using the original method as closely as possible. Any methodological changes should be documented separately.

### Stage II — Controlled Directional Intervention

Compare the original direction and its inverse under matched conditions.

| Condition | Intervention | Purpose |
|---|---:|---|
| Baseline | None | Establish reference behavior |
| Positive steering | +α\mathbf{v}_P | Measure effects along the original direction |
| Inverse steering | −α\mathbf{v}_P | Measure effects along the inverse direction |
| Random-direction control | Matched-norm random vector | Estimate nonspecific steering effects |
| Alternative control | Independently derived control direction | Test representational specificity |

The experiment should vary steering magnitude and, where feasible, intervention layer.

Matched norms are important: otherwise, apparent directional differences may simply reflect different intervention magnitudes.

The same prompt sets, decoding parameters, and evaluation procedures should be used across conditions.

### Stage III — Representational Analysis

Characterize how the intervention changes the model’s internal activation structure.

Candidate analyses include:

- Directional projection and signed activation displacement.
- Cosine similarity between activation vectors.
- Pairwise distances between condition-level representations.
- Principal component analysis of activation differences.
- Layerwise activation distributions.
- Feature-level analysis using available sparse autoencoders.
- Unembedding comparisons as a diagnostic of changes in token-associated readout.

Where appropriate, compare both absolute activations and intervention-induced changes relative to the same baseline prompts.

A change in projection onto the original direction is not, by itself, evidence of a new or distinct state. Complementary measurements are needed to establish the scope and specificity of the effect.

### Stage IV — Functional Evaluation

Evaluate model outputs under matched baseline, positive-steering, inverse-steering, and control conditions.

Possible measurements include:

- Output-category frequencies.
- Semantic similarity and lexical shifts.
- Task performance.
- Response consistency across repeated trials.
- Prompt sensitivity.
- Behavioral differences across intervention strengths.

Evaluation criteria should be defined before inspecting final results wherever practical.

Automated judgments may be useful, but they should be validated against transparent criteria and, when appropriate, human review.

Changes in wording alone should not be interpreted as evidence of a corresponding internal state.

### Stage V — Robustness and Replication

Test whether the findings survive changes in:

- Prompt wording.
- Prompt category.
- Random seed or sampling configuration.
- Steering magnitude.
- Intervention layer.
- Evaluation method.
- Model checkpoint, where resources permit.

Report null results, unstable effects, and failures to reproduce alongside positive findings.

---

## Figure Atlas

The project uses a consistent visual vocabulary to make its experimental results interpretable across conditions and layers.

These names describe planned analyses and visualizations, not results already obtained.

- Figure I — The Antipodal Response: Compare activation and output responses under positive and inverse steering. Plot intervention magnitude against a preregistered measurement of the response.

- Figure II — Directional Symmetry: Quantify the relationship between effects produced by opposing directions.

- Figure III — Layerwise Emergence: Identify where intervention effects become detectable and how they develop across the network.

- Figure IV — The Harmony–Pain Separation Map: Visualize the geometry of representations under the original and inverse interventions in a shared low-dimensional space.

- Figure V — The Residual-State Portrait: Compare activation distributions and intervention-induced changes across conditions.

- Figure VI — Intervention Topology: Characterize how representational and behavioral measurements vary with steering strength.

- Figure VII — The Control Atlas: Establish whether observed effects are specific to the reference direction by comparing with matched-norm random directions and other controls.

- Figure VIII — Cross-Context Robustness: Evaluate whether the effect persists across prompt categories and linguistic formulations.

- Figure IX — Representational Specificity: Determine whether inverse steering selectively affects features associated with the original direction.

---

## Analysis Principles

- Separate geometry from semantics: The fact that two vectors point in opposite directions is a geometric statement. Whether their effects correspond to opposing semantic or behavioral patterns requires independent measurement.
- Distinguish intervention from observation: An intervention tests how the model responds to a controlled perturbation. It does not automatically reveal the meaning of a naturally occurring activation pattern.
- Report uncertainty: Where applicable, report confidence intervals, effect sizes, sample counts, and variation across prompts or runs.
- Keep exploratory and confirmatory analyses distinct: Exploratory analyses can generate hypotheses; confirmatory analyses should specify measurements and comparisons in advance where feasible.
- Preserve negative results: A lack of detectable differentiation is informative and should be reported and investigated.

---

## Scientific Context and Limitations

The Pain Axis provides a starting point for studying pain-associated activation directions and steering interventions. It does not establish that reversing such a direction yields a distinct harmony-associated representation.

An independent replication, treeline-lab/pain-axis-replication, raises methodological questions about interpreting relief-seeking behavior in the original experimental setup. This project treats those questions as reasons to strengthen the experimental design.

The initial implementation is limited to selected model checkpoints, layers, datasets, and intervention configurations. Findings should not be generalized beyond the tested conditions without additional evidence.

---

## Repository Roadmap

The repository is intended to develop into a reproducible experimental pipeline.

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

This is a proposed organizational structure, not a claim that every component has already been implemented.

Experiment configurations, model identifiers, random seeds, and analysis parameters should be versioned alongside corresponding results.

---

## Initial Milestones

1. Reconstruct: Reproduce the reference direction extraction procedure for the selected Gemma checkpoint and validate its basic properties.
2. Invert: Implement matched positive and inverse steering interventions, with baseline and random-direction controls.
3. Characterize: Measure directional projections, activation changes, and layerwise effects.
4. Visualize: Generate the initial figure atlas from measured data, including uncertainty and control comparisons where appropriate.
5. Evaluate: Test output-level consequences using predefined metrics and matched prompts.
6. Stress-test: Investigate robustness across prompt contexts, intervention strengths, and alternative explanations.
7. Replicate: Document the conditions under which the effect does—or does not—generalize.

---

## Current Status

- Phase: Research design and experimental implementation.
- Starting model: Gemma 2 2B.
- Reference method: The Pain Axis.
- Primary intervention: Sign inversion of a pain-associated activation direction.
- Primary objective: Determine whether inverse steering produces a reproducible, distinguishable computational effect beyond the expected consequences of a generic directional perturbation.

No empirical findings are claimed until the relevant experiments have been run and evaluated.

---

## References

- Tagliabue, V., Dung, L., & Berg, C. (2026). The Pain Axis: LLMs Represent Self-Directed Harm and Act to Relieve It.
  - Paper: https://arxiv.org/abs/2609.16247
  - Original implementation: https://github.com/valen-research/Pain-axis

- Allchin, J. E., Allchin, A. E., & Allchin, J. J. (2026). Relief-seeking or steering? A replication and extension of The Pain Axis.
  - Replication repository: https://github.com/treeline-lab/pain-axis-replication

---

<p align="center">
  <em>Opposition is a property of geometry. Meaning is a property to be investigated.</em>
</p>
