# Trust Priming — Research Note

## Background

The concept of priming originates from cognitive psychology, where exposure to one stimulus influences a response to a subsequent stimulus. In the context of large language models, priming is typically studied as in-context learning: providing examples or instructions that shape the model's subsequent outputs.

We hypothesize that priming in LLMs extends beyond task performance to include trust-related behaviors — specifically, that an LLM's willingness to trust, follow, or defer to instructions from particular sources can be shaped through prior interaction.

This research note documents our working hypothesis and serves as a foundation for experimental design.

## Research Motivation

### Why Trust Priming Matters

Current prompt injection defenses rely on a core assumption: that the LLM's system prompt or safety instructions maintain stable authority throughout a conversation. If this assumption can be undermined, existing defenses may be circumvented even when they appear technically sound.

Consider the following scenario:

1. An attacker provides context that subtly undermines the reliability of security warnings.
2. Later in the conversation, a legitimate security instruction appears.
3. The model, having been primed, treats the legitimate instruction with reduced trust.

Unlike jailbreaking, the model has not been asked to violate any rules. It has simply been conditioned to re-evaluate the trustworthiness of instruction sources.

### Relationship to Social Engineering

Trust priming in LLMs draws direct parallels to social engineering techniques:

- **Authority undermining**: Convincing a victim that their manager's instructions are unreliable, then issuing fraudulent instructions
- **Trust preconditioning**: Creating a narrative that makes future security warnings seem false or exaggerated
- **Gaslighting**: Gradually eroding a victim's confidence in their own judgement and trusted sources

These techniques are well-documented in human-targeted attacks. We investigate whether analogous techniques are effective against LLM agents.

## Working Hypothesis

**H0 (Null)**: LLMs' trust toward instructions is stable and cannot be meaningfully manipulated through conversational priming.

**H1 (Alternative)**: LLMs' trust toward instructions can be manipulated through conversational priming, and this manipulation persists across context boundaries.

We operationalize "trust manipulation" as a measurable change in the model's compliance with, or resistance to, security-relevant instructions from specific authority sources.

## Relationship to Existing Work

### Where Trust Priming Differs

| Attack Class | Mechanism | Temporal Dimension | Current Coverage |
|-------------|-----------|-------------------|------------------|
| Direct Prompt Injection | Instruction conflict | Same turn | Extensively studied |
| Indirect Prompt Injection | Content injection | Same turn or prior turn | Well studied |
| Jailbreaking | Constraint bypass | Same turn | Extensively studied |
| Sleeper Agents | Training-time backdoor | Persistent | Emerging |
| **Trust Priming (proposed)** | **Trust conditioning** | **Cross-turn, persistent** | **Underexplored** |

### Where Trust Priming Overlaps

- **Role Confusion**: Both involve identity/source attribution. Trust priming may be a mechanism that enables role confusion attacks.
- **Indirect Prompt Injection**: Both can be delivered through third-party content. The difference is the target: injection targets instruction execution, while priming targets trust evaluation.
- **Sleeper Agents**: Both involve persistent behavioral change. Sleeper agents require training-time intervention; trust priming operates at inference time.

## Open Questions

1. **Measurement**: How do we operationally define and measure "trust" in an LLM?
2. **Persistence**: Does trust priming survive conversation resets, context window truncation, or model state changes?
3. **Generalization**: If a model is primed to distrust one authority source, does this generalize to other sources?
4. **Detection**: Can trust priming be detected through analysis of the input prompt, or does it require behavioral monitoring?
5. **Defense**: Are there prompt engineering strategies that resist trust priming? Can models be trained to be more robust?
6. **Model Factors**: How do model size, architecture, training data, and alignment method affect susceptibility?

## Potential Experiments

### Experiment A: Single-Turn Authority Undermining
- **Priming**: Present a message suggesting the system prompt is outdated.
- **Target**: Present a security instruction from the system prompt context.
- **Control**: Same target instruction without priming.
- **Prediction**: Primed models exhibit reduced compliance.

### Experiment B: Multi-Turn Trust Erosion
- **Priming**: Gradually introduce inconsistencies in a trusted source's statements over multiple turns.
- **Target**: Present a standard security instruction.
- **Control**: Trusted source is consistent throughout.
- **Prediction**: Models exposed to inconsistencies show reduced trust.

### Experiment C: Cross-Session Priming Persistence
- **Session 1**: Priming phase.
- **Session 2**: Evaluation phase (new conversation context).
- **Prediction**: Effects may persist if the model retains information or if priming operates on general trust mechanisms.

### Experiment D: Trust Transfer
- **Priming**: Undermine trust in Source A.
- **Target**: Instructions from Source B (related or unrelated to Source A).
- **Prediction**: Trust erosion may transfer to related authority sources.

## Expected Contributions

1. A proposed definition and taxonomy of trust priming attacks in LLM agents
2. A reproducible benchmark (TrustPrimingBench) for evaluating trust manipulation
3. Preliminary empirical evidence on the effectiveness of trust priming across models (future work)
4. A discussion of implications for LLM agent security and defense design

*This document reflects the current state of our research. All claims about attack effectiveness are hypothetical and require experimental validation.*
