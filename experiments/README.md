# Experiments

This section documents experimental work related to technical AI alignment research.

The goal is to move from conceptual understanding to reproducible empirical investigation. Each experiment is treated as a test of a specific hypothesis rather than as a demonstration designed to confirm a preferred conclusion.

## Current Experimental Focus

The initial experimental direction is motivated by a question arising from research on model self-interpretation:

> Can an interpretation of a model's internal activity make reliable predictions about what will happen when the underlying internal process is causally perturbed?

This focuses on the distinction between an interpretation that is merely correlated with model behavior and one that provides evidence about a causally relevant mechanism.

## Core Hypothesis

If a model's self-interpretation captures a causally meaningful internal process, then the interpretation should provide predictive information about the effects of controlled interventions on that process.

A stronger interpretation should therefore do more than describe an observed activation pattern. It should allow testable predictions about changes in model behavior following interventions.

## Experimental Question

The initial investigation asks:

> When a model associates an internal state with a particular semantic or computational description, does modifying that internal state produce the behavioral change predicted by the description?

The experiment is designed to distinguish three possibilities:

1. The interpretation is causally informative.
2. The interpretation is correlated with the relevant computation but does not identify its causal mechanism.
3. The interpretation is primarily a plausible explanation generated from observable patterns without reliable causal information.

## Experimental Logic

The investigation follows a simple sequence:

1. Select a model and a controlled task.
2. Establish a baseline behavior.
3. Measure or identify an internal representation associated with the behavior.
4. Obtain an interpretation of that internal activity.
5. Form a prediction based on the interpretation.
6. Apply a controlled intervention to the relevant internal representation.
7. Measure the resulting behavioral change.
8. Compare the observed change with the prediction.
9. Repeat under different prompts or task conditions.
10. Record both successful predictions and failures.

The important outcome is not simply whether the model produces a convincing explanation. The important outcome is whether the explanation survives empirical testing.

## Controls

A meaningful experiment should include controls that help distinguish causal effects from correlations.

Potential controls include:

- Intervening on unrelated internal components.
- Applying interventions of different magnitudes.
- Testing equivalent prompts with different wording.
- Testing the same interpretation across multiple task instances.
- Comparing predicted behavioral changes with randomly selected intervention targets.
- Measuring baseline behavior before and after intervention.

These controls are intended to reduce the possibility that an apparent relationship is caused by prompt-specific or task-specific correlations.

## Robustness Tests

If an interpretation appears predictive in an initial setting, the next question is whether that result generalizes.

The investigation should therefore consider:

- Prompt variation
- Task variation
- Distribution shift
- Adversarial or deliberately challenging inputs
- Different intervention strengths
- Different model states or checkpoints where feasible

A result that only works under the exact conditions used to discover the interpretation would provide weaker evidence than a result that generalizes to previously unseen conditions.

## Failure Cases

Negative results are considered useful research outcomes.

An interpretation may fail because:

- The identified representation is correlated with behavior but not causally responsible for it.
- The intervention affects multiple computations simultaneously.
- The interpretation is too coarse to make precise predictions.
- The model relies on redundant representations.
- The interpretation works only for a narrow task or prompt distribution.
- The intervention changes the model in ways unrelated to the original hypothesis.

Documenting these failures is important because they reveal limitations of the proposed methodology.

## Evaluation Criteria

The experiment should evaluate:

- Predictive accuracy of the interpretation
- Consistency across repeated trials
- Sensitivity to controlled interventions
- Specificity of the causal effect
- Robustness across task and prompt variation
- Difference between targeted and control interventions

The strongest evidence would be an interpretation that predicts intervention outcomes substantially better than appropriate controls and continues to do so under changed conditions.

## Alignment Relevance

This experimental direction is relevant to alignment because increasingly capable systems may behave acceptably during ordinary evaluations while relying on internal processes that are poorly understood.

If self-interpretation can provide reliable information about those processes, it could become an additional signal for alignment evaluation.

However, the methodology should not be treated as inherently trustworthy. A model capable of producing explanations may also produce explanations that are incomplete, strategically misleading, or disconnected from the mechanisms responsible for its behavior.

Therefore, causal testing and adversarial validation are central to the research question.

## Recursive Self-Improvement Consideration

A particularly important long-term question is whether this methodology remains useful as systems become capable of modifying or improving their own behavior.

A model could potentially learn to preserve the externally measured properties of an interpretation while changing internal processes that the evaluation does not capture.

For this reason, behavioral agreement alone should not be treated as sufficient evidence of alignment.

The more important question is whether interpretations remain causally predictive when the system is exposed to new capabilities, new environments, and stronger optimization pressures.

## Research Status

This repository currently documents experimental hypotheses, methodology, controls, and planned evaluation criteria.

No experimental result is claimed unless it has actually been executed and recorded.

Future results will be documented separately from hypotheses and expectations so that observed evidence is clearly distinguished from prior assumptions.

## Research Standard

The experimental standard for this repository is:

> State the hypothesis clearly, define what would falsify it, test it against appropriate controls, document failures, and avoid treating plausible explanations as evidence without empirical validation.
