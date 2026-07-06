---
name: worldview-synthesis
description: Articulates and documents a personal worldview—beliefs, values, and tensions—into structured YAML data and narrative outputs (mission, thesis, essay). Use when someone wants to articulate their values, explore what they believe, document their philosophy, write a manifesto, or define a leadership philosophy; triggers on phrases like "articulate my values", "figure out what I believe", "document my philosophy", "write a manifesto", "explore my beliefs", "define my leadership philosophy".
---

# Worldview Synthesis

**Core principle:** A worldview isn't a list of opinions—it's a graph of beliefs with tensions. The goal is to surface what someone already believes, name the contradictions, and synthesize into something they can share.

## When to Use

- Someone says "I want to articulate my values"
- Someone says "help me figure out what I believe"
- Someone wants to document their philosophy
- Someone is preparing for leadership, writing a manifesto, or defining a company culture

## The Method

### Phase 1: Bootstrap Structure

Create project structure:

```
worldview/
├── data/
│   ├── schema.yaml      # Structure definitions
│   ├── ideas.yaml       # Belief nodes
│   ├── sources.yaml     # Influences (books, people, experiences)
│   └── tensions.yaml    # Productive paradoxes
├── narrative/
│   ├── mission.md       # One-liner + principles
│   ├── thesis.md        # One page
│   ├── synopsis.md      # Three sections
│   └── full-narrative.md
└── README.md
```

### Phase 2: Seed from Sources

Ask: "What books, articles, people, or experiences shaped how you see the world?"

For each source, extract 3-5 key ideas. This gives you initial nodes to build from.

### Phase 3: Interrogation Rounds

Run 4-6 rounds of questions. Each round covers 3-4 domains.

**Question Design Rules:**
- 2-4 options per question, each with label + description
- Use `multiSelect: true` when beliefs can coexist
- Leave room for custom "Other" answers
- Options should be genuinely different, not leading

**Domains to Cover:**

| Domain | Example Questions |
|--------|-------------------|
| **Mortality** | How does knowing you'll die shape how you live? |
| **Metaphysics** | What's your relationship with spirituality/religion? |
| **Relationships** | How do you think about romantic partnership? |
| **Parenting** | Philosophy on having/raising children? |
| **Body** | How do you relate to physical health and aging? |
| **Vices** | Relationship with alcohol, drugs, pleasure? |
| **Money** | Beyond spending—freedom, obligation, suspicion? |
| **Competition** | Collaboration vs ruthlessness? |
| **Trust** | Default open or earned? |
| **Learning** | Autodidact, mentorship, formal education? |
| **Nature** | Essential or nice to visit? |
| **Leadership** | Natural, reluctant, servant, example? |
| **Emotion** | Relationship with anger? |
| **Recognition** | Need fame? Already had it? |
| **Rest** | Protect sleep or run on fumes? |
| **Conflict** | Clear air fast or avoid? |
| **Work** | Philosophy on effort, failure, shipping? |
| **Ethics** | Hard lines vs softer truths? |
| **Society** | Diagnosis of what's broken? |
| **Future** | Optimism, pessimism, preparation? |

### Phase 4: Capture Tensions

When beliefs contradict, DON'T resolve—NAME:

```yaml
- id: collaboration-vs-ruthlessness
  ideas: [collaboration-over-competition, strategic-ruthlessness]
  description: "Default to positive-sum, but crush when necessary"
  resolution: |
    Different contexts call for different modes. Collaboration is default.
    Ruthlessness is available when needed. The key is knowing when to switch.
  status: embraced  # or: unresolved, resolved
```

Tensions are often the most interesting part of a worldview.

### Phase 5: Generate Narratives

From data, generate at ascending scales:

1. **Mission** (~100 words): The one-liner + 5-7 principles
2. **Thesis** (~300 words): One page that captures the core
3. **Synopsis** (~500 words): Three sections (Diagnosis, Orientation, Ethics)
4. **Full Narrative** (~2000 words): Complete essay with all major themes

### Phase 6: Iterate

A worldview is living. Add new beliefs, update old ones, regenerate narratives.

## Idea Node Schema

For the canonical schema definition (Idea, Source, Tension types with all fields and enums), see [`references/schema.yaml`](references/schema.yaml).

## Tension Statuses

- **embraced**: Both sides are true. Live in the paradox.
- **resolved**: Found synthesis that dissolves the tension.
- **unresolved**: Genuinely don't know. Honest about uncertainty.

## Sample Interrogation Round

For the full 6-round question bank (covering Foundations, Body & Pleasure, Relationships & Learning, Emotion & Recognition, Work & Ethics, Society & Future), see [`references/interrogation-questions.md`](references/interrogation-questions.md). Each question includes multi-select options with descriptions ready for the AskUserQuestion tool.

## Red Flags

- **"I don't have a worldview"** → Everyone does. Start with sources.
- **No tensions found** → Dig deeper. Everyone has contradictions.
- **All high confidence** → Push on uncertainty. What don't you know?
- **Only "should" beliefs** → Ask what they actually DO, not just believe.
- **Avoiding hard questions** → Death, money, conflict—go there.

## Output Quality Checklist

- [ ] Core thesis is one sentence
- [ ] Mission fits on a card
- [ ] Tensions are named, not hidden
- [ ] Hard lines are clear (non-negotiables)
- [ ] Softer truths acknowledged (where grace lives)
- [ ] Narrative voice sounds like the person
- [ ] Contradictions are embraced, not resolved away

## Example Mission Output

```markdown
# Mission Statement

**Put people first. Prepare for what's coming. Fight anyway.
Find the cracks. Leave no trace.**

---

We operate with systemic pessimism and local optimism.
We hold strong opinions weakly.
We embrace productive paradoxes.
We draw hard lines on human rights.
We extend grace for pain, never for harm.

People first. Always.
```

## Reference Materials

- **Full 6-round question bank:** [`references/interrogation-questions.md`](references/interrogation-questions.md) — ready-to-use questions across all domains, formatted for AskUserQuestion.
- **Canonical entry schema:** [`references/schema.yaml`](references/schema.yaml) — type definitions for Idea, Source, and Tension nodes including all field names and enums.
