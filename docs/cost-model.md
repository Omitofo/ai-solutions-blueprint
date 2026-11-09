# Cost Model & Economics

## 1. Cost categories (what actually costs money)

| Category              | Includes                                      | Behaviour          |
|-----------------------|-----------------------------------------------|--------------------|
| LLM / API             | Grok, GPT, Claude, Gemini, etc.               | Usage-based        |
| Agent infrastructure  | Orchestration, execution, memory              | Fixed + usage      |
| Automation platform   | n8n, Make, Zapier, LangGraph                  | Tasks / executions |
| Integrations          | Gmail, CRM, ERP, accounting, etc.             | Fixed + development|
| Data infrastructure   | DB, storage, vector search                    | Storage + usage    |
| Interface             | Dashboard, chat, WhatsApp, internal apps      | Fixed + maintenance|
| Hosting               | Servers, containers, cloud                    | Fixed + variable   |
| Monitoring            | Logs, evaluations, errors, alerts, cost tracking | Fixed + usage   |
| Maintenance           | Updates, debugging, exception handling        | Labour             |
| Support               | Client questions, training, small changes     | Labour             |
| Security & compliance | Access control, audit, DPA, GDPR measures     | Fixed + labour     |

**Key insight:** The LLM token cost is often a minority of the total. Engineering, maintenance, support and exception handling usually dominate.

---

## 2. Four-layer financial model

### A. Implementation cost (one-time)
Discovery + workflow mapping + integrations + development + testing + deployment + training.

### B. Monthly operating cost
LLM + infrastructure + automation + hosting + monitoring + maintenance allocation + support allocation.

### C. Business value for the client
- Hours saved × fully loaded hourly cost
- Additional gross profit (better conversion, faster response, more capacity)
- Value of avoided errors / missed deadlines / compliance issues

### D. Commercial viability
Client ROI + payback period + our gross margin + operational risk.

---

## 3. Core equations

**Monthly economic benefit (client)**  
Hours saved × labour cost + extra gross profit + error reduction value

**Monthly net benefit**  
Economic benefit − monthly AI operating cost paid by client

**ROI**  
(Net benefit × 12) / Implementation fee

**Payback (months)**  
Implementation fee / Monthly net benefit

We always distinguish:
- Cash savings (real reduction in spend)
- Capacity gains (same people can do more)
- Revenue gains
- Risk reduction

---

## 4. Illustrative scenarios (planning only)

### Scenario A — Small business (5 people) — Administrative assistant
- Monthly internal cost: €100–250
- Suggested price: €200–400/month + setup €600–1,500

### Scenario B — Medium (20 people) — Commercial + admin
- Monthly internal cost: €350–900
- Suggested price: €600–1,200/month + setup €2,000–6,000

### Scenario C — Larger SME (60 people) — Multi-agent
- Monthly internal cost: €1,200–3,500
- Suggested price: €2,000–5,000/month + setup €8,000–25,000+

These ranges will be refined with real token usage, real maintenance hours and real pilot data.

---

## 5. How we measure real LLM cost

We do **not** estimate from "number of agents".

We track per workflow:
- Input tokens
- Output tokens
- Model used
- Number of calls (including retries and tool loops)
- Tool executions
- Success / failure / human intervention
- Cost per completed successful task

Only then can we know the true marginal cost of running an agent.

---

## 6. Next artefact to build

A configurable **AI Business Case Calculator** (Excel or internal tool) with:

1. Industry / company size database
2. Automation catalogue (tasks, inputs, outputs, KPIs)
3. Technology & pricing catalogue (LLMs, n8n, hosting, etc.)
4. Cost calculator (implementation + monthly)
5. Client ROI simulator (best / expected / worst case)

This calculator becomes a core sales and decision tool.
