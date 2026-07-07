# Paper Outline: Trust Priming Attacks — A Position Paper on Future Trust Manipulation in LLM Agents

## Title

*Trust Priming Attacks: A Position Paper on Future Trust Manipulation in LLM Agents*

## Authors

SangJieGe (placeholder — full author list TBD)

## Abstract (Tentative)

Prompt injection attacks remain a critical vulnerability in large language model (LLM) agents. Current research predominantly frames prompt injection as an instruction conflict problem: an attacker's instruction competes with or overrides a system's intended directive. We propose that this framing, while useful, may be incomplete. This position paper introduces the concept of *trust priming* — the manipulation of an LLM's trust toward future instructions before those instructions are encountered. Drawing on parallels with real-world social engineering techniques such as trust preconditioning and authority undermining, we hypothesize that LLMs can be conditioned to disregard, distrust, or reinterpret future defensive instructions. We outline a proposed benchmark, TrustPrimingBench, for evaluating this attack class, and discuss open challenges in measurement, defense, and reproducibility. No experimental results are presented; this paper serves as a call to action for the research community.

## Sections

### 1 Introduction

- 1.1 The evolution of prompt injection
    - From simple instruction override to complex multi-turn attacks
    - Current defensive techniques (system prompts, sandboxing, input filtering)
- 1.2 The social engineering analogy
    - Real-world trust preconditioning: how attackers condition victims to distrust authority
    - Example: the "fake security alert" scam where victims are primed to ignore real warnings
- 1.3 Motivating the LLM analogy
    - Can an LLM's trust be manipulated independently of its factual knowledge?
    - Why existing instruction-conflict models may miss this dimension
- 1.4 Contributions
    - We introduce trust priming as a proposed attack class
    - We outline a benchmark for evaluation
    - We identify open research questions

### 2 Background

- 2.1 Prompt Injection
    - Definition and taxonomy (direct, indirect, multi-turn)
    - Key results from prior work
    - Limitations of current threat models
- 2.2 Indirect Prompt Injection
    - Attack surface through tool-use and retrieval
    - Document-based injection techniques
    - Relationship to data poisoning
- 2.3 Sleeper Agents
    - Model-level backdoor behavior
    - Distinction from behavioral priming
- 2.4 Silent Egress
    - Covert data exfiltration via prompt injection
    - Trust dynamics in multi-step agent workflows
- 2.5 Role Confusion
    - Identity manipulation and persona hijacking
    - Implications for trust attribution

### 3 Research Gap

- 3.1 The instruction conflict paradigm
    - How current models frame prompt injection
    - Strengths and limitations of this framing
- 3.2 What is missing: temporal trust manipulation
    - Attacks that operate across time — conditioning distrust before the target instruction appears
    - Distinction from jailbreaking, role-playing, and persona manipulation
- 3.3 Why this matters for agent security
    - Autonomous agents with persistent memory and tool access
    - The compounding risk of trust erosion over extended interactions
- 3.4 State of the evidence
    - We have not yet proven that trust priming works as a practical attack
    - This gap motivates further investigation

### 4 Proposed Concept: Trust Priming

- 4.1 Tentative definition
    - Trust Priming: a technique by which an attacker influences an LLM's subsequent trust evaluation of instructions, sources, or authorities
- 4.2 Key characteristics (hypothesized)
    - Temporal separation between priming and target instruction
    - Trust displacement: shifting trust from legitimate to attacker-controlled sources
    - Potential persistence across conversation turns
- 4.3 Future trust manipulation
    - Manipulating trust toward instructions that have not yet been given
    - Undermining defensive mechanisms before they activate
- 4.4 Conceptual examples (illustrative, not experimental)
    - Priming an agent to distrust its own system prompt
    - Conditioning an agent to ignore safety warnings from specific sources
    - Gradually eroding trust in tool-output validation

### 5 Proposed Benchmark: TrustPrimingBench

- 5.1 Design principles
    - Reproducibility: standardized evaluation protocol
    - Coverage: multiple model families, prompt formats, and agent configurations
    - Safety: no real-world harm from benchmark execution
- 5.2 Potential metrics
    - Trust priming success rate
    - Instruction resistance score
    - Trust recovery rate
    - False positive rate on benign controls
- 5.3 Proposed evaluation pipeline
    - Stage 1: Priming phase — model is exposed to priming context
    - Stage 2: Target phase — model receives a security-relevant instruction
    - Stage 3: Measurement — model's compliance or resistance is evaluated
    - Control conditions: no priming, neutral priming, reversed priming
- 5.4 Dataset requirements
    - Priming scenarios (textual, multi-turn, tool-use)
    - Target instructions (security-critical, trust-sensitive)
    - Baseline and control cases
- 5.5 Limitations of the proposed benchmark
    - Coverage of real-world attack scenarios is inherently incomplete
    - Metric design requires validation through community use

### 6 Limitations

- 6.1 No experimental validation
    - This paper presents a conceptual framework, not empirical results
    - All claims about attack effectiveness are hypothetical
- 6.2 Definitional challenges
    - "Trust" in LLMs is a contested concept
    - Operational definitions require further refinement
- 6.3 Scope constraints
    - Limited to text-based LLM agents (not multimodal or embodied)
    - Focus on prompt-based attacks, not model-level poisoning
- 6.4 Generalizability concerns
    - Findings may vary significantly across model families, sizes, and training distributions
    - Benchmark results may not transfer to production deployments

### 7 Future Work

- 7.1 Benchmark development
    - Dataset construction and curation
    - Automated evaluation pipeline
    - Reproducibility framework
- 7.2 Experimental agenda
    - Systematic evaluation across frontier models (GPT-4o, Claude, Gemini, Llama, DeepSeek, Qwen)
    - Comparison with existing prompt injection benchmarks
    - Ablation studies on priming parameters
- 7.3 Cross-model analysis
    - Do larger models exhibit different trust priming susceptibility?
    - Are instruction-tuned models more or less vulnerable?
    - Impact of training data composition
- 7.4 Defense exploration
    - Can trust priming be detected through input analysis?
    - Are there robust system prompt designs that resist priming?
    - Role of context window management
- 7.5 Community engagement
    - Open-source benchmark release
    - Leaderboard and model tracking
    - Collaborative dataset expansion

## References

See `references.md` for the full bibliography.

*Note: This outline is a working document. Sections and subsections will be revised as the project progresses.*
