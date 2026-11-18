# Consulting Capability Map

**Purpose:** Reference material for client discovery and solution design.  
Not used by the website or product code. Use this when assessing a client requirement, choosing tools, and deciding whether AI is actually needed.

---

## The 12 Fundamental Enterprise Operations

A functional classification independent of software vendors. One system can perform several of these.

| # | Operation | Description | Examples |
|---|-----------|-------------|----------|
| 01 | **Communicate** | Exchange information between people and systems | Emails, messages, meetings, notifications |
| 02 | **Store** | Preserve information for future use | Files, documents, records, databases |
| 03 | **Retrieve** | Find and access existing information | Search, queries, document retrieval |
| 04 | **Transform** | Convert information into another format or structure | Extraction, classification, translation, summarization |
| 05 | **Analyze** | Understand data and derive insights | Calculations, metrics, forecasting, anomaly detection |
| 06 | **Decide** | Choose what should happen based on rules or reasoning | Approvals, eligibility, prioritization, recommendations |
| 07 | **Execute** | Perform actions that change the state of the business | Create orders, update records, send invoices |
| 08 | **Coordinate** | Organize tasks and activities across people and systems | Workflows, assignments, orchestration |
| 09 | **Monitor** | Observe activity and detect important changes | Alerts, logs, monitoring, compliance checks |
| 10 | **Secure** | Control who can access or change information | Identity, permissions, authentication, auditing |
| 11 | **Interact** | Provide interfaces for humans and other systems | Dashboards, forms, chatbots, APIs |
| 12 | **Learn & Optimize** | Improve performance using feedback and historical results | Machine learning, evaluation, optimization |

These are not 12 separate types of software. The classification describes **what a system does**, not what its marketing department calls it.

---

## Tool Capability Matrix

Legend:
- **Strong** — Native, core capability
- **Possible** — Supported, often through configuration or integration
- **—** — Not generally its primary purpose

| Tool / Technology | Store | Retrieve | Transform | Analyze | Decide | Execute | Orchestrate |
|-------------------|-------|----------|-----------|---------|--------|---------|-------------|
| Outlook | Strong | Strong | Possible | — | — | Strong | Possible |
| SharePoint | Strong | Strong | Possible | — | — | Possible | Possible |
| Salesforce | Strong | Strong | Possible | Possible | Possible | Strong | Strong |
| SAP | Strong | Strong | Possible | Possible | Strong | Strong | Strong |
| Power BI | — | Strong | Possible | Strong | Possible | — | Possible |
| SQL Server | Strong | Strong | Strong | Possible | Possible | Possible | — |
| Python | Possible | Strong | Strong | Strong | Strong | Strong | Possible |
| n8n | Possible | Strong | Strong | Possible | Possible | Strong | Strong |
| Power Automate | Possible | Strong | Strong | Possible | Possible | Strong | Strong |
| OpenAI API | — | Possible | Strong | Possible | Strong | Possible | Possible |
| LangGraph | Possible | Possible | Strong | Possible | Strong | Strong | Strong |
| Kafka | Possible | Possible | — | — | — | Possible | Strong |

*This table can (and should) be extended with more tools as we encounter them in real client environments.*

---

## Group Tools by Actual Job

Memorize the functional groups, not hundreds of product names.

### 1. Systems of Record — Where truth lives
Primarily CREATE / READ / UPDATE / DELETE

- **ERP:** SAP, Oracle, Dynamics 365
- **CRM:** Salesforce, HubSpot
- **Databases:** PostgreSQL, SQL Server
- **HR:** Workday, Personio

*Example:* Retrieve a customer's balance or update an order.

### 2. Knowledge and Content Systems
STORE / SEARCH / RETRIEVE

- SharePoint, Google Drive, OneDrive
- Box, Dropbox, OpenText
- Confluence, Notion
- Elasticsearch, OpenSearch

*Example:* Find the latest company policy or retrieve a particular contract.

### 3. Workflow and Integration Engines
TRIGGER / COORDINATE / EXECUTE

- Power Automate
- n8n
- Make, Zapier
- Workato, MuleSoft, Boomi
- Camunda, Temporal

*Example:* When an order arrives, validate it, create a record and notify the finance team.

### 4. Intelligence Systems
INTERPRET / CLASSIFY / REASON / GENERATE

- OpenAI, Anthropic, Google Gemini, Grok
- Traditional machine learning
- Specialized document AI and OCR

*Example:* Understand a customer request and determine which business process it belongs to.

### 5. Analytics and Computation
TRANSFORM / CALCULATE / ANALYZE / FORECAST

- Power BI, Tableau, Looker
- Excel
- Python, R
- Snowflake, Databricks
- dbt, Spark

*Example:* Calculate revenue by region and identify an unusual decline.

### 6. Agent and Orchestration Systems
PLAN / SELECT TOOLS / COORDINATE MULTI-STEP TASKS

- LangGraph
- Microsoft Agent Framework / Semantic Kernel
- OpenAI agent tooling
- Custom Python applications

*Example:* An agent investigates a customer issue by consulting CRM, email and order information.

