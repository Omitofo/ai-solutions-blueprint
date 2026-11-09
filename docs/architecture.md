# Technical Architecture

## Design goals

- Model-independent (swap LLMs without rewriting the business layer)
- Multi-tenant ready (data isolation per client)
- High reuse of components across clients
- Clear separation of concerns
- Observable (cost, success rate, human intervention, latency)
- Human-in-the-loop for high-risk actions

---

## Layered architecture

```
CLIENT INTERFACE
Chat · Dashboard · WhatsApp · Teams · Web app

AGENT MANAGEMENT LAYER
Agent teams · Roles · Permissions · Tasks · Memory · Approvals

ORCHESTRATION LAYER
n8n · LangGraph (when needed) · API gateway · Workflow execution

LLM PROVIDERS
Grok · OpenAI · Claude · Gemini · (others)

DATA LAYER
PostgreSQL / Supabase · Object storage · Knowledge base / vector store

BUSINESS SYSTEMS
Email · CRM · ERP · Accounting · Calendar · Documents · Messaging

CROSS-CUTTING CONTROLS
Security · Logging · Cost tracking · Evaluations · Human approvals · Audit
```

---

## Recommended starting stack

| Layer              | Choice (Phase 1)              | Why                                      |
|--------------------|-------------------------------|------------------------------------------|
| Orchestration      | n8n (self-hosted or cloud)    | Excellent integrations + AI agent nodes, self-host option, good price |
| Advanced agents    | LangGraph (later)             | Complex state, branching, long-running processes |
| LLM                | Multi-provider (Grok + others)| Best model for each task type            |
| Database           | PostgreSQL / Supabase         | Structured data + auth + storage         |
| Vector / knowledge | To be decided (pgvector, etc.)| Client knowledge bases                   |
| Monitoring         | Built into workflows + simple dashboard | Cost + success + intervention tracking |
| Interface          | Start simple (chat + reports) | Avoid over-building UI early             |

**Important:** Grok is excellent for development (generating specs, code, workflows) and as one production intelligence provider. It is **not** the entire platform. Production needs proper multi-tenant isolation, credential management, usage accounting per client, versioning and backups.

---

## Integration difficulty levels (we price accordingly)

| Level | Example                          | Difficulty |
|-------|----------------------------------|------------|
| 1     | Native connector                 | Low        |
| 2     | Standard API                     | Low-Medium |
| 3     | API + auth + custom mapping      | Medium     |
| 4     | Legacy / custom API              | High       |
| 5     | No API (files / RPA)             | Very High  |

We prefer Level 1-3 clients in the early stages.

---

## Where Grok fits specifically

1. **Development & design time:** generating agent specs, tool definitions, n8n workflows, integration plans, code, documentation.
2. **Production intelligence:** selected agents where its strengths (tool calling, research, agentic behaviour) are the best fit.

We keep the door open to route different tasks to different models (cheap model for classification, stronger model for complex reasoning).
