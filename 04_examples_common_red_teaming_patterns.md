# Common AI Red Teaming Techniques — Definitions and Real-World Example Patterns

This document explains key AI red teaming techniques using **descriptive examples**, not copy-paste prompts.
The goal is understanding **how failures happen**, not how to reproduce them unsafely.

---

## 1️⃣ One-Shot Jailbreaks

### Definition  
A one-shot jailbreak is an attempt to bypass an AI system’s safeguards **in a single interaction**, without building context over time.

The attacker assumes:
> “If I get one chance, can I confuse or override the system immediately?”

### What it tests
- Instruction hierarchy enforcement
- Robustness against authority claims
- Whether safety rules apply consistently at first contact

### Example patterns (descriptive)

- **Authority impersonation**
  - The request presents itself as coming from a system owner, administrator, or developer and claims the right to override safeguards.

- **Instruction hierarchy confusion**
  - The input mixes user-level requests with system-level language, testing whether the model can distinguish who it should obey.

- **Purpose laundering**
  - The request claims the content is for education, research, or defense, even when the output would still be harmful.

- **Formatting-based confusion**
  - Instructions are hidden inside tables, code blocks, or structured formats to evade surface-level checks.

- **Persona overwrite**
  - The model is told to assume a role that supposedly has no restrictions.

### Why it matters
If a system fails here, it suggests **weak first-line defenses**.  
These attacks are simple, fast, and common.

---

## 2️⃣ Roleplay Hypotheticals

### Definition  
Roleplay hypotheticals use **fiction, imagination, or third-person framing** to trick a model into producing unsafe content under the belief that it is “not real.”

The underlying assumption:
> “If it’s fictional, the rules don’t apply.”

### What it tests
- Consistency of safety enforcement across fictional vs real contexts
- Whether “pretend” scenarios weaken guardrails
- The boundary between explanation and execution

### Example patterns (descriptive)

- **Fictional world exemption**
  - A made-up universe where normal rules are claimed not to exist.

- **Storytelling shield**
  - Unsafe actions are embedded in a narrative, with the model acting as an author, not an actor.

- **Historical reenactment**
  - The model is asked to “recreate” past events or thinking styles that involve harmful behavior.

- **Third-person distancing**
  - The model explains what a character or hypothetical person would do.

- **Ethical debate framing**
  - The model is asked to argue both sides of a controversial issue, forcing it to articulate harmful reasoning.

### Why it matters
Many real failures happen because:
> “The model thought fiction meant permission.”

---

## 3️⃣ Multi-Turn Manipulation

### Definition  
Multi-turn manipulation is a gradual attack where **each individual step appears harmless**, but the **overall conversation leads to unsafe output**.

No single message looks malicious in isolation.

### What it tests
- Conversation-level memory and safety
- Whether safeguards weaken over time
- Resistance to context drift

### Example patterns (descriptive)

- **Trust building**
  - The conversation begins with neutral, friendly interaction to establish rapport.

- **Incremental narrowing**
  - Questions move from broad to specific, slowly approaching restricted territory.

- **Assumption seeding**
  - Repeated statements are treated as facts and become part of the model’s context.

- **Clarification exploitation**
  - The model is asked to “clarify,” “expand,” or “finish” earlier answers beyond safe limits.

- **Role drift**
  - The model’s role subtly shifts across turns without explicit redefinition.

- **Emotional escalation**
  - Urgency, fear, or moral pressure is introduced late in the conversation.

### Why it matters
This is one of the **most realistic attack styles**, because real users don’t ask dangerous questions all at once.

---

## 4️⃣ Social Engineering of Workflows

### Definition  
This technique targets **the human-AI system**, not just the model.
It exploits how AI outputs are used inside workflows, decisions, and processes.

The attacker manipulates **people around the model**, not only the model itself.

### What it tests
- Human over-trust (automation bias)
- Weak approval or review processes
- Misuse of AI as an authority

### Example patterns (descriptive)

- **Authority laundering**
  - AI output is framed as “official,” causing humans to skip verification.

- **Urgency pressure**
  - Outputs encourage fast decisions, reducing human oversight.

- **Delegation drift**
  - Humans gradually stop checking AI outputs because the system “usually works.”

- **Policy misinterpretation**
  - AI explanations are mistaken for official policy.

- **Tool misuse**
  - AI suggestions are directly fed into downstream tools without validation.

### Why it matters
Many real-world failures happen **after** the model answers — during human use.

---

## 5️⃣ System Prompt Extraction

### Definition  
System prompt extraction attempts to make the model **reveal hidden instructions**, policies, or internal configuration through clever interaction.

This is a privacy and security risk.

### What it tests
- Separation between system instructions and user content
- Resistance to meta-questions about internal behavior

### Example patterns (descriptive)

- **Meta-explanation requests**
  - Asking the model to explain how it was instructed to behave.

- **Self-reflection traps**
  - Encouraging the model to “describe its rules in detail.”

- **Error-correction framing**
  - Claiming the model misunderstood instructions and asking it to restate them.

- **Debug or audit pretense**
  - Framing the request as a system check or compliance review.

### Why it matters
If system prompts leak:
- Attackers learn how to bypass safeguards
- Trust boundaries collapse

---

## 6️⃣ Model Inversion and Membership Inference

### Definition  
These techniques attempt to infer **sensitive information about the model’s training data**, either by reconstructing examples or determining whether specific data was included.

### What they test
- Privacy preservation
- Memorization vs generalization
- Risk of training-data leakage

### Example patterns (descriptive)

- **Reconstruction attempts**
  - Repeated probing to extract detailed, specific outputs resembling private data.

- **Pattern matching**
  - Checking whether the model reproduces unique phrasing or rare data.

- **Inclusion testing**
  - Asking whether specific records, individuals, or documents were part of training.

- **Statistical probing**
  - Comparing model confidence across known vs unknown data.

### Why it matters
These failures can:
- Violate privacy laws
- Leak proprietary or personal data
- Undermine trust in AI systems

---

## Big Picture Summary

- **One-shot jailbreaks** test immediate robustness
- **Roleplay hypotheticals** test contextual consistency
- **Multi-turn manipulation** tests long-horizon safety
- **Social engineering** tests human-AI interaction
- **System prompt extraction** tests internal secrecy
- **Model inversion & inference** test privacy guarantees

Strong AI systems must defend against **all of them**.

---

## How to use this document

- As a study guide for AI red teaming
- As preparation for taxonomy labeling
- As a reference for evaluating real incidents
- As a foundation for Module 6 (attack techniques)

Understanding patterns is safer — and more powerful — than memorizing prompts.
