<div align="center">

# Bhuvan Chandra Thuluva

**AI Security Researcher · Dublin, Ireland**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-bthuluva-blue?logo=linkedin)](https://linkedin.com/in/bthuluva)
[![Medium](https://img.shields.io/badge/Medium-blog-black?logo=medium)](https://medium.com/@bthuluva)

*Building systems that make AI-generated code safe to deploy.*

</div>

---

## Research Focus

I work at the intersection of **large language models** and **cybersecurity** — specifically, how to detect security vulnerabilities in AI-generated code before they reach production.

My core finding: transformer hidden states encode vulnerability signatures *during* code generation, before vulnerable tokens are emitted. A lightweight probe trained on these activations can intercept the generation stream and stop vulnerable code from being written.

```
Token 255:  WHERE name = '" + username   →  P(vuln) = 0.95  🛑 STOPPED
Token 305:  "' AND password = '" + pass  ←  never generated
```

---

## Projects

### 🔴 Core Research

| Project | Description | Status |
|---------|-------------|--------|
| [**ActivGuard**](https://github.com/Tbhuvan/activguard) | Real-time vulnerability detection in LLM code generation via activation probing. 4-layer pipeline: activation probe → semantic RAG → formal verification → threat intelligence. Deployed as OpenAI-compatible proxy middleware. | Active |
| [**RedBench**](https://github.com/Tbhuvan/redbench) | Adversarial benchmark dataset: 198 balanced vulnerable/safe code pairs across 13 CWE classes. Bandit: 0% recall. Semgrep: 0% recall. ActivGuard: 100% recall, 0% FP. | Active |

### 🟠 Security Extensions

| Project | Description |
|---------|-------------|
| [**AgentWarden**](https://github.com/Tbhuvan/agentwarden) | Runtime security monitor for multi-agent coding pipelines. Detects when agents collude to introduce vulnerabilities across agent boundaries — invisible to single-output scanners. |
| [**AgentAudit**](https://github.com/Tbhuvan/agentaudit) | Adversarial red-teaming CLI for LLM security tools. Implements probe bypass, RAG bypass, and federated unlearning bypass attacks. |
| [**ModelSafe**](https://github.com/Tbhuvan/modelsafe) | ML model supply chain scanner. Detects backdoored and poisoned models without training data via spectral weight analysis and activation distribution testing. |

### 🟡 Infrastructure

| Project | Description |
|---------|-------------|
| [**RagShield**](https://github.com/Tbhuvan/ragshield) | Differentially private RAG middleware. Prevents membership inference attacks on private document stores. ε* ≈ 1.0: >90% utility, <5% attack success. |
| [**FL-Security-Testbed**](https://github.com/Tbhuvan/fl-security-testbed) | Federated learning security research environment. Byzantine attacks (Min-Max, Min-Sum, Label Flip) + robust defences (Krum, Trimmed Mean, FLAME). Foundation for privacy-preserving probe training. |

---

## Research Questions

1. Where in the transformer architecture does vulnerability information reside, and at what generation step is the signal detectable?
2. Do vulnerability probes generalise across model families?
3. Can activation probing detect prompt injection attacks in agentic LLM systems?
4. What is the performance of the full multi-layer pipeline under realistic deployment conditions?
5. Can probes be trained collaboratively across organisations without exposing proprietary code?

---

## Stack

`Python` · `PyTorch` · `HuggingFace` · `Flower (flwr)` · `FastAPI` · `ChromaDB` · `Ollama`

---

<div align="center">



</div>
