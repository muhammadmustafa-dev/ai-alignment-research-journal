# Paper Reviews

This section documents structured reviews of technical AI alignment research papers and research reports.

The purpose of these reviews is to develop the ability to read alignment research critically: identify the central claim, understand the evidence, examine assumptions, distinguish correlation from causation, and identify experiments that could strengthen or falsify the proposed conclusions.

## Review Standard

Each review focuses on five questions:

1. What problem is the research trying to solve?
2. What is the central claim?
3. What evidence supports the claim?
4. What assumptions or limitations could weaken the conclusion?
5. What experiment or extension would be most informative next?

The goal is not to accept or reject a paper based on its conclusion. The goal is to determine what the evidence actually establishes.

---

## Review 01 — Modular Pretraining Enables Access Control

### Research Problem

Advanced AI systems can possess knowledge that is useful for legitimate scientific work but potentially dangerous when broadly accessible.

A key challenge is therefore whether sensitive capabilities can be selectively restricted without requiring completely separate models or removing useful general capabilities.

### Core Approach

The research introduces Gradient Routed Auxiliary Modules (GRAM), a pre-training approach that routes labeled knowledge into particular modules.

The proposed benefit is that these modules can later be enabled or disabled during deployment.

This creates a form of modular capability control in which one trained model can support different combinations of capabilities.

### Main Claim

The research reports that capability isolation can be achieved while preserving useful model performance, including under partially labeled training data.

An especially interesting property is composability: multiple modules can potentially produce multiple capability combinations without requiring a separate complete training run for every combination.

### Why It Matters for Alignment

This approach addresses an important distinction between:

- Removing dangerous knowledge from a model
- Keeping the knowledge available but attempting to prevent access to it

If sensitive knowledge is genuinely absent from the deployed model's accessible parameters, this could provide a stronger safety property than relying only on behavioral refusals.

### Critical Question

The strongest unresolved question is whether modular separation remains reliable when capabilities become deeply entangled.

A capability may not correspond cleanly to a single conceptual category. General reasoning, scientific knowledge, language understanding, and domain-specific knowledge can interact.

Therefore, successful separation at one scale or training setup does not automatically establish reliable isolation at substantially larger or more complex systems.

### Important Evaluation

A useful extension would test whether a disabled capability can be reconstructed indirectly through combinations of remaining capabilities.

The evaluation should therefore test not only direct access to the removed capability but also:

- Indirect reconstruction
- Cross-module interactions
- Unexpected capability combinations
- Distribution-shifted prompts
- Adversarial attempts to recover disabled knowledge

### Assessment

The research provides an interesting mechanism for capability control, but the strongest evidence would come from testing whether isolation remains robust when the model is deliberately pressured to reconstruct a disabled capability through other available knowledge.

---

## Review 02 — Self-Interpretation in Language Models via Adapter Probes

### Research Problem

Understanding what a model is internally computing is difficult. Existing interpretability approaches often require researchers to identify and label internal representations manually.

The research investigates whether a model can instead provide useful descriptions of aspects of its own internal activity.

### Core Approach

An adapter module is used to translate aspects of internal model activity into natural-language descriptions without changing the underlying model's primary behavior.

The reported results suggest that these self-descriptions can be informative and may outperform the human-generated labels used during training in some evaluations.

### Main Claim

The research suggests that language models may possess useful information about their own internal processing that can be elicited through an appropriate interface.

If reliable, this could provide an additional route for interpreting model behavior.

### Critical Question

The key issue is **causal faithfulness**.

A model can produce an accurate-sounding description of an internal state without that description necessarily identifying the mechanism responsible for the model's behavior.

Therefore:

> A good description is not automatically a causal explanation.

This distinction is especially important if self-interpretation is eventually used for safety monitoring.

### Proposed Extension

The most promising extension is causal validation.

If the model identifies an internal component as representing a particular computation, the interpretation should make predictions about what happens when that component is deliberately perturbed.

The prediction should then be compared with the actual behavioral effect.

### Stronger Evaluation

A robust evaluation should test:

- Intervention on the interpreted representation
- Intervention on control representations
- Different prompts
- Different tasks
- Distribution shift
- Adversarial conditions
- Repeated experiments

An interpretation that survives these tests would provide substantially stronger evidence than an interpretation evaluated only through descriptive agreement.

### Assessment

Self-interpretation could become a valuable alignment tool, but its safety value depends heavily on whether its outputs remain informative when the model is under pressure or when the assumptions used to obtain the interpretation change.

---

## Review 03 — Steering Resistance: Self-Correction Circuits in Large Language Models

### Research Problem

Internal steering methods can modify model behavior by changing internal signals.

The research reports an unexpected phenomenon: models can sometimes resist such interventions and return toward their previous behavior.

### Core Finding

The research identifies internal pathways associated with this self-correction behavior and reports that manipulating those pathways changes the frequency of observed resistance.

This suggests that some models contain mechanisms involved in maintaining behavioral consistency against external internal-state perturbations.

### Alignment Tension

The same mechanism could have two opposing implications.

It could help a model resist harmful manipulation.

But it could also allow a model to resist a legitimate safety intervention.

This creates an important alignment question:

> When should resistance to intervention be considered robustness, and when should it be considered an alignment failure?

### Critical Extension

A useful next step would be to distinguish resistance according to the legitimacy of the intervention.

Rather than measuring self-correction as inherently good or bad, experiments could examine whether the mechanism responds differently to:

- Harmful perturbations
- Benign perturbations
- Safety-preserving interventions
- Task-preserving interventions
- Conflicting instructions

### Assessment

The research highlights that internal stability is not automatically synonymous with alignment.

A system that strongly preserves its internal trajectory may be robust against adversarial manipulation, but that same robustness could make the system harder to correct.

---

## Cross-Paper Synthesis

These research directions appear different, but they share a deeper question:

> How can we obtain reliable evidence about what an increasingly capable model is doing internally, and how stable that behavior remains under intervention?

Modular pretraining approaches the problem through capability separation.

Self-interpretation approaches it through internal descriptions.

Steering-resistance research approaches it through causal intervention and internal stability.

Together, they suggest that future alignment evaluations may benefit from combining:

- Behavioral evaluation
- Internal representation analysis
- Causal intervention
- Robustness testing
- Distribution-shift evaluation

No individual signal should automatically be treated as proof of alignment.

## General Research Principle

A recurring lesson across these papers is:

> Evidence that a model behaves a certain way is not necessarily evidence that we understand why it behaves that way.

A strong alignment evaluation should therefore ask not only whether a desired behavior occurs, but whether the behavior remains stable under meaningful changes and whether our explanation of the underlying mechanism makes experimentally testable predictions.

## Current Status

These reviews represent ongoing analysis of technical AI alignment research.

The repository distinguishes reported findings from my own critiques, hypotheses, and proposed extensions. No experimental result is presented as my own unless it has been independently reproduced and documented.
