# Microsoft Foundry – GA Overview & Enterprise Enablement

## Purpose
This document provides an overview of Microsoft Foundry (General Availability) and outlines key considerations for enterprise AI adoption, including evaluation, observability, memory, and governance.

---

## 1. Overview

Microsoft Foundry is now Generally Available (GA), enabling production-ready AI systems for enterprise use.

It provides an end-to-end platform across:

- Discover → Build → Operate

This enables teams to build, deploy, and manage AI systems at scale with integrated governance and operational controls.

---

## 2. Key Capabilities

### Model & Deployment
- Discover and deploy models
- Manage model lifecycle and inference

### Agent Development
- Build AI agents
- Integrate evaluation, monitoring, and tracing
- Transition from LLM applications to agent-based systems

### Operations
- Manage deployments and assets
- Apply governance policies
- Control quota and administration

---

## 3. Evaluation & Guardrails

- Built-in evaluation frameworks (GA)
- Red teaming capabilities (GA)
- Guardrails (partially GA)

These features help:
- Improve output quality
- Reduce hallucination
- Ensure safe and compliant AI usage

---

## 4. Observability

- Tracing for agent execution
- Monitoring for system performance

Note: Some monitoring and tracing features are in preview and should be validated for production use.

---

## 5. Memory & Data Handling

- Memory capabilities are evolving
- Not recommended as sole mechanism for large data

### Recommended approach:
- Use RAG (Retrieval-Augmented Generation)
- External data sources (AI Search, databases)

---

## 6. Governance & Security

- RBAC using Microsoft Entra ID
- Audit logs and compliance support
- Policy-based access control

### Best practice:
- Prefer RBAC over API keys for production environments

---

## 7. Feature Readiness

### GA (Production Ready)
- Model workflows
- Core agent development
- Evaluations and red teaming

### Preview (Validate before production)
- Memory
- Monitoring
- Workflows
- Agent guardrails

---

## 8. Common Pitfalls

- Using preview features in production without validation
- Relying only on API keys instead of RBAC
- Ignoring region availability
- Migrating without fallback strategy

---

## 9. Suggested Enablement Approach

### Phase 1 – Foundations
- Platform overview
- AI lifecycle
- Core services

### Phase 2 – Role-Based Learning
- Agent development
- Evaluation and monitoring
- RAG architectures

### Phase 3 – Architecture & Governance
- AI landing zones
- Security and access models
- Deployment patterns

---

## 10. Hands-on Activities

Recommended practical exercises:

- Build AI agents using Foundry
- Implement evaluation and guardrails
- Design enterprise-ready AI architectures

Focus areas:
- Multi-agent systems
- RAG solutions
- Observability and evaluation
