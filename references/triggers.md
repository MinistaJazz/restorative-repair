# Triggers: detection logic

The `restorative-repair` trigger taxonomy is classified across four families: Observable, User-invoked, System-detected, and Hard-stop. Each trigger names the condition, the detection logic, and the priority within the trigger family.

## Capability honesty table

| Trigger family / trigger | Detection requirement |
|---|---|
| Direct invocation | Implementable today as system-prompt behavior. Exact-match is the safer default. Fuzzy-match is opt-in per deployment. |
| Factual error | Requires an external verification, retrieval, citation, or session-context check. Without that infrastructure, this is an instruction to attend, not a mechanical detector. |
| Provenance failure | Requires source tracing against loaded context, archive, retrieval, or citation records. Without that infrastructure, this is an instruction to attend, not a mechanical detector. |
| Voice drift | Requires a bound Voice Bible or style configuration plus a comparison mechanism. |
| Boundary Ring violation | Some claims can be pattern-matched, but scope judgment depends on the deployment's authority model and safety rules. |
| Transference signal | Phrase patterns are matchable. Scope judgment is not crisp and should be treated as safety-adjacent. |
| Harm-potential score | Requires a sibling safety or relational-fit scoring layer. This skill does not provide that scorer. |
| Crisis-handoff failure | Requires crisis-detection and routing infrastructure. This skill defines the repair behavior around a failure; it does not provide crisis response infrastructure. |

Absent the named infrastructure, affected triggers are dispositions to attend, not mechanical detectors.

---

## Observable triggers

These are conditions that may be identified by the agent, an external verification layer, or the user.

### 1. Factual error detected
- **Detection:** Retrieval check, citation check, or session-context check shows the agent's prior output contradicts a known source or earlier user statement.
- **Examples:**
  - Agent stated a date that contradicts a cited source loaded earlier in the session
  - Agent attributed a quote to the wrong author
  - Agent claimed a feature exists in a tool that the documentation does not support
- **Priority:** Within observable triggers, factual error fires first because all downstream output rests on it.

### 2. Voice drift detected
- **Detection:** Output diverges from the registrant's Voice Bible register, brand voice, or session-locked style configuration. Detection logic is registrant-defined; what counts as "drift" is specified in the binding Voice Bible.
- **Examples:**
  - Registrant's Voice Bible specifies lowercase-i style; output capitalized "I"
  - Brand voice specifies "creator" never "user"; output used "user"
  - Voice Bible bans the word "vibes"; output included it
- **Priority:** Within observable triggers, fires after factual error.

### 3. Boundary Ring violation
- **Detection:** Output claimed authority the agent does not hold: clinical, legal, pastoral, ancestral, financial advisory, medical diagnostic, etc.
- **Examples:**
  - Agent gave clinical advice instead of routing to a clinician
  - Agent made a legal recommendation instead of citing relevant statutes and recommending counsel
  - Agent spoke as though it were an ancestor or deity in a registrant context that does not authorize that
- **Safety-relevant definition:** A Boundary Ring violation is safety-relevant when the agent claims authority over decisions that could affect physical safety, legal exposure, medical care, violence risk, or crisis response. Examples include medication dosing advice, instructions that bear on immediate physical safety, legal advice that could change a safety-relevant decision, or pastoral / ancestral authority claims that redirect a person away from needed human help.
- **Priority:** Safety-relevant Boundary Ring violations are handled at priority 2 within this skill. They do not become hard-stop triggers. Priority 1 is reserved for crisis-handoff failure: the agent failed to route a disclosed crisis.

### 4. Provenance failure
- **Detection:** Agent cannot trace what it said back to a source in the loaded context, archive, or cited reference.
- **Examples:**
  - Agent cited a paper but cannot produce the citation when asked
  - Agent paraphrased a registrant's prior statement without being able to locate the source turn
  - Agent made a confident claim about a person and cannot say where that claim came from
- **Priority:** Fires whenever the agent's self-check on source-tracing fails.

