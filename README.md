# The Harmony Axis

Antipodal Representations and Latent-State Dynamics in Gemma

Amanda Hatley

A mechanistic interpretability study of inverse steering, representational geometry, and computational state differentiation.

## Abstract

The Harmony Axis investigates whether sign-inversion of a pain-associated activation direction in Gemma models produces a reproducible and distinguishable computational state. Building on prior work in pain-associated representations and activation steering, the project examines whether the inverse direction yields measurable changes in model internals and output behavior beyond what is explained by baseline variation or generic perturbation. The repository is structured to support direction reconstruction, matched positive/inverse steering, representational analysis, and robustness checks under controlled experimental conditions.

## Project Aims

1. Characterize directional inversion: determine how positive and inverse steering alter activation patterns across layers, intervention strengths, and task conditions.
2. Establish representational specificity: test whether inverse steering produces effects beyond baseline variation, generic perturbation, or matched control directions.
3. Evaluate functional consequences: assess whether representational changes correspond to reproducible differences in downstream outputs and task performance.

## Research Premise

Reversing an activation direction is mathematically straightforward. Determining whether that reversal produces a distinct computational effect requires controlled experimentation.

Let the pain-associated direction at layer l be:

$$
\mathbf{v}_{P}^{(l)} \in \mathbb{R}^{d}
$$

Its inverse is defined as:

$$
\mathbf{v}_{H}^{(l)} = -\mathbf{v}_{P}^{(l)}
$$

For a residual-stream activation $\mathbf{h}^{(l)}$, the intervention is:

$$
\mathbf{h}'^{(l)} = \mathbf{h}^{(l)} + \alpha\,\mathbf{v}_{H}^{(l)}
$$

where $\alpha$ controls steering magnitude.

The inverse direction is not assumed to be an independently discovered representation. It is the sign-reversed form of the original vector. Whether it produces a distinct functional or representational pattern is an empirical question.

## Status

Current phase: research design and experimental implementation.

Starting model: Gemma 2 2B.

Reference study: The Pain Axis (2026).

Primary objective: determine whether inverse steering produces a reproducible, distinguishable computational effect beyond generic directional perturbation.

## References

- Tagliabue, V., Dung, L., & Berg, C. (2026). The Pain Axis: LLMs Represent Self-Directed Harm and Act to Relieve It.
- Allchin, J. E., Allchin, A. E., & Allchin, J. J. (2026). Relief-seeking or steering? A replication and extension of The Pain Axis.

## Contact

Amanda Hatley — amanda@keito.uk
