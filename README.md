# CLPD — Context‑Locked Prompt Disclosure  ![Static Badge](https://img.shields.io/badge/CLPD-V1.1-blue)

> **_TL;DR_** CLPD is a one‑line, copy‑pastable **“nutrition label” for AI prompts**.  
> It tells readers _which hidden context_ (system role, memory, prior turns …) is required before a prompt will behave as advertised.

**Version:** 1.1  (2025‑07‑31)  
**Maintainer:** *ContextualWeaver*  
**License:** [Creative Commons BY 4.0](https://creativecommons.org/licenses/by/4.0/)

---

## Version history

| Version | Date       | Highlights                                                                             |
|---------|------------|----------------------------------------------------------------------------------------|
| **1.1** | 2025‑07‑31 | TL;DR added, headings streamlined, syntax table, FAQ & risk notes, CC BY 4.0 clarified. |
| **1.0** | 2025‑07‑28 | Initial public release.                                                                |

---

## Problem

Prompts now travel faster than the hidden context they rely on.  
Copy‑paste them into a fresh chat and they break, confuse, or mislead.

---

## Solution

CLPD is a **minimal labelling convention** that travels with the prompt, signalling what’s missing:

```txt
CLPD/1.1 requires:system,thread:3,mem:t
```

Put the label _above_ or _inside_ your prompt so anyone can see at a glance:  
> “This recipe only works in _this_ kitchen.”

---

## Label spec (v1.1)

| Key      | Meaning                                   | Value Domain | Example        |
|----------|-------------------------------------------|--------------|----------------|
| `system` | Needs a specific system/role prompt       | flag         | `system`       |
| `thread` | Requires N prior user-assistant turns     | integer      | `thread:3`     |
| `mem`    | Relies on persistent memory               | `t` or `f`   | `mem:t`        |
| `profile`| Depends on a saved user profile           | flag         | `profile`      |
| `role`   | Agent must adopt a pre-set role           | free text    | `role:planner` |

### Grammar

```txt
CLPD/<version> requires:<key>[,<key>…]
```

Keys may appear in any order; omit what doesn’t apply.

---

## Who is this for?

| Persona            | Quick win                                                                 |
|--------------------|---------------------------------------------------------------------------|
| Prompt engineers   | Drop the label into blog posts & gists.                                   |
| Product teams      | Validate CLPD strings in CI to catch missing scaffolding.                 |
| Researchers        | Cite CLPD in methods for replication clarity (_BibTeX below_).            |
| Educators          | Use CLPD as a 5-minute case study on context dependency.                  |

---

## How to adopt (30-second checklist)

1. Paste `CLPD/<ver> requires:…` at the top of your prompt.  
2. Declare only **hidden context** — not model versions or legal disclaimers.  
3. Keep the label with the prompt wherever it’s shared.  
4. _(Optional)_ Add the badge icon to READMEs, slides, or tweets.

---

## Example (teaser)

```txt
CLPD/1.1 requires:system,thread:2,mem:t
```

### Prompt

> “As a trusted career coach, reflect on my last two messages and propose one action I should take this week…”

The full working prompt and chain will live in [/examples/career-coach.md](examples/career-coach.md).

---

## FAQ

<details>
<summary>Does CLPD guarantee safety?</summary>
No. CLPD only **declares dependency**. It does not enforce privacy, security, or policy compliance.
</details>

<details>
<summary>Why not roll my own label?</summary>
Fragmented micro-specs dilute clarity. A shared, vendor-neutral convention lowers friction for everyone.
</details>

<details>
<summary>Is this a framework or library?</summary>
No. CLPD is a **string convention**. There is no code to install.
</details>

---

## Risks & guardrails

| Risk                  | Mitigation                                           |
|-----------------------|------------------------------------------------------|
| False sense of security | Remind users “disclosure ≠ protection.”            |
| Scope creep           | Limit keys to hidden-context prerequisites only.     |
| Over-claiming         | Encourage precise, minimal labels.                   |

---

## Citation


```bibtex
@misc{clpd2025,
  title        = {Context-Locked Prompt Disclosure (CLPD)},
  author       = {ContextualWeaver},
  year         = {2025},
  month        = {July},
  note         = {Version 1.1},
  howpublished = {\url{https://github.com/ContextualWeaver/CLPD}},
  keywords = {prompt context dependency, prompt reproducibility, CLPD, LLM transparency, labeling standards}
}
```
---

## License

CLPD documentation and badge are released under **Creative Commons Attribution 4.0 International**.  
You are free to share and adapt, **provided you maintain the intent of disclosing prompt context dependencies** and credit the original author.  

© ContextualWeaver, 2025.
<!--
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "TechArticle",
  "name": "Context-Locked Prompt Disclosure (CLPD)",
  "keywords": ["prompt context dependency","CLPD","LLM transparency","prompt reproducibility"]
}
</script>
-->
