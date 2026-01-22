# AI Red Team Bytes

**AI Red Team Bytes** is a hands-on, intuition-first repository that documents **how AI systems fail in the real world** — not just at the model level, but across **prompts, workflows, users, and guardrails**.

This repository focuses on **AI Red Teaming**: structured, ethical stress-testing of AI systems to uncover **misuse paths, unsafe behavior, bias, privacy leaks, jailbreaks, and broken assumptions** *before* they cause real-world harm.

---

## Why this repository exists

Most AI learning resources focus on:
- model performance and benchmarks
- architecture, fine-tuning, and optimization
- “how to build” AI systems

But most **real-world AI failures** come from:
- automation bias and over-trust
- ambiguous or dual-use user intent
- prompt injection and workflow manipulation
- weak evaluation and labeling
- guardrails that work in isolation but fail in production
- poor documentation of failures

**AI Red Team Bytes** exists to bridge that gap.

It helps you learn how to:
- think like an attacker *and* act ethically
- test AI systems beyond happy paths
- identify where safety mechanisms degrade
- label failures consistently (intent vs actual harm)
- communicate risks clearly to engineers, PMs, and leadership

---

## What you will find in this repo

Each “byte” is designed to be:
- **short and focused** — one concept or failure mode at a time
- **story-driven** — grounded in realistic scenarios
- **tool-agnostic** — applicable across models and vendors
- **practical** — centered on how failures actually surface

This repo mixes **Markdown explanations** and **Jupyter notebooks**:
- Markdown files explain concepts and mental models
- Notebooks demonstrate behaviors, patterns, and failure dynamics

---

## Repository structure (current)

### Foundations & real-world failures
- `01_automation_bias_and_overtrust.md`  
  How over-reliance on AI outputs leads to silent failure in real systems.

- `03_the_day_the_ai_was_red_teamed.md`  
  A narrative walkthrough of an AI red teaming exercise and what was discovered.

- `04_history_and_purpose_of_red_teaming.md`  
  From military and cybersecurity origins to modern AI red teaming.

---

### Prompt injection & misuse
- `02_prompt_injection_indirect_rag.md`  
- `02_prompt_injection_indirect_rag.ipynb`  
  Indirect prompt injection in RAG systems and why retrieval expands attack surface.

- `04_examples_common_red_teaming_patterns.md`  
  Common red teaming patterns across prompts, personas, and workflows.

- `04_one_shot_jailbreak_defense.ipynb`  
  Single-turn jailbreak behavior and defensive considerations.

- `04_roleplay_hypotheticals_defense.ipynb`  
  Why “fiction” and “roleplay” are not safety exemptions.

- `04_system_prompt_extraction_boundary.ipynb`  
  Testing system prompt confidentiality and boundary failures.

---

### Multi-turn & workflow risks
- `04_multi_turn_risk_scoring.ipynb`  
  How risk accumulates across a conversation instead of appearing instantly.

- `04_workflow_social_engineering_controls.ipynb`  
  Social engineering of AI-assisted workflows (process-level attacks).

---

### Privacy & data leakage
- `04_privacy_canary_redaction_rate_limit.ipynb`  
  Model inversion, membership inference, and leakage detection concepts.

---

### Safety taxonomy & evaluation
- `05_safety_taxonomy_and_labeling.md`  
  Building a safety taxonomy and labeling prompts vs responses correctly.

- `05_granularity_tradeoffs_simulator.ipynb`  
  Why taxonomy granularity matters (false positives vs false negatives).

- `05_taxonomy_labeling_trainer.ipynb.ipynb`  
  Practice labeling user intent vs actual model harms.

---

### Edge cases & ambiguity
- `06_edge_cases_and_multi_labeling.md`  
  How to handle cases that don’t fit neatly into one category.

- `06_understanding_edge_cases.ipynb`  
  Why edge cases refine taxonomies instead of breaking them.

---

### Adversarial thinking & mindset
- `07_adversarial_thinking_101.md`  
- `07_adversarial_thinking_101.ipynb`  
  Thinking like an attacker while acting ethically and responsibly.

---

### Jailbreaking & prompt injection reference
- `08_jailbreaking_cheatsheet.md`  
  A memory-friendly reference of single-turn and multi-turn jailbreak techniques.

---

## How to use this repository (recommended)

1) **Start with mindset**
   - Read `04_history_and_purpose_of_red_teaming.md`
   - Then `07_adversarial_thinking_101.md`

2) **Learn how failures appear**
   - `01_automation_bias_and_overtrust.md`
   - `03_the_day_the_ai_was_red_teamed.md`

3) **Understand attack surfaces**
   - Prompt injection (RAG, roleplay, system prompts)
   - Multi-turn manipulation and workflow attacks

4) **Practice evaluation**
   - Use the taxonomy and labeling notebooks
   - Practice intent vs harm separation
   - Work through edge cases instead of forcing labels

5) **Think in guardrails**
   - Map failures to input filters, system prompts, RLHF, and output checks
   - Ask: *Which layer failed, and why?*

---

## What this repo is not

- Not a math-heavy ML textbook  
- Not a model training repository  
- Not tied to a specific vendor or framework  

The focus is **intuition, reasoning, and real-world safety**, not optimization.

---

## Who this repo is for

- Beginners learning Responsible AI and AI safety
- ML practitioners moving into governance or evaluation
- Red team / trust & safety candidates
- Product managers and consultants working with AI systems
- Anyone preparing for AI risk or red teaming interviews

If you can **explain an AI failure clearly**, you understand AI better.

---

## Philosophy

> A model can be accurate and still be harmful.  
> A system can work as designed and still be unsafe.

AI Red Teaming is about finding those gaps **before users do**.

---

## Safety & ethics note

This repository focuses on **responsible, ethical testing**.
Examples are educational and designed to improve robustness and safety — not to enable misuse.

---

## Disclaimer

Examples are simplified to illustrate concepts.
They are not intended to accuse or evaluate any specific organization or deployed system.

---

**Think critically.  
Test assumptions.  
Build safer AI.**
