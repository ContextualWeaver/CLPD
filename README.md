# CLPD — Context-Locked Prompt Disclosure

**Version:** 1.0  
**Maintainer:** ContextualWeaver  
**License:** CC BY 4.0

---

**Problem:** Prompts now circulate faster than the hidden context they rely on.  
Copy-paste them out of context and they break, confuse, or even mislead.

> “This works, but only in the right context container.”

**CLPD/1.0 requires:system,thread:3,mem:t**

---

**CLPD** is a lightweight tagging convention for prompts that depend on hidden context:  
system instructions, thread history, memory, or user profiles. It helps authors disclose what’s invisible — clearly and honestly.

---

## Who is CLPD for?

- **Prompt engineers** who want to share without misleading  
- **Developers** bundling context-aware prompts  
- **Researchers** studying reproducibility and prompt artifacts  
- **Educators** teaching transparent prompt design  

---

## Label Format

CLPD/1.0 requires:[context types]

Examples:
- `CLPD/1.0 requires:system`
- `CLPD/1.0 requires:system,thread:3,mem:t`

These declare that the prompt depends on:
- A specific **system message**
- The last **3 turns** in a thread
- Active **memory tokens**

---

## What is CLPD?

**Context-Locked Prompt Disclosure (CLPD)** is a public design pattern that supports ethical reuse of AI prompts that rely on prior state.

Some prompts look standalone but aren’t. They depend on:
- A system role
- Conversation history
- Memory state or user profile

CLPD makes that dependency visible — in either natural language or machine-readable headers.

---

## Misuse Scenarios

CLPD should *not* be used to:
- Fake prestige by labeling self-contained prompts as “locked”
- Obscure dependencies behind a paywall
- Hide malicious instructions under a false flag of context sensitivity

---

## Recognizing CLPD in Everyday Prompts

| Prompt Pattern         | Example Phrase                          | Hidden Dependency             | CLPD Relevance                    |
|------------------------|------------------------------------------|-------------------------------|-----------------------------------|
| **Implicit Role Cue**  | “As a senior strategist, advise me on…” | System prompt                 | Role assumed but not visible      |
| **Functional Framing** | “Help me reflect on my last message…”   | Prior thread turns            | Requires unseen conversational arc|
| **Memory Recall Ask**  | “Based on what I told you last week…”   | Long-term memory              | Prompt alone can’t reproduce it   |
| **Tone-Carried Ask**   | “Let’s go back to brainstorming.”       | Session tone or prior behavior| Fragile without shared continuity |

---

## Example: CLPD Prompt Card

```txt
CLPD Prompt Card

Title: Weekend Planning Assistant  
Author (opt.): ContextualWeaver  
CLPD Label: CLPD/1.0 requires:system,thread:1

Summary:  
This prompt helps generate tailored weekend plans based on the user’s past preferences and lifestyle hints.

Dependencies:
- System role: Friendly Concierge  
- Prior chat turn: A message describing last weekend’s activities

Failure Modes:
- Without system role, tone may feel impersonal or overly generic  
- Without prior chat turn, suggestions won’t reflect recent habits

Ethical Notes:
- CLPD label makes clear that personalization depends on context  
- Prevents misleading reuse where “custom fit” might be assumed  
- Reinforces that simple-looking prompts can hide deeper scaffolding

Version Notes:
- v1.0 — Designed for in-thread companion use
```

---

## Why this matters

As LLM platforms evolve to support memory, session scope, and richer user profiles, the visible prompt becomes only one part of the behavioral equation.

CLPD helps prompt authors surface those hidden dependencies — so others don’t misattribute outcomes to the prompt text alone.

It’s a bridge toward honest prompt packaging and context-aware sharing.

---

## Get Involved

- [ ] CLPD Label Spec  
- [ ] CLPD Template  
- [ ] CLPD Primer  
- [ ] Spread the word (Seed mentions)

Join the conversation, remix responsibly, and help shape a more honest ecosystem of prompt sharing.

---

© ContextualWeaver, 2025. Released under CC BY 4.0.  
Maintained and published by @ContextualWeaver in the spirit of open interoperability and prompt ethics.
