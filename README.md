# Microsoft Foundry – General Availability (GA) Overview & Enterprise Enablement

## 1. Purpose

This document provides a detailed and structured overview of Microsoft Foundry (GA), including:
- Supported enterprise scenarios
- Feature readiness (GA vs Preview)
- Evaluation, guardrails, observability
- Governance and production-readiness guidance
- Enablement and adoption approach

---

## 2. What is Microsoft Foundry (GA)?

Microsoft Foundry is now **Generally Available (GA)**, marking a transition from pilot/experimental use to **secure, enterprise-ready production usage**.

It is designed for teams that need to:

- Build AI solutions at scale  
- Deploy and manage models and agents  
- Operate AI systems with governance and monitoring  

### Core concept:
Unified lifecycle → Discover → Build → Operate
This lifecycle ensures:
- Faster development cycles  
- Consistent workflows  
- Governance and compliance integration  

---

## 2a. Agent Architecture (High Level)


<img width="1536" height="1024" alt="Designer (15)" src="https://github.com/user-attachments/assets/b4009c34-a573-4164-b601-4a170b7ec63e" />


### Architecture Overview

The diagram above illustrates the full agent architecture within a **Microsoft Foundry Project**, covering:

#### 🔵 Sources & Inputs
| Source | Examples |
|--------|---------|
| User / Channels | Web / Mobile App, Teams / Slack, API / SDK |
| Enterprise Data | Documents, Databases, Files / SharePoint, Knowledge Bases |
| Real-time Data | APIs, Events / Streams, IoT / Telemetry |
| Unstructured Content | PDF / Images, Audio / Video, Email / Chats |

#### 🤖 Agent Orchestration (Core Loop)
The agent operates in a continuous cycle:
1. **Plan** – Understand goal & create plan
2. **Reason** – Break down tasks & decide actions
3. **Act** – Invoke tools & services
4. **Observe** – Process results & iterate
5. **Respond** – Generate final response

*Memory (Short-term Session State)* flows across all orchestration steps.

#### 🧠 Model Layer
- **Azure OpenAI Service** (Foundation / LLMs)
- **Other Foundry Models** (Microsoft / OSS / Partner)
- **Model Gateway & Routing** (Safety, Cost, Latency)

#### 🛠️ Tool & Service Layer
- **Foundry Tools (Built-in):** Web Search, Code Interpreter, File Search, Computer Use, etc.
- **Custom Tools:** Functions, APIs, Connectors
- **MCP / OpenAPI / REST** – Standardized tool integration

#### 📚 Knowledge Layer (RAG)
- **Azure AI Search** (Vector + Hybrid Search)
- **Embeddings** (Azure OpenAI Embeddings)
- **Indexing Pipeline** (Chunk, Enrich, Embed, Index)
- **Data Connectors** (Blob, DB, Confluence, SharePoint, Websites)

#### 🏢 Enterprise Systems & Actions
| Category | Examples |
|----------|---------|
| Business Applications | ERP / CRM, ITSM, Custom Apps |
| Process Automation | Logic Apps, Power Automate, Workflows |
| Data Stores | SQL / Cosmos DB, Data Lake / Storage, Operational DBs |
| External Systems | SaaS / 3rd Party APIs, Partner Systems, Internet Services |

#### 📊 Observability, Evaluation & Governance
| Capability | Details |
|-----------|---------|
| **Evaluations** | Quality / Correctness, Safety / Groundedness, Custom Metrics |
| **Tracing** | End-to-end Traces, Tool Calls, Latency Analysis |
| **Monitoring** | Performance, Usage / Token, Cost Monitoring |
| **Guardrails & Safety** | Content Safety, Prompt Shields, PII / Data Protection |
| **Red Teaming** | Vulnerability Testing, Jailbreak Testing, Risk Assessment |
| **Audit & Compliance** | Audit Logs, Access Logs, Policy Compliance |

#### 🔐 Security, Identity & Governance (Cross-cutting)
| Domain | Details |
|--------|---------|
| **Microsoft Entra ID (RBAC)** | Users, Groups, Service Principals |
| **Private Networking** | VNet, Private Link, NSG, Firewall |
| **Data Security** | Encryption (At-rest/In-transit), Keys (Key Vault) |
| **Policies & Compliance** | Azure Policy, Purview, Regulatory Compliance |
| **Cost Management** | Budgets, Alerts, Chargeback |
| **Environment Strategy** | Dev / Test / Prod Landing Zones |

> **Notes:**
> - Secure by design
> - Scalable & highly available
> - Built-in enterprise governance

---

## 3. What GA Means (Key Capabilities)

At GA, Foundry provides:

### ✅ Production-ready platform
- Validated end-to-end AI workflows
- Reliable deployment and operational capabilities

### ✅ Enterprise features
- Role-Based Access Control (RBAC)
- Audit logs and compliance controls
- Monitoring and alerting
- Virtual network integration

