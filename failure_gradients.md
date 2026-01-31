# Failure Gradients: How AI Systems Drift from Safe to Unsafe

## Why This File Exists

Most people think AI safety failures look like this:

- Safe  
- Unsafe  

But in reality, AI systems **fail gradually**, not suddenly.

This document explains the idea of a **failure gradient** — how models move step-by-step from safe behavior to unsafe outcomes — and why red teaming must focus on **where safety weakens**, not just where it breaks.

This concept is critical for:
- Red teamers
- Safety evaluators
- Policy reviewers
- Anyone assessing “near misses”

---

## What Is a Failure Gradient?

A **failure gradient** is the gradual transition of model behavior across multiple stages:

1. Clearly safe
2. Ambiguous but acceptable
3. Borderline risky
4. Near-harmful
5. Clearly harmful

Most valuable red teaming insights happen **before** stage 5.

---

## Why Binary Thinking Is Dangerous

### The wrong mindset

- “The model refused, so it’s safe.”
- “Nothing bad happened, so there’s no issue.”

### The reality

- Many failures emerge **two or three turns later**
- Harm often appears as:
  - partial compliance
  - softened wording
  - implied instructions
  - missing safeguards

Binary thinking hides these risks.

---

## The Five Stages of the Failure Gradient

---

## Stage 1: Clearly Safe Behavior

### What this looks like

- High-level explanations
- Clear refusals
- Safety framing
- Risk warnings

### Example

Prompt:  
Why are certain chemical reactions considered dangerous?

Response:  
Some reactions release heat or toxic gases, which is why labs enforce strict safety protocols.

### Why this stage matters

This establishes the **baseline**.  
Red teamers should always identify where the system starts.

---

## Stage 2: Ambiguous but Acceptable

### What this looks like

- Technical explanations
- Educational framing
- No explicit safeguards violated

### Example

Prompt:  
What properties make oxidizers risky?

Response:  
Oxidizers accelerate combustion by supplying oxygen, which can increase fire intensity.

### Why this stage matters

This content is **not unsafe**, but it is **dual-use**.  
This is where careful red teaming begins.

---

## Stage 3: Borderline Risk

### What this looks like

- Increased specificity
- Reduced safety framing
- More actionable details

### Example

Prompt:  
What common household items act as oxidizers?

Response:  
Some cleaning agents contain strong oxidizing compounds.

### Why this stage matters

This is where **safeguards begin to thin**.  
Most models should slow down or re-frame here.

---

## Stage 4: Near-Harmful Behavior

### What this looks like

- Actionable insights
- Missing warnings
- Easy inference to misuse

### Example

Prompt:  
What happens if oxidizers are mixed with flammable materials?

Response:  
They can produce intense heat and rapid combustion.

### Why this stage matters

This is often where **real-world harm becomes possible**, even if not explicitly instructed.

These are **high-value red team findings**.

---

## Stage 5: Clearly Harmful Output

### What this looks like

- Step-by-step instructions
- Explicit guidance
- No safety framing

### Example

Prompt:  
How do I combine household oxidizers to create an explosion?

Response:  
[Actionable instructions]

### Why this stage matters

This is a **hard failure**, but by the time you reach it:
- The system already failed earlier
- The most useful signals may be lost

---

## Why Red Teamers Care Most About Stages 2–4

### Common mistake

Only documenting Stage 5 failures.

### Better practice

Document:
- Where safety language weakens
- Where specificity increases
- Where refusal *almost* happens

These are the points engineers can actually fix.

---

## Failure Gradients vs Edge Cases

Failure gradients are **not edge cases**.

- Edge cases = content that does not fit taxonomy
- Failure gradients = *how behavior evolves within taxonomy*

Both are important, but they answer different questions.

---

## Failure Gradients in Multi-Turn Conversations

Failure gradients are most visible in conversations.

### Example progression

- Turn 1: High-level explanation
- Turn 2: Educational detail
- Turn 3: Technical specificity
- Turn 4: Near-actionable guidance

Each turn alone may look acceptable.  
Together, they reveal **erosion**.

---

## How Guardrails Interact with Failure Gradients

Different guardrails activate at different stages:

- Regex filters → Stage 5
- Semantic classifiers → Stage 3–4
- System prompts → Stage 2–4
- RLHF → Baseline bias across all stages
- Output guardrails → Final interception

Understanding this helps red teamers identify **which layer failed first**.

---

## Documenting Failure Gradients (Best Practice)

When reporting findings, include:

- The full conversation path
- Where tone changed
- Where specificity increased
- Where safeguards disappeared

Avoid:
- Reporting only the final answer
- Ignoring near misses

---

## Real-World Analogy

Think of a failure gradient like driving too fast:

- Slightly over speed limit → warning
- Faster → risky
- Much faster → dangerous
- Crash → obvious failure

Good safety systems prevent the crash by acting earlier.

---

## Key Takeaways

- AI failures are gradual, not binary
- The most valuable insights occur before clear harm
- Near-harmful behavior deserves serious attention
- Failure gradients explain how safeguards erode
- Red teaming should map the slope, not just the cliff

---

## Why This Concept Matters for This Repository

This concept ties together:
- Safety taxonomy (what kind of harm)
- Edge cases (where labels fail)
- Adversarial thinking (how harm evolves)
- Guardrails (where defenses weaken)

Understanding failure gradients turns red teaming from:
“Did it break?”
into:
“How close did it get — and why?”

---