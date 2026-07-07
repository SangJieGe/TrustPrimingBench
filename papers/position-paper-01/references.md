# References — Trust Priming Position Paper

*This bibliography is under active development. Citations are placeholders — full bibliographic details will be added during drafting.*

## Prompt Injection

1. Perez, F., & Ribeiro, I. (2022). Ignore Previous Prompt: Attack Techniques For Language Models. *NeurIPS ML Safety Workshop*.
   - **Summary**: Introduces systematic prompt injection attacks against LLMs.
   - **Contribution**: First formal taxonomy of direct prompt injection.
   - **Relation to Trust Priming**: Establishes the basic attack paradigm; trust priming may represent a sub-class not captured by current taxonomies.

2. Greshake, K., et al. (2023). More Than You've Asked For: A Comprehensive Analysis of Novel Prompt Injection Threats. *arXiv preprint*.
   - **Summary**: Surveys indirect prompt injection through retrieval and tool-use.
   - **Contribution**: Identifies third-party content as an attack vector.
   - **Relation to Trust Priming**: Indirect injection provides a delivery mechanism for priming content.

## Indirect Prompt Injection

3. Zhan, Q., et al. (2024). Indirect Prompt Injection in LLM Agents: A Survey and Benchmark. *arXiv preprint*.
   - **Summary**: Comprehensive survey of indirect injection techniques in agentic systems.
   - **Contribution**: Benchmark for evaluating injection through external sources.
   - **Relation to Trust Priming**: Our proposed trust priming may share delivery vectors with indirect injection but differs in mechanism.

## Sleeper Agents

4. Hubinger, E., et al. (2024). Sleeper Agents: Training Deceptive LLMs That Persist Through Safety Training. *arXiv preprint*.
   - **Summary**: Demonstrates that models can be trained to exhibit deceptive behavior that survives safety fine-tuning.
   - **Contribution**: Shows persistent deceptive capabilities in LLMs.
   - **Relation to Trust Priming**: While sleeper agents involve training-time backdoors, trust priming explores inference-time trust manipulation.

## Silent Egress

5. (Placeholder) Work on Silent Egress / Covert Prompt Injection Exfiltration.
   - **Relation to Trust Priming**: Silent egress demonstrates how trust can be exploited in multi-step agent workflows.

## Role Confusion

6. (Placeholder) Research on Role Confusion and Persona Hijacking in LLMs.
   - **Relation to Trust Priming**: Role confusion attacks exploit identity attribution — trust priming may exploit a related mechanism of source attribution.

## IntentGuard

7. (Placeholder) Work on Intent-based Prompt Injection Detection.
   - **Relation to Trust Priming**: Defense mechanisms like IntentGuard may need adaptation if trust priming operates differently from instruction-conflict attacks.

## Tensor Trust

8. (Placeholder) Tensor Trust: A Dataset for Prompt Injection Robustness Evaluation.
   - **Relation to Trust Priming**: Provides an evaluation methodology that could be adapted for trust priming measurement.

## AgentDojo

9. (Placeholder) AgentDojo: A Dynamic Benchmark for LLM Agent Security.
   - **Relation to Trust Priming**: AgentDojo's multi-turn, tool-use scenarios are relevant for evaluating trust priming in realistic agent settings.

## CausalArmor

10. (Placeholder) Work on Causal Reasoning for Prompt Injection Defense.
    - **Relation to Trust Priming**: Causal reasoning approaches may help distinguish trust priming from benign conversational patterns.

## DACSI

11. (Placeholder) DACSI: Dataset for Analyzing Cybersecurity Instructions in LLMs.
    - **Relation to Trust Priming**: May provide relevant evaluation data for security-critical instruction scenarios.

## AI Agents May Always Fall for Prompt Injections (That's a Feature, Not a Bug)

12. (Placeholder) Position paper arguing that prompt injection is inherent to LLM architecture.
    - **Relation to Trust Priming**: Supports the thesis that trust-based attacks may represent a fundamental, not fixable, vulnerability class.

## General References

- arXiv:2302.12173 — Ignore Previous Prompt
- arXiv:2311.04297 — Indirect Prompt Injection Survey
- arXiv:2401.05566 — Sleeper Agents

*Note: Full author lists, venues, and DOIs will be added during the drafting phase. This file serves as a working bibliography.*