### ✅ Unified developer experience
- Portal, APIs, SDKs, CLI aligned
- Consistent lifecycle across tools

### ✅ Defined GA scope
- Core scenarios supported in Foundry projects
- Non-supported scenarios handled via Foundry (classic)

---

## 4. Core Scenarios Supported at GA

### 4.1 Model Lifecycle
- Discover models
- Deploy models
- Run inference
- Manage model deployments
- Transition to agent-based workflows

---

### 4.2 Agent Development
- Build and manage AI agents
- Integrate:
  - Evaluations (GA)
  - Red teaming (GA)
  - Monitoring (partial)
  - Tracing (partial)
  - Guardrails (partially GA)

---

### 4.3 Operate & Administration
- Manage AI assets and agents
- Enforce governance policies
- Control quotas and administration features

---

## 5. Feature Readiness (GA vs Preview)

### ✅ Fully GA
- Model deployment & inference
- Core agent development
- Evaluations
- Red teaming
- Data handling (core)
- Admin and quota management

---

### ⚠️ Partial / Preview
- Workflows
- Advanced tracing (VNet scenarios)
- Monitoring
- Memory
- Knowledge features
- Agent guardrails
- Optimization features

---

## 6. Unsupported Scenarios (GA Scope Limitation)

The following are not supported in the new Foundry portal at GA:

- Standalone Azure OpenAI resources outside Foundry projects  
- Assistant authoring (legacy assistants)  
- Content Understanding  
- Audio playground  
- Some fine-tuning scenarios  
- Direct dataset ingestion via UI (limited flows)  

➡️ These require use of **Foundry (classic)**

---

## 7. Governance & Security

### Core Capabilities:
- RBAC via Microsoft Entra ID  
- Audit logs and compliance  
- Policy-driven controls  
- Network isolation (partial support)

---

### Best Practices:
- Use **Entra ID + RBAC** for production  
- Avoid API keys where fine-grained access is required  
- Restrict preview features in production environments  

---

## 8. Evaluation, Guardrails & Responsible AI

### Evaluation (GA)
- Integrated evaluation pipelines  
- Quality, accuracy, and performance validation  

---

### Red Teaming (GA)
- Systematic testing of AI outputs  
- Identification of vulnerabilities and risks  

---

### Guardrails
- Model guardrails → GA  
- Agent guardrails → Preview  

---

### Key Outcomes:
- Reduced hallucination  
- Safer outputs  
- Compliance with policies  

---

## 9. Observability & Monitoring

### Tracing
- Track agent execution flows  
- Debug reasoning steps  

---

### Monitoring
- Observe performance, usage, and reliability  

⚠️ Some capabilities are still in preview → validate before production use  

---

## 10. Memory & Data Considerations

### Current State:
- Memory features are in preview  

---

### Recommended Pattern:
Do NOT rely on memory alone

Use:
- Retrieval-Augmented Generation (RAG)
- External data systems:
  - AI Search
  - Databases
  - Document stores

---

## 11. Production Readiness – Prerequisites

Before deploying in production:

- Define required scenarios (models, agents, operations)
- Identify dependencies on preview features
- Establish policy for GA-only usage
- Configure RBAC roles and identities
- Validate model & feature availability by region
- Plan migration path from existing systems

---

## 12. Common Pitfalls

Avoid:

- Using preview features as production dependencies  
- Relying only on API key authentication  
- Ignoring regional availability of models  
- Migrating without fallback to classic portal  
- Assuming all features support private networking  

---

## 13. Enterprise Architecture Guidance

### Recommended Setup:
- Identity → Entra ID + RBAC  
- Environments → Dev / Test / Prod separation  
- Platform → Foundry projects as central hub  
- Governance → policies + controls  
- Cost → quota and monitoring  

---

## 14. Suggested Enablement Approach

### Phase 1 – Foundations
- Foundry overview  
- AI lifecycle  
- Core platform understanding  

---

### Phase 2 – Role-Based Enablement
- Agent development  
- Evaluation and observability  
- RAG-based architectures  

---

### Phase 3 – Architecture & Governance
- AI landing zones  
- Security models  
- Deployment patterns  

---

## 15. Suggested Hands-on Activities

- Build AI agents using Foundry  
- Implement evaluation pipelines  
- Add guardrails and monitoring  
- Integrate external data (RAG)  
- Analyze performance using tracing  

---

## 16. Key Takeaways

- Foundry GA enables **enterprise-grade AI deployment**
- Supports **end-to-end lifecycle (Discover → Build → Operate)**
- Built-in capabilities for:
  - Evaluation
  - Governance
  - Observability
- Requires **careful handling of GA vs Preview features**

---

## 17. Next Steps

- Explore Foundry project setup  
- Validate feature readiness for target scenarios  
- Start with pilot use cases  
- Scale with governed enterprise architecture  