### 7. Identity, Security and Governance
AUTHENTICATE / AUTHORIZE / AUDIT / PROTECT

- Microsoft Entra ID
- Okta
- CyberArk
- Microsoft Purview
- HashiCorp Vault

*Example:* Ensure an AI assistant only retrieves documents the employee is allowed to see.

### 8. User Interfaces and Interaction
PRESENT / RECEIVE INPUT / INTERACT

- Microsoft Teams, Slack
- Copilot
- Custom web applications
- Power Apps
- Internal dashboards

*Example:* An employee interacts with an AI assistant inside Teams.

> Note: Categories are based on functional responsibilities, not mutually exclusive products. Microsoft (and others) offer products in almost every category.

---

## Practical Decision Matrix (Client Discovery)

When a client describes a requirement, identify its **fundamental operation** first.

| Client says... | First principle | Technology to consider |
|----------------|-----------------|------------------------|
| "Find information in our PDFs" | Retrieve | Search, RAG, SharePoint |
| "Read invoices and extract fields" | Transform | OCR, Document AI, LLM |
| "Calculate monthly revenue" | Compute / Analyze | SQL, Python, Power BI |
| "Predict which customers will churn" | Analyze / Predict | ML, Python |
| "Decide which requests are urgent" | Classify / Decide | Rules, LLM, ML |
| "Send an email automatically" | Execute | Outlook API, Power Automate / n8n |
| "Update our CRM automatically" | Execute | Salesforce API |
| "Connect five systems together" | Orchestrate | n8n, Workato, APIs |
| "Answer questions about company policies" | Retrieve / Reason | RAG, LLM |
| "Investigate a customer problem" | Multi-step reasoning | Agent + APIs |
| "Notify us when something changes" | Event / Monitor | Webhooks, Kafka |
| "Make sure employees only see authorized data" | Secure | Entra ID, RBAC |
| "Show management business performance" | Analyze / Present | Power BI, Tableau |

**The architecture follows the operation.**

Do not automatically choose an AI agent just because the customer uses the word "automation."

- Copy data from an email into a spreadsheet → a workflow is usually enough.
- Investigate a complicated situation, compare multiple sources and decide actions → an agent may make sense.

---

## The Four Components That Tie Everything Together

These four things are often confused:

| Component | Responsibility | Example |
|-----------|----------------|---------|
| **System of record** | Owns the business information | SAP, Salesforce, PostgreSQL |
| **Intelligence** | Understands, interprets or reasons | GPT, Claude, Grok |
| **Execution engine** | Performs actions and coordinates processes | APIs, n8n, Power Automate |
| **Interface** | Allows humans to interact | Teams, Slack, web app |

### A useful general-purpose mental model

```
USER INTERFACE
Teams / Slack / Web application

INTELLIGENCE
LLM / RAG / Agent

EXECUTION
APIs / Python / n8n / Power Automate

BUSINESS DATA
Salesforce / SAP / SQL

KNOWLEDGE
SharePoint / Drive / RAG

Security and governance across every layer
Identity, permissions, audit, monitoring and approvals
```

This is **not** a mandatory architecture. Sometimes the intelligence is embedded in the business application, sometimes the workflow engine handles everything, and sometimes you build a custom backend. It is a useful mental model.

---

## Ultimate Cheat Sheet

If you encounter a new technology, ask what fundamental operation it specializes in.

| If you need to... | Look at... |
|-------------------|------------|
| Store information | SQL, PostgreSQL, SAP, Salesforce |
| Find information | Search engines, SQL, RAG |
| Extract information | OCR, Document AI, LLMs |
| Transform information | Python, Pandas, dbt |
| Calculate something | SQL, Python, Excel |
| Analyze patterns | Power BI, Databricks, ML |
| Make decisions | Rules engines, ML, LLMs |
| Execute actions | APIs, connectors, RPA |
| Coordinate processes | n8n, Power Automate, Temporal |
| Build autonomous workflows | LangGraph, agent frameworks |
| React to events | Webhooks, Kafka, EventBridge |
| Control access | Entra ID, Okta, RBAC |
| Monitor systems | Datadog, OpenTelemetry |
| Present information | Teams, Power Apps, dashboards |

---

## Three Dimensions to Assess for Every Operation

1. **What is being operated on?**  
   Documents, structured records, messages, transactions, people or events.

2. **What operation is required?**  
   Retrieve, transform, analyze, decide or execute.

3. **What level of autonomy is required?**  
   Human-operated → Deterministic automation → AI-assisted → Autonomous agent.

The third dimension is especially important when designing AI solutions.

---

## How to Approach a Business Problem

1. Identify the **operation**.
2. Identify the **data**.
3. Choose the **execution mechanism**.
4. Decide whether **AI is actually needed**.

You can now approach a business problem without immediately thinking about which AI framework to use.

---

## Suggested Next Evolution

Turn this into an interactive **Enterprise Systems Capability Map** where you can:
- Select a business operation
- See which tools can execute it
- See what integrations are required
- See which AI architecture fits

For now this file is the living reference.
