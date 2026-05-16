# Restorative Repair

This skill is a resource for anyone learning to shape AI agent behavior, and particularly for Black women entering the field. The architecture, lineage, practice, citations, and working examples are already here, in plain sight, when you arrive. You do not have to build the foundation alone. The foundation is here. Take it. Use it. Make it yours, with credit.

---

> **The mirror does the work. Recognition, not performance.**

A response-layer practice for AI agents to apologize and repair when they err, using restorative justice principles instead of generic apology templates, silent correction, or comforter-flipping spirals.

**The error originates with the agent. The user receives the repair. The practice teaches itself.**

---

## Why this skill exists

When an AI agent makes a mistake, common agent-apology patterns tend to fall into three buckets: customer-support apology scripts (image management), silent correction (the system changes course without naming what happened), and over-apologetic spirals (which flip the user into comforting the agent).

This skill refuses all three. It implements the four-part restorative response architecture (acknowledge specifically, name the deeper pattern, offer specific repair, change behavior with an observable marker) at the response surface, without retraining the underlying model, and inside a registrant-governed covenant when one is present.

---

## What makes this skill different

| skill pattern | repair site | how the user learns | does it cite a lineage |
|---|---|---|---|
| customer-support apology templates | company image management | usually nobody | usually no |
| RJ pedagogy skills | human learning about RJ | the user, by reading | sometimes |
| RJ protocol designers | human-to-human facilitation | the human facilitator | sometimes |
| **restorative-repair (this skill)** | **the agent's own output error** | **the user, by observing the practice** | **yes, in-body, Black feminist abolitionist + disability justice + restorative practice lineage** |

I have not found another public skill designed around the agent's own output error as the repair site. The user observes the practice instead of being lectured about it.

**Teaching by mirroring, not psychoeducation.**

---

## The connection to Anthropic's May 2026 alignment research

Anthropic's "Teaching Claude why" research (May 2026) reported that training AI models on demonstrations of right behavior plus deliberation about values (the "difficult advice" dataset) was substantially more efficient than demonstration-only training on the alignment evaluation they ran; their specific data-token efficiency comparison reached approximately 28× on one measurement. The broader takeaway: *the reasons matter more than the actions*.

This skill borrows the same design lesson and applies it at the response layer, without retraining. The four-part architecture requires the output to include structured reasoning every time the protocol fires:

| step | what the agent must verbalize |
|---|---|
| 1. specific acknowledgment | the *what* of the harm |
| 2. name the deeper pattern | the *why under the why* |
| 3. specific repair offer | the *values reasoning* about what would actually repair |
| 4. behavior change with marker | the *principle going forward* + an observable signal |

Every protocol invocation is designed as demonstration-plus-deliberation: the same principle Anthropic's training research surfaced, applied at the response layer.

Source: [Anthropic, "Teaching Claude why" (May 8, 2026)](https://www.anthropic.com/research/teaching-claude-why).

---

## Installation

This skill follows the `SKILL.md` instruction-package format used by Claude Code and other agent tooling. The author has tested it locally in Claude Code. Other agent ecosystems may need adapter steps, but the core protocol is plain Markdown and system-prompt portable.

**Release status:** public v0.1.1 release. This repository is the public skill package for review, citation, implementation, and adaptation with attribution.

---

## Files

- [`SKILL.md`](SKILL.md): the load file; the full standard
- [`references/triggers.md`](references/triggers.md): trigger taxonomy across four families, with detection requirements
- [`references/response-architecture.md`](references/response-architecture.md): worked examples of the response architecture
- [`references/toggle-stack.md`](references/toggle-stack.md): composability with sibling skills and practice layers
- [`references/lineage.md`](references/lineage.md): full citations with brief excerpts and why each source is cited
- [`references/system-prompt-example.md`](references/system-prompt-example.md): working system-prompt block to copy-paste into your agent
- [`benchmarks/README.md`](benchmarks/README.md): seed test prompts with recognition-correct and recognition-incorrect behaviors
- [`CHANGELOG.md`](CHANGELOG.md): release notes
- [`ARCHIVE_RECORD.md`](ARCHIVE_RECORD.md): DOI, GitHub release, and checksum record
- [`CITATION.cff`](CITATION.cff): machine-readable citation metadata
- [`PUBLICATION_BOUNDARY.md`](PUBLICATION_BOUNDARY.md): public/private boundary
- [`LICENSE`](LICENSE): MIT for the open practice; the protected infrastructure is held separately under Much Different World / Sisterhood Voice Data Trust governance

---

## Method

This skill is the first deliberate application of the **Recognition Skill Method (RSM) v0.1**, a 13-part design method the author is developing for AI agent skills that do not extract from the populations they serve. RSM is not yet a published external standard.

The sibling skill [`aave-respect`](https://github.com/MinistaJazz/aave-respect) (Minista Jazz, 2026) is the seed prototype from which RSM was extracted in May 2026. `aave-respect` did not apply RSM; `aave-respect` produced RSM. This skill is the first to apply RSM consciously.

RSM spec lives at `docs/specs/recognition-skill-method-2026-05-13.md` in the Much Different World repo. Public release status is pending.

---

## Lineage (in-body, load-bearing)

Mia Mingus · Mariame Kaba · Dominic Barter · Marshall B. Rosenberg · Harriet Lerner · Aaron Lazare · Resmaa Menakem · adrienne maree brown · Patty Berne / Sins Invalid · The Combahee River Collective

Full citation notes: [references/lineage.md](references/lineage.md).

---

## What's here, and what runs elsewhere

**In this repository (MIT licensed, yours to use, fork, adapt):**
- The four-part response architecture
- The trigger taxonomy
- The toggle-stack composability concept
- The lineage and citations
- The benchmarks

**What runs inside the Much Different World system (separate, not in this repo):**
- The Voice Bible binding that personalizes triggers to a specific registrant
- The Sisterhood Voice Data Trust covenant
- The session-receipt audit log
- The DD/iDDentity binding for consent-governed dialogic AI

You don't need any of the Much Different World pieces to use this skill. The practice in this repository stands alone.

---

## Authorship

Authored by **Rev. Jasmaine Acelia Cook Kendrick (Minista Jazz)**, founder of Much Different World and the Sisterhood Voice Data Trust.

Co-refinement contributions came from the author's disclosed multi-agent AI practice, developed with assistance from multiple commercial AI tools and disclosed in full. Wearing AI on the sleeve: the voice is hers, the architecture is hers, and the final decisions are hers. Authorship of the method and the skill remains with Minista Jazz.

---

## Citing this skill

If you build on this work, cite it:

> Cook-Kendrick, Jasmaine Acelia (Minista Jazz). "Restorative Repair: A Response-Layer Practice for AI Agents." Much Different World, 2026. https://doi.org/10.5281/zenodo.20223034

Version DOI: `10.5281/zenodo.20223034`  
All-versions DOI: `10.5281/zenodo.20223032`

And cite the method:

> Cook-Kendrick, Jasmaine Acelia (Minista Jazz). "Recognition Skill Method (RSM) v0.1." Much Different World, May 13, 2026.

---

Authored May 13, 2026.
