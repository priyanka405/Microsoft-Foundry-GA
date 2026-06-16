# Microsoft Foundry – General Availability (GA) Overview

> **Reference:** [New Microsoft Foundry portal general availability overview](https://learn.microsoft.com/en-us/azure/foundry/concepts/general-availability)

---

## 1. What is Microsoft Foundry (GA)?

The new Microsoft Foundry portal is now **Generally Available (GA)**. This milestone marks a shift from pilot-focused usage to **secure, reliable, enterprise-ready production usage** for core scenarios.

Foundry is designed for teams that need to build, deploy, and operate AI systems at scale, with governance, security, and operational controls integrated throughout the lifecycle.

### Core Lifecycle:
**Discover → Build → Operate**

---

## 2. Key Terms

| Term | Definition |
|------|-----------|
| **GA** | Generally available features supported for production use |
| **Preview** | Features that are not yet generally available |
| **Foundry projects** | Workspace containers that organize your AI assets, deployments, and agent configurations within the new Foundry portal |
| **AOAI** | Azure OpenAI resources and workflows |

---

## 3. What GA Means for Customers

At GA, the new Microsoft Foundry portal provides:

- **Production-ready core platform** with validated end-to-end core scenarios
- **Enterprise capabilities** including RBAC, audit logs, compliance controls, monitoring, alerting, and virtual network integration
- **Governed lifecycle consistency** across the portal, APIs, SDKs, CLI, and developer tools
- **Defined GA scope** for Foundry projects, with out-of-scope capabilities continuing in Foundry (classic) portal

> **Note:** Foundry supports API key authentication for most areas. **Exceptions:** evaluations, dataset tab, Content Understanding, agents, and workflows require **Microsoft Entra ID** authentication.
>
> For governance-sensitive production workloads, use **Microsoft Entra ID with RBAC**. API key-based access is available but doesn't provide the same role-based permissions.

---

## 4. GA Scope by Project Type

| Project Type | Status |
|-------------|--------|
| **Foundry projects** | ✅ Fully supported at GA with end-to-end coverage for model deployment, agent development, and operations |
| **Standalone Azure OpenAI resources** | ❌ Not supported in the new Foundry portal — continue using Foundry (classic) portal or upgrade to a Foundry project |
| **Hub-based projects (classic)** | ❌ Not supported in the new Foundry portal — see migration guidance |

> Confirm that your target regions support the models and features you need. See [Feature availability across cloud regions](https://learn.microsoft.com/en-us/azure/foundry/reference/region-support).

---

## 5. Core Scenarios at GA

| Scenario | Details |
|----------|---------|
| **Model core flows** | Discover models, deploy models, run inference, manage deployments, and transition to agent-based workflows |
| **Agent development** | Build agents and integrate evaluations, tracing, monitoring, red teaming, and fine-tuning where supported |
| **Operate experiences** | Manage agents and assets, enforce policies, and manage quota and administration features where supported |

---

## 6. Feature Readiness at GA

| Area | Feature | Status |
|------|---------|--------|
| Home | All | ✅ GA |
| Discover | Overview | ✅ GA |
| Discover | Model | ✅ GA |
| Discover | Instant Models | ⚠️ Preview |
| Discover | Tools | ✅ GA |
| Discover | Solution Templates | ✅ GA |
| Discover | Search | ✅ GA |
| Discover | Ask AI | ⚠️ Preview |
| Build | Agents (core) | ✅ GA |
| Build | Agents — Voice Live | ⚠️ Preview |
| Build | Agents — traces in agent builder | ⚠️ Preview |
| Build | Workflows | ⚠️ Preview |
| Build | Models | ✅ GA |
| Build | Tracing (including Trace Replay) | 🔶 Partial GA (GA for prompt agents; Preview for hosted, workflow and external agents) |
| Build | Tracing VNet | ⚠️ Preview |
| Build | Optimization (cluster analysis) | ⚠️ Preview |
| Build | Fine-tuning | ✅ GA |
| Build | Tools | ✅ GA (check individual tool labels) |
| Build | Knowledge (Foundry IQ) | 🔶 Partial GA (API-level GA; portal access remains Preview) |
| Build | Data (core) | ✅ GA |
| Build | Data — stored completions | ⚠️ Preview |
| Build | Evaluations | ✅ GA (some evaluators and features are Preview; check individual evaluator labels) |
| Build | Memory | ⚠️ Preview |
| Build | Guardrails — Models | ✅ GA |
| Build | Guardrails — Agents | ⚠️ Preview |
| Build | Guardrails — Controls and intervention | ⚠️ Preview |
| Build | Monitoring | ⚠️ Preview |
| Build | Red teaming | ✅ GA |
| Build | AI services speech playgrounds | ✅ GA |
| Operate | Overview | ⚠️ Preview |
| Operate | Assets | ⚠️ Preview |
| Operate | Compliance | ⚠️ Preview |
| Operate | Quota | ✅ GA |
| Operate | Admin | ✅ GA |
| Docs | All | ✅ GA |

---

## 7. Unsupported at GA

The following are **out of scope** for the new Foundry portal at GA and require the classic portal:

- Standalone Azure OpenAI or other single-service resources not connected to a Foundry project
- Assistant creation and authoring in the new Foundry portal
- Listing AOAI evaluation files as datasets for upgrade workflows
- Audio playground
- AI service fine-tuning (e.g., Speech or Vision custom model training) — model fine-tuning through Foundry projects is GA
- Content Understanding
- Prebuilt prompts in video playground
- Adding data directly from the Data tab (users can add data during agent creation workflows)
- Private/Government cloud support for the new Foundry portal

➡️ These require use of **Foundry (classic)**

---

## 8. Prerequisites (Before Production)

Before standardizing on GA features for production:

- Understand your required scenarios across model deployment, agent development, and operations
- Identify any current dependencies on preview-only or classic portal experiences
- Define your organization policy for using only GA capabilities in production
- Review migration guidance for existing Azure OpenAI and Foundry (classic) portal workloads
- Confirm required role assignments for your teams and service identities
- Define how your organization restricts preview feature access in production environments

---

## 9. Validate GA-Only Usage

Before production rollout, validate the following:

- Required scenarios in your workload map to capabilities marked **GA** in the [feature readiness table](#6-feature-readiness-at-ga)
- Dependencies on **Preview** features are documented and approved for non-production use only
- Role assignments and authentication model are aligned to your governance policy, especially where API keys are used
- Target-region model and feature availability are confirmed
- Teams supporting migration scenarios have a documented path between the new Foundry portal and Foundry (classic) portal workflows

---

## 10. Common Rollout Pitfalls

Avoid:

- Treating **Preview features as production dependencies** without explicit approval — check the feature readiness table for current status
- Assuming **API key authentication** provides the same governance granularity as Entra ID with RBAC
- **Skipping region availability validation** for required models and services
- Migrating assistants or AOAI workflows **without a documented fallback path** in Foundry (classic) portal
- Assuming all GA features work **behind a virtual network** — some features (including Traces and Workflow Agents) don't yet fully support network isolation; Hosted Agents require public access to Azure services

---

## 11. FAQ

**What does general availability mean for Microsoft Foundry?**
GA means the new Foundry portal is supported for production use for defined core scenarios in Foundry projects, with validated end-to-end experiences, enterprise support readiness, and operational reliability commitments.

**Which projects are supported at GA?**
Foundry projects with end-to-end coverage for core scenarios. Other resource types can continue in the Foundry (classic) portal where needed.

**Are all Foundry features GA?**
No. GA covers validated core experiences and required enterprise features. Some capabilities remain in public preview.

**What is the experience for existing Azure OpenAI users?**
Existing Azure OpenAI resources can continue to use the classic portal for unsupported workflows while you plan your upgrade to Foundry projects.

**Are assistants supported in Foundry projects?**
The new Foundry portal supports Agents v2. Existing assistants and v1 agents aren't supported. To use or edit assistants, continue using Foundry (classic) portal until a migration path is available.

**Can customers use Foundry GA through APIs and developer tools?**
Yes. Foundry provides support across portal, APIs, SDKs, and CLI for GA-supported scenarios.

**Is GA the final state of Microsoft Foundry?**
No. GA is a production milestone, not an endpoint. Microsoft continues to expand workflow authoring, operations, and governance capabilities based on customer feedback and production usage.

---

## 12. Next Steps

- [What is Microsoft Foundry?](https://learn.microsoft.com/en-us/azure/foundry/what-is-foundry)
- [Upgrade Azure OpenAI to Microsoft Foundry](https://learn.microsoft.com/en-us/azure/foundry/how-to/upgrade-azure-openai)
- [Migrate from hub-based to Foundry projects](https://learn.microsoft.com/en-us/azure/foundry-classic/how-to/migrate-project)
- [Microsoft Foundry SDKs](https://learn.microsoft.com/en-us/azure/foundry/how-to/develop/sdk-overview)
- [Role-based access control for Microsoft Foundry](https://learn.microsoft.com/en-us/azure/foundry/concepts/rbac-foundry)
- [Configure network isolation for Microsoft Foundry](https://learn.microsoft.com/en-us/azure/foundry/how-to/configure-private-link)
- [Feature availability across cloud regions](https://learn.microsoft.com/en-us/azure/foundry/reference/region-support)
