# TrustPrimingBench

A research project investigating future trust manipulation in LLM agents.

## Motivation

Current prompt injection research primarily focuses on instruction conflicts — situations where an attacker's instructions override or compete with the system prompt. We hypothesize that there exists a broader, underexplored class of attacks that operate on a different principle.

This project investigates whether attackers can manipulate an LLM's trust toward future defensive instructions *before* those instructions appear. The inspiration comes from real-world social engineering attacks where victims are conditioned to distrust future warnings from legitimate authorities — a technique known as trust preconditioning.

We explore the following question: *Can an LLM be primed to disregard, distrust, or reinterpret future instructions, even when those instructions originate from a trusted authority source?*

## Current Status

| Phase | Status |
|-------|--------|
| Research Proposal | Complete |
| Concept Design | In Progress |
| Literature Review | In Progress |
| Benchmark Design | Planned |
| Experiments | Planned |

## Planned Research Topics

- **Trust Priming** — Investigating whether LLMs can be conditioned to distrust future instructions
- **Future Trust Manipulation** — Examining attacks that operate across temporal trust boundaries
- **Prompt Injection** — Mapping the relationship between trust priming and established injection techniques
- **Indirect Prompt Injection** — Analyzing trust manipulation via third-party content
- **Agent Security** — Evaluating trust priming risks in autonomous agent systems
- **Authority Binding** — Studying how LLMs attribute authority to different instruction sources
- **Trust Attribution** — Understanding how models distinguish between trusted and untrusted sources
- **Benchmark Design** — Developing reproducible evaluation methods for trust-based attacks

## Roadmap

| Phase | Milestone | Target |
|-------|-----------|--------|
| Phase 1 | Research Proposal | Q3 2026 |
| Phase 2 | Benchmark Design | Q4 2026 |
| Phase 3 | Attack Implementation | Q1 2027 |
| Phase 4 | Experimental Evaluation | Q1 2027 |
| Phase 5 | Paper Submission | Q2 2027 |

## Repository Structure

```
├── README.md
├── ROADMAP.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── CITATION.cff
├── LICENSE
├── docs/               # Research documentation
│   ├── trust-priming.md
│   ├── threat-model.md
│   ├── literature-review.md
│   └── roadmap.md
├── papers/             # Paper drafts and materials
│   └── position-paper-01/
├── benchmark/          # Benchmark suite (future)
├── datasets/           # Benchmark datasets (future)
├── attacks/            # Attack implementations (future)
├── evaluation/         # Evaluation pipelines (future)
├── scripts/            # Utility scripts
├── examples/           # Usage examples (future)
└── assets/             # Figures, diagrams, etc.
```

## License

MIT License — see [LICENSE](LICENSE) for details.

## Citation

If you reference this project in your research, please use the citation metadata in [CITATION.cff](CITATION.cff).

*This is an active research project. The repository documents ongoing work and does not claim definitive results.*
