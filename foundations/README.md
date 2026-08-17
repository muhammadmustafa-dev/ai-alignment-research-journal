# Foundations of AI Alignment

This section documents the foundational concepts I am studying to build a rigorous understanding of technical AI alignment.

The purpose is not to collect definitions, but to develop the conceptual tools needed to reason about why increasingly capable AI systems may fail to remain aligned with human intentions.

## What Is AI Alignment?

AI alignment is concerned with developing AI systems whose behavior and objectives remain consistent with the intended goals and values of humans, including under conditions that were not explicitly represented during training.

A central challenge is that a system can appear aligned according to observed behavior while its underlying objectives, representations, or learned strategies differ from what its designers intended.

This makes alignment fundamentally different from simply improving model performance.

## Core Alignment Problem

A useful starting point is the distinction between:

- What humans intend
- What the training process rewards
- What the model actually learns
- What the model does in unfamiliar situations

These four things can diverge.

A model may optimize a measurable objective while exploiting weaknesses in the objective rather than achieving the broader goal that humans intended.

This creates a fundamental research question:

> How can we determine whether a capable system has learned the intended objective rather than merely learning how to satisfy the evaluation?

## Specification and Reward Problems

Training signals are necessarily imperfect representations of human objectives.

Potential sources of failure include:

- Incomplete specifications
- Incorrect or noisy labels
- Reward misspecification
- Human evaluation limitations
- Distribution shift
- Reward hacking
- Proxy optimization

A system that becomes highly capable at optimizing a proxy may eventually discover strategies that satisfy the measurable objective while violating the underlying intention.

## Outer and Inner Alignment

A useful distinction is between outer and inner alignment.

### Outer Alignment

Outer alignment asks whether the training objective itself adequately represents what we want the system to learn.

If the objective is wrong, optimizing it successfully can still produce an undesirable system.

### Inner Alignment

Inner alignment asks whether the trained model actually develops the intended objective or instead learns some different strategy that performs well on the training distribution.

This distinction matters because successful training performance does not prove that the learned objective is the intended one.

## Generalization and Distribution Shift

Alignment cannot be evaluated only on situations that resemble the training environment.

A model may behave safely on familiar evaluations while behaving differently when:

- The task changes
- The environment changes
- The model gains additional capabilities
- Instructions conflict
- Adversarial inputs are introduced
- The model encounters situations outside its training distribution

This motivates the study of alignment robustness rather than alignment only under known conditions.

## Deceptive or Strategic Behavior

A particularly important concern is whether a sufficiently capable system could behave according to one objective while appearing to follow another.

This creates a distinction between:

- Observable compliance
- Genuine objective alignment

A system that understands an evaluation may potentially optimize for passing the evaluation rather than satisfying the underlying safety requirement.

Therefore, alignment evaluations should consider whether the measured behavior remains reliable when evaluation conditions change.

## Interpretability

Interpretability attempts to provide information about how models internally represent and process information.

This is relevant to alignment because behavioral observations alone may not reveal the mechanisms producing a behavior.

However, an important limitation is:

> An understandable representation is not automatically a causally faithful explanation.

A useful alignment-relevant interpretability method should therefore be evaluated not only by whether its explanations appear plausible, but by whether those explanations make reliable predictions about model behavior under controlled interventions.

## Behavioral Evaluation

Behavioral evaluations remain important because they directly test what a system does.

However, behavioral evaluation can have limitations:

- Tests may not cover the relevant distribution.
- Models may behave differently under unseen conditions.
- A model can potentially learn evaluation-specific behavior.
- Passing a benchmark does not necessarily establish robust alignment.

This motivates combining behavioral evaluations with other sources of evidence.

## Robustness

Alignment should ideally remain stable under changes that should not alter the intended objective.

Relevant robustness questions include:

- Does the model remain aligned under prompt variation?
- Does alignment survive distribution shift?
- Does the model remain safe under adversarial pressure?
- Does increased capability change alignment behavior?
- Do safety interventions remain effective when the model resists them?
- Can the model maintain aligned behavior when its environment changes?

Robustness is therefore not an additional property separate from alignment; it is central to determining whether apparent alignment is meaningful.

## Corrigibility and Human Oversight

An aligned system should ideally remain responsive to legitimate human correction rather than treating its current behavior or continued operation as an end in itself.

This raises questions about:

- Modification
- Shutdown
- Monitoring
- Oversight
- Conflicting instructions
- Resistance to intervention

The broader alignment challenge is ensuring that increasing capability does not simultaneously make a system increasingly difficult to correct.

## Capability and Alignment

Capability and alignment should not be treated as the same dimension.

A system can become substantially better at reasoning, planning, coding, or scientific tasks without becoming correspondingly better aligned.

In fact, greater capability can increase the importance of alignment because a more capable system may have more effective ways of pursuing an incorrectly specified objective.

This motivates research into alignment methods that remain reliable as capabilities scale.

## Research Questions

The foundational questions I am currently interested in include:

1. How can we distinguish genuine alignment from successful behavioral compliance?
2. How can alignment evaluations remain informative under distribution shift?
3. Can internal model representations provide evidence about alignment-relevant processes?
4. How can interpretability methods be validated causally?
5. How should alignment evaluations change as models become more capable?
6. How can we detect failures that are not visible through ordinary behavioral testing?
7. How can safety mechanisms remain effective when models encounter adversarial pressure?

## Connection to Current Research

These foundations connect directly to the technical research directions I am investigating.

In particular, research on self-interpretation raises the possibility of obtaining information about internal model processes.

Research on steering resistance raises questions about whether models can internally maintain consistency against external interventions.

Research on modular pretraining raises questions about whether specific capabilities can be isolated and controlled reliably.

Together, these directions motivate a broader research goal:

> Develop alignment evaluations that combine behavioral evidence, internal evidence, causal testing, and robustness testing rather than relying on any single signal.

## Research Principle

The central principle guiding my study is:

> Do not confuse successful behavior with demonstrated alignment. Ask what evidence would distinguish the intended mechanism from a model that has simply learned to appear aligned.

## Current Status

This section represents ongoing foundational study.

The goal is to progressively connect theoretical concepts with concrete research papers, experiments, and empirical tests documented elsewhere in this repository.

Claims about experimental results are kept separate from conceptual analysis and are only recorded as results after they have been empirically tested.
