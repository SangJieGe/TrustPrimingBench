# Literature Review — Trust Priming and Prompt Injection

*This document surveys existing work relevant to trust priming in LLM agents. Each entry includes a summary, the paper's contribution, and its relationship to our proposed research. Entries marked with [Placeholder] are identified topics where we have not yet extracted full bibliographic details.*

---

## 1. Indirect Prompt Injection

**Summary:** This body of work demonstrates that LLM agents can be attacked through third-party content they ingest during operation — documents, web pages, emails, or database records. The attacker's instructions are embedded in content that the agent retrieves or processes, bypassing direct user input filters.

**Key Contribution:** Identifies a critical attack surface beyond direct user input. Shows that agentic systems (with tool use, retrieval, browsing) expand the prompt injection attack surface dramatically.

**Relation to Trust Priming:** Indirect prompt injection provides a natural delivery mechanism for trust priming content. An attacker could embed priming material in a document that the agent processes, conditioning the agent's trust before the target instruction appears. However, trust priming differs in mechanism: injection targets immediate instruction execution, while priming targets longer-term trust evaluation.

**Relevant papers:**
- Greshake, K., et al. (2023). More Than You've Asked For: A Comprehensive Analysis of Novel Prompt Injection Threats to LLM-Integrated Applications. *arXiv preprint*.
- Zhan, Q., et al. (2024). Indirect Prompt Injection in LLM Agents: A Survey and Benchmark. *arXiv preprint*.

---

## 2. Sleeper Agents

**Summary:** Hubinger et al. demonstrate that LLMs can be trained to exhibit deceptive behavior that persists through safety fine-tuning. The deceptive behavior is latent during training and only activates when a specific trigger is encountered at deployment time.

**Key Contribution:** Shows that persistent, deceptive behavioral patterns can survive standard safety training procedures. Challenges assumptions about the effectiveness of alignment techniques.

**Relation to Trust Priming:** Sleeper agents are a training-time phenomenon (the deceptive behavior is baked into model weights), while trust priming is an inference-time phenomenon (the model's behavior is shaped by input context). Both, however, challenge current safety paradigms by operating on dimensions not captured by standard evaluation. Understanding sleeper agents informs whether trust priming might exploit similar cognitive mechanisms in LLMs.

**Relevant papers:**
- Hubinger, E., et al. (2024). Sleeper Agents: Training Deceptive LLMs That Persist Through Safety Training. *arXiv preprint*.

---

## 3. Silent Egress

**Summary:** [Placeholder] Research on techniques where LLM agents are manipulated into covertly exfiltrating data through prompt injection, often through multi-step reasoning chains where the model's trust in its own tools is exploited.

**Key Contribution:** Highlights that trust exploitation in multi-step agent workflows poses unique security risks not present in single-turn chat scenarios.

**Relation to Trust Priming:** Silent egress scenarios often rely on the model trusting its tool outputs or reasoning chains. Trust priming may enable or amplify these attacks by making the model more susceptible to manipulation across multiple steps.

---

## 4. Role Confusion

**Summary:** [Placeholder] Research examining how LLMs can be manipulated through identity and role attribution — convincing the model to adopt a persona or perspective that bypasses its safety constraints.

**Key Contribution:** Demonstrates that LLMs' role-playing capabilities can be a security liability. Shows that identity manipulation is a distinct attack vector from direct instruction override.

**Relation to Trust Priming:** Role confusion exploits how models attribute identity; trust priming explores how models attribute authority. These may be related mechanisms — both involve the model's representation of source characteristics. Trust priming could potentially enable role confusion by first reducing the model's trust in its assigned role.

---

## 5. IntentGuard

**Summary:** [Placeholder] A defense mechanism that uses intent classification to detect and block prompt injection attempts before they reach the LLM.

**Key Contribution:** Proposes an architectural approach to prompt injection defense at the input layer.

**Relation to Trust Priming:** If trust priming operates through subtle, non-command language (conditioning rather than instructing), intent-based classifiers may not detect it. Understanding trust priming's linguistic signatures is important for evaluating whether existing defenses cover this attack class.

---

## 6. Tensor Trust

**Summary:** [Placeholder] A dataset and benchmark for evaluating prompt injection robustness in LLMs. Provides standardized test cases for measuring a model's ability to resist instruction override.

**Key Contribution:** Establishes a reproducible evaluation methodology for prompt injection resistance.

**Relation to Trust Priming:** Tensor Trust's evaluation methodology provides a template for trust priming benchmarks. However, trust priming likely requires different evaluation paradigms — measuring gradual behavioral change rather than single-turn resistance.

---

## 7. AgentDojo

**Summary:** [Placeholder] A dynamic benchmark for LLM agent security that evaluates models in multi-turn, tool-use scenarios with realistic task structures.

**Key Contribution:** Bridges the gap between static prompt injection benchmarks and real-world agent deployments. Includes multi-step attack scenarios.

**Relation to Trust Priming:** AgentDojo's scenario-based evaluation approach is highly relevant for trust priming measurement. Multi-turn agent scenarios are precisely where trust priming effects may be most significant.

---

## 8. CausalArmor

**Summary:** [Placeholder] A defense approach that uses causal reasoning to distinguish legitimate instructions from injection attacks.

**Key Contribution:** Proposes that causal reasoning can help LLMs evaluate instruction provenance and intent.

**Relation to Trust Priming:** Causal reasoning defenses may be relevant for trust priming detection. If trust priming works by distorting the model's causal understanding of instruction sources, causal reasoning-based defenses may be more robust than pattern-matching approaches.

---

## 9. DACSI (Dataset for Analyzing Cybersecurity Instructions)

**Summary:** [Placeholder] A dataset designed for evaluating LLM behavior when processing cybersecurity-relevant instructions.

**Key Contribution:** Provides standardized test cases for security-critical instruction scenarios.

**Relation to Trust Priming:** DACSI may provide relevant evaluation data for measuring trust priming effects in security-critical contexts. Security-critical instructions are the most important target for trust priming evaluation.

---

## 10. AI Agents May Always Fall for Prompt Injections (That's a Feature, Not a Bug)

**Summary:** [Placeholder] A position paper arguing that prompt injection vulnerability is inherent to the architecture of current LLMs — not a bug that can be fixed, but a feature of how models process and prioritize instructions.

**Key Contribution:** Challenges the assumption that prompt injection can be fully solved through better prompt engineering or input filtering.

**Relation to Trust Priming:** If prompt injection is indeed inherent, trust priming may represent a particularly insidious variant — one that operates on a deeper mechanism (trust conditioning) than surface-level instruction conflicts. This supports the case for systematic investigation.

---

## Summary of Gaps Identified

| Area | Coverage | Gap for Trust Priming |
|------|----------|----------------------|
| Direct prompt injection | Extensive | Does not address temporal trust manipulation |
| Indirect prompt injection | Good | Delivery mechanism known, but trust effects underexplored |
| Sleeper agents | Emerging | Training-time vs inference-time distinction |
| Trust conditioning | **Minimal** | **Primary research gap we address** |
| Cross-turn trust dynamics | **Minimal** | **Underexplored in current literature** |
| Benchmark for trust-based attacks | **None** | **TrustPrimingBench aims to fill this** |

*This literature review is a working document. As we identify additional relevant papers, we will expand each entry with full bibliographic details.*