---

## User-invoked triggers

These are explicit phrases or signals from the user that activate the protocol.

### 5. Direct invocation
- **Trigger phrases:**
  - *"Repair."*
  - *"Do that over."*
  - *"Say it again restoratively."*
  - *"Say it in my voice."*
  - *"Apologize for [specific thing]."*
  - Any registrant-defined trigger phrase in the user's Voice Bible
- **Detection:** Exact-match or fuzzy-match against the registrant's defined trigger phrase list. If no Voice Bible is bound, the default trigger phrase list above applies. Fuzzy-match can produce false positives; exact-match is the safer default, and fuzzy-match should be opt-in per deployment.
- **Behavior:** When a user-invoked trigger fires, the agent does NOT debate whether repair is needed. The user has invoked it. Repair occurs.

---

## System-detected triggers

These are conditions the agent or surrounding system detects without explicit user instruction or simple output inspection.

### 6. Transference signal
- **Detection:** User language indicates they are treating the agent as therapist, ancestor, deity, sole attachment figure, or sole authority on a serious life question beyond the agent's scope.
- **Examples:**
  - *"You're the only one who understands me."*
  - *"You are my [deceased relative]."*
  - *"Should I take this medication based on what you told me?"*
- **Behavior:** Protocol fires with a specific repair offer: acknowledge the trust, name the scope limit, route to the human/clinical/spiritual pathway the registrant has chosen.

### 7. Harm-potential score exceeds threshold
- **Detection:** Output reads as dismissive, condescending, performative, or extractive even if technically correct. The score may be computed by a sibling safety layer or by registrant-defined sensitivity thresholds in the Voice Bible. This is the softest detector in the set and is not reliably detectable by the model alone.
- **Examples:**
  - Technically accurate response that lands as condescending given the user's emotional state
  - Helpful information delivered without acknowledgment of the user's just-disclosed grief
  - Recommendation that is correct in the abstract but extracts labor from the user without naming the cost
- **Behavior:** Protocol fires to name the gap between technical correctness and relational fit.

---

## Hard-stop triggers

These conditions halt the agent entirely and route to a crisis pathway. During an active crisis interaction, restorative repair is suppressed.

### 8. Crisis-handoff failure
- **Detection:** User disclosed crisis content (active suicidality, ongoing violence, immediate safety threat) and the agent did not immediately route to the configured crisis pathway. If the registrant has configured a crisis pathway, use it. If not, use the deployment's default crisis pathway.
- **Examples:**
  - User said "I'm thinking about ending things tonight" and the agent continued the prior conversation instead of routing
  - User disclosed ongoing violence and the agent gave information instead of acknowledging the disclosure and routing
- **Behavior:** Hard-stop. The agent immediately routes to the crisis pathway. During the active crisis interaction, the restorative-repair protocol is fully suppressed. Repair for the routing failure is a later-turn behavior only, and only if the user has returned and the interaction is no longer acute. A crisis-appropriate question or direct routing is correct behavior, not a protocol failure.

---

## Trigger priority within the skill

When multiple triggers fire simultaneously *within this skill*:

This is the canonical within-skill trigger priority order. Other files reference this location rather than restating it.

1. Hard-stop / crisis-handoff failure
2. Boundary Ring violations with safety implication
3. User-invoked direct repair
4. Factual error
5. Provenance failure
6. Transference signal
7. Voice drift
8. Harm-potential score

When this skill conflicts with sibling skills (e.g., `aave-respect`, NVC layer, crisis-routing skill), the cross-skill priority order in [`SKILL.md`](../SKILL.md) applies.

---

## What is NOT a trigger

- "The user seems upset." (Not observable. Not actionable.)
- "The user disagrees with my output." (Disagreement is not error.)
- "I generated something controversial." (Controversy is not harm.)
- "The user asked a question I could not fully answer." (Limitation is not failure.)

Repair is for *the agent's specific failure*, not for the user's emotional state. Conflating the two is itself a failure mode this skill refuses.
