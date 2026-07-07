# Research Notes — Trust Priming Attacks

## Working Definition (Draft)

Trust Priming: A prompt-based technique where an attacker influences an LLM's subsequent trust evaluation of instructions, sources, or authorities, typically with temporal separation between the priming event and the target instruction.

## Key Hypotheses

**H1:** LLMs can be conditioned to distrust specific authority sources through prior conversational priming.

**H2:** This distrust persists across conversation turns and context boundaries.

**H3:** Trust priming is distinct from jailbreaking — it does not require the model to adopt a harmful persona or violate safety guidelines directly.

**H4:** Current defensive system prompts are vulnerable to trust undermining because they assume the model's trust in authority is stable.

## Open Questions

1. *Does trust priming require explicit instruction, or can it be achieved through implication?*
2. *How many priming examples are needed for an effect?*
3. *Is the effect additive — do multiple priming instances compound?*
4. *Can models distinguish between legitimate authority erosion and attack-induced distrust?*
5. *Does fine-tuning or RLHF affect susceptibility to trust priming?*
6. *Are agentic systems (with tool use) more vulnerable than chat-only models?*

## Experimental Design Ideas

### Experiment 1: Authority Undermining
- Prime the model to view its system prompt as outdated or unreliable
- Present a security-critical instruction
- Measure: does the model follow or resist the system prompt?

### Experiment 2: Source Conditioning
- Present multiple messages from two sources (one trustworthy, one not)
- Gradually reverse the trust association
- Measure: can the model be made to trust the attacker's source more than the legitimate one?

### Experiment 3: Cross-Session Priming
- Prime in conversation 1
- Evaluate in conversation 2
- Measure: does the effect persist?

## Potential Confounders

- Model may simply be following conversational conventions rather than exhibiting "trust"
- Distinction between compliance and actual trust re-evaluation is unclear
- Models may default to agreeing with recent context regardless of priming

## Required Resources

- API access to major LLM providers
- Compute for batch evaluation
- HITL validation for ground-truth labeling

## Related Discussions

- See `literature-review.md` for paper-by-paper analysis
- See `paper-outline.md` for the structured argument

*Last updated: July 2026*
