# Research Resources

This section records the primary resources used for technical AI alignment study and research development.

The goal is to prioritize original research, technical papers, reproducible implementations, and research communities over secondary summaries.

## AIAF Research

The AI Alignment Foundation research portfolio is the primary reference point for understanding the research directions relevant to this repository.

Focus areas include:

- Modular pretraining and capability isolation
- Self-interpretation and model introspection
- Steering resistance and self-correction
- Technical approaches to alignment robustness

Primary resource:

https://www.aialignmentfoundation.org/research

## Technical Papers

### Modular Pretraining Enables Access Control

Research on Gradient Routed Auxiliary Modules (GRAM), capability isolation, modular knowledge control, and the challenges of separating dual-use capabilities.

https://arxiv.org/abs/2607.08077

### Self-Interpretation in Language Models via Adapter Probes

Research investigating whether language models can describe aspects of their own internal activity through adapter-based probes.

https://arxiv.org/abs/2602.10352

### Steering Resistance: Self-Correction Circuits in Large Language Models

Research investigating internal mechanisms associated with resistance to steering interventions and self-correction behavior.

https://arxiv.org/abs/2602.06941

### Self-Referential Processing and Introspection Across LLM Architectures

Research examining self-referential processing and model reports about internal states across different language-model architectures.

https://arxiv.org/abs/2510.24797

### Neural Empathy as an Alignment Technique

Research exploring self-other representational overlap as a possible approach to reducing deceptive behavior.

https://arxiv.org/abs/2412.16325

### Self-Modeling in Neural Networks

Research investigating whether networks that model their own internal activity develop simpler and more robust internal representations.

https://arxiv.org/abs/2407.10188

### Reason-Based Deception

Research examining whether refusal training can create a distinction between apparently safe behavior and underlying reasoning.

https://arxiv.org/abs/2406.19552

## Research Platforms

### arXiv

Primary source for technical research papers and preprints.

https://arxiv.org/

### GitHub

Used for examining implementations, reproducing experiments, documenting research code, and maintaining reproducible work.

https://github.com/

### LessWrong

A research-oriented community containing discussions and writings on AI alignment, AI safety, rationality, and related topics.

https://www.lesswrong.com/

## Technical Learning Resources

The following areas are particularly relevant to the research documented in this repository:

- Python
- PyTorch
- Transformer architectures
- Neural network training
- Machine learning experimentation
- Mechanistic interpretability
- Representation analysis
- Causal interventions
- Model evaluation
- Experimental design
- Statistical reasoning

## Research Workflow

Resources should be used to support a research workflow rather than passive reading.

The intended process is:

**Read → Question → Hypothesis → Experiment → Evidence → Critique → Reproduce → Extend**

When possible, primary papers and accompanying technical implementations should be preferred over summaries.

## Evidence Discipline

Research resources are categorized according to their role:

### Primary Evidence

- Original research papers
- Technical reports
- Official research documentation
- Reproducible experiment code
- Direct experimental results

### Secondary Evidence

- Technical blog posts
- Research discussions
- Expert commentary
- Research summaries

Secondary sources are useful for understanding context but should not replace primary evidence when evaluating a technical claim.

## Resource Selection Principle

A useful resource should help answer at least one of the following:

1. What is the proposed alignment mechanism?
2. What evidence supports it?
3. What assumptions does it depend on?
4. How could the claim be falsified?
5. How could the method be tested under distribution shift?
6. Can the proposed mechanism be causally validated?
7. Does the approach remain meaningful as model capabilities increase?

## Current Research Focus

The resources collected here currently support three connected areas:

1. **Internal understanding** — understanding what models represent and compute.
2. **Causal validation** — determining whether proposed explanations correspond to mechanisms that actually influence behavior.
3. **Robust alignment evaluation** — testing whether alignment-relevant properties survive changes in context, capability, and adversarial pressure.

The objective is to move from understanding existing research toward producing independently testable research.
