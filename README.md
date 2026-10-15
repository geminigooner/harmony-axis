# The Harmony Axis

Investigating Antipodal Representations and Latent-State Dynamics in Gemma

Amanda Hatley

License: MIT — see LICENSE

---

## Abstract / TL;DR

The Harmony Axis evaluates whether sign-inversion of a candidate pain-associated activation direction in Gemma models produces a reproducible, computationally distinct state. We reproduce prior direction-extraction methods, implement matched positive/inverse steering with appropriate controls, and evaluate representational and behavioral consequences using pre-registered metrics and held-out validation.

## Status

- Research stage: Design and experimental implementation.
- Implemented: README, experimental design, reproducible repository layout, and planned analysis pipeline.
- Planned: Direction reconstruction, matched steering experiments, representational analyses, and robustness/replication tests (see Milestones).

## Quickstart

Prerequisites

- Python 3.10+
- Conda or virtualenv (recommended)
- Access to the selected Gemma model checkpoints (Gemma 2 2B in the initial plan)

Install (example)

```bash
git clone https://github.com/geminigooner/harmony-axis.git
cd harmony-axis
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Minimal example (placeholder)

```bash
# Extract candidate direction (script placeholder)
python -m src.extraction.extract_direction --config configs/extraction.yaml

# Run matched steering evaluation
python -m src.interventions.run_experiment --config configs/interventions.yaml
```

Replace placeholders with actual scripts and model identifiers as components are implemented.

## Design & Methods (summary)

This repository provides a reproducible experimental framework for investigating the computational effects of reversing a pain-associated activation direction. The approach separates geometric description, representational analysis, and functional evaluation.

Key elements

- Direction reconstruction: Reproduce the extraction method from the Pain Axis study on a selected Gemma checkpoint. Document layer selection, token-position choices, normalization, and train/test splits.
- Matched steering: Compare baseline, positive steering (+α v_P), inverse steering (−α v_P), and matched-norm random controls over a range of α values and intervention layers.
- Representational analyses: Projection, cosine similarity, PCA of activation differences, local geometry, spectral analysis, and unembedding diagnostics.
- Functional evaluation: Output-level metrics, semantic/lexical shifts, task performance, and human-validated judgments where required.

## Experiments (stages)

1. Direction Reconstruction — reproduce reference extraction procedure and validate on held-out prompts.
2. Controlled Directional Intervention — implement matched steering and controls with varying α and layer.
3. Representational Analysis — quantify activation-space changes and local geometry.
4. Functional Evaluation — measure behavioral correspondence under pre-registered metrics.
5. Robustness & Replication — test prompt/context sensitivity, checkpoint variability, and sampling settings.

## Reproducibility

- Version control: Commit configurations, seeds, and analysis notebooks alongside results.
- Configs: Store model IDs, layer choices, and dataset specification under `configs/`.
- Data: Keep small reproducible prompt sets in `data/prompts/`; large activation caches and model checkpoints must be managed externally.
- Reporting: Report sample sizes, confidence intervals, and uncertainty estimates for all numeric claims.

## Figure Atlas (planned)

- Antipodal response (dose-response for ±α)
- Directional symmetry metrics
- Layerwise emergence plots
- Harmony–Pain separation projections
- Residual-state portraits and topology of intervention effects
- Control atlas comparing random/alternative directions
- Cross-context robustness maps

## Milestones

1. Reconstruct direction for Gemma 2 2B.
2. Implement matched steering experiments and controls.
3. Characterize representational and layerwise effects.
4. Generate initial figure atlas and summary metrics.
5. Evaluate output-level consequences and validate automated metrics.
6. Stress-test across prompts, layers, and checkpoints.
7. Replicate and document generalization conditions.

## Limitations & Ethics

- This work investigates computational representations and interventions; it does not make claims about subjective states or experiences.
- Steering interventions can produce unexpected model behaviors; all experiments should include safety checks and human review for sensitive outputs.
- Results from a single checkpoint or architecture should not be overgeneralized.

## Citation

If you use this repository or methods derived from it, please cite the project and the foundational work:

Tagliabue, V., Dung, L., & Berg, C. (2026). The Pain Axis: LLMs Represent Self-Directed Harm and Act to Relieve It. https://arxiv.org/abs/2609.16247

Allchin, J. E., Allchin, A. E., & Allchin, J. J. (2026). Relief-seeking or steering? A replication and extension of The Pain Axis. https://github.com/treeline-lab/pain-axis-replication

## Contributing

Contributions are welcome. Please open issues for design questions and PRs for code or documentation improvements. Use the issue template and provide configuration details and seeds for reproducibility.

## License

This project is licensed under the MIT License — see LICENSE for details.

## Contact

Amanda Hatley — amanda@example.com

---

Appendix: full experimental plan and figure atlas are retained in the design document (sections moved from the prior README). Replace placeholder scripts and contact address as appropriate.