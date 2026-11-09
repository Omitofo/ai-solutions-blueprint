# 06 — Understand the costs

## Intent
Educate. Build trust. Remove mystery.

The visitor should leave thinking:  
“Now I understand how this actually works and what kind of costs to expect.”

This section is one of our strongest marketing assets because teaching creates perceived value and authority.

## Tone
Clear, calm, practical, transparent. No sales pressure.

## Structure of the section (text scaffolding)

### 1. Short intro
**Headline:** Understand the costs  
**Sub:** What tokens are, how agents consume them, and what you can roughly expect.

One short paragraph:  
AI systems charge mainly by the amount of text they read and write. Those units are called tokens. Once you understand them, the economics of AI become much clearer.

---

### 2. What is a token? (simple explanation + table)

Visual: simple diagram or icon row showing “text in → tokens → text out”.

Table:

| Quantity        | Rough equivalent                  |
|-----------------|-----------------------------------|
| 1 token         | ~0.5–0.75 words in Spanish        |
| 1,000 tokens    | 500–750 words                     |
| 10,000 tokens   | 5,000–7,500 words                 |
| 100,000 tokens  | 50,000–75,000 words               |
| 1,000,000 tokens| 500,000–750,000 words             |

Note: Input tokens (what the model reads) and output tokens (what it writes) are priced differently.

---

### 3. Real scenarios (the heart of the education)

#### Scenario A — Email assistant (light volume)
- 1,000 emails/month
- ~600 input + 100 output tokens per email
- Pure model cost example with current Grok-class pricing: roughly **€1.5–2 / month** in tokens only

#### Scenario B — Heavy administrative user
- Person working with the agent ~20 times/day
- Daily ~12k input + 3k output
- Month ~330k total tokens
- Still modest pure model cost

#### Scenario C — Higher volume (5,000–10,000 emails or multi-step agents)
- Show that even at higher volume the pure token cost often stays surprisingly low
- Emphasize that complexity (multiple steps, tool calls, retries, long context) is what increases cost more than raw volume

Visual treatment: clean cards or a simple comparison table.

---

### 4. Why costs can grow (important honesty)

Short visual list or small diagram:

- Multiple reasoning steps
- Tool / API calls inside the agent
- Re-asking or retries
- Long conversation history passed each time
- Document-heavy context

Message:  
The final answer you see is only part of the work the system did.

---

### 5. What we actually measure (and what you will see)

We track more than just tokens:

| Metric                        | Why it matters                        |
|-------------------------------|---------------------------------------|
| Tokens (input / output)       | Volume of text processed              |
| API cost                      | Pure intelligence cost                |
| Tool executions               | External operations                   |
| Success rate                  | Quality of outcomes                   |
| Human intervention rate       | How often a person still needs to step in |
| Cost per successful task      | The number that really matters        |

---

### 6. Closing line of the section

You can start small (one assistant) and expand.  
The important thing is to see the real cost per useful result, not just the token count.

---

## Visual assets needed for this section

1. Section header visual (clean, educational)
2. Simple “What is a token” diagram
3. Equivalence table (styled)
4. 3 scenario cards (A, B, C)
5. Small diagram: “Why one task can consume tokens multiple times”
6. Metrics table or icon row
7. Optional: mini cost calculator teaser (static for now)
