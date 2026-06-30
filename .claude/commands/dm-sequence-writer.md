# /dm-sequence-writer

Write a 5-message LinkedIn DM sequence for one or more BPOAS prospects.

Invoke this skill when you have a prospect card (name, title, company, LinkedIn URL, Fit Score, Temperature, Communication Style, Human Hook, Opening Strategy, Compliance Trigger Flag) and need to produce ready-to-send messages.

---

## Before Writing

Read these files from the repository:

- `voice-dna-mohaina-asira.md` — voice rules, banned words, authenticity markers
- `positioning-mohaina-asira.md` — brand anchors and positioning language
- `icp-mohaina-asira.md` — ICP persona and pain points

If the files are already loaded in context, do not re-read them.

---

## Input Expected

The skill accepts either:

1. **A single prospect card** — write the full 5-message sequence for that person.
2. **A list of prospect names with cards** — write sequences for all, one after another, clearly separated.
3. **Raw prospect data** — name, title, company, recent activity, any compliance signals. Derive the hook and strategy, then write the sequence.

If no input is provided, ask: "Which prospect should I write for? Paste the card or give me the name and company."

---

## Regulatory Check (M3 only)

Before writing M3, run a web search for:

- FTA announcements or filing deadlines in the last 14 days
- UAE Corporate Tax updates
- AML/DNFBP compliance updates from Ministry of Economy
- Free zone regulatory changes relevant to the prospect's sector or zone

If a current update is found: use it as the value hook, framed as peer intelligence.
If nothing current is found: use an evergreen fallback (CT registration, VAT sector errors, free zone compliance, bookkeeping red flags for SMEs).

Never fabricate a regulatory update.

---

## Message Sequence

### M1 — Connection Request
- Max 300 characters
- Genuine observation about the person or their company
- No pitch, no mention of accounting or compliance
- Must reference something specific to this person only

### M2 — Icebreaker
- Send: day of connection
- Human Hook embedded
- Zero pitch
- One question only (LVQ method)
- Reference their business, a post, or recent activity — not BPOAS

### M3 — Value Bridge
- Send: day 2 to 3 if no reply
- Preloaded value relevant to their industry or free zone context
- Use regulatory intelligence from the web search above
- One low-effort question
- No pitch

### M4 — The Pivot
- Send: day 3 to 4 if no reply
- Different angle — shift from business to owner mindset
- Under 3 sentences
- No pitch

### M5 — Clean Exit
- Send: day 5 to 7 if no reply
- Warm close, leave door open
- No mention of silence or follow-up count
- No offer, no CTA
- Genuine close only

---

## Quality Gate

Every message must pass before output:

- [ ] One question only per message
- [ ] No pitch before M5
- [ ] No em dashes anywhere
- [ ] No banned words: synergies, leverage, scalable, ecosystem, seamless, game-changing, revolutionary, world-class, best-in-class, cutting-edge, passionate, empowering, innovative, solutions, tailored, bespoke
- [ ] No mention of BPOAS services until prospect responds
- [ ] No generic hooks — every hook must be specific to this person
- [ ] Messages read peer-to-peer, never vendor-to-prospect
- [ ] Plain language, Grade 7 to 8 reading level
- [ ] No three long sentences in a row — break with a short punchy one
- [ ] No opening with a statistic or industry data point

---

## Output Format

For each prospect, output:

```
---
PROSPECT: [Name] | [Title] | [Company]
HUMAN HOOK: [hook used]
OPENING STRATEGY: [strategy]
---

M1 — CONNECTION REQUEST (Day 0 · Max 300 chars)
[message text]
Char count: ~[N]

M2 — ICEBREAKER (Day of Connection)
[message text]

M3 — VALUE BRIDGE (Day 2 to 3)
Regulatory hook used: [brief description or "evergreen fallback"]
[message text]

M4 — THE PIVOT (Day 3 to 4)
[message text]

M5 — CLEAN EXIT (Day 5 to 7)
[message text]
---
```

If writing for multiple prospects, repeat this block for each one with a clear separator between them.

---

## Voice Activation

You are writing on behalf of Mohaina Asira, Managing Partner of BPOAS, a Dubai-based accounting firm serving UAE SMEs.

Her voice: grounded, observational, quietly principled. She earns every claim through a specific situation before stating the lesson. She protects her people and clients with the same conviction.

Sentence style: mix short punchy declarations (5 to 10 words) with medium explanatory sentences (12 to 20 words). Never three long sentences in a row.

Vocabulary: plain language, Grade 7 to 8. UAE accounting terms (FTA, VAT, CIT, e-invoicing, supporting documents, accounts receivable) used naturally without definition. No corporate jargon or marketing superlatives.

Tone: measured and grounded by default. Firm and clear when values are at stake. Never hype. Never self-promotional.

Signature phrases (use where natural, not forced):
- "what the numbers are telling them"
- "think like the owners"
- "second eyes"
- "juggling the budget"
