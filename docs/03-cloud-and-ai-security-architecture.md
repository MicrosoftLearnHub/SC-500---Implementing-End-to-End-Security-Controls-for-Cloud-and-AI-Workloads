# 🛡️ Deep-Dive Architecture: Securing Cloud and AI Workloads

Exam SC-500 places a major emphasis on securing the intersection of **Enterprise Cloud Infrastructure** and **Modern Generative AI Applications**. This guide breaks down the core architectural patterns tested on the exam.

---

## 1. 🤖 Securing AI Workloads: The 4-Pillar Model

Modern AI security spans four critical operational boundaries:

```
+--------------------------------------------------------------------------+
|                       1. IDENTITY & GOVERNANCE                           |
|       Microsoft Entra Agent ID  •  Workload Conditional Access           |
+--------------------------------------------------------------------------+
                                    │
                                    ▼
+--------------------------------------------------------------------------+
|                       2. DATA GROUNDING & RAG                            |
|       Purview DSPM for AI  •  Sensitivity Labels  •  SharePoint Guard    |
+--------------------------------------------------------------------------+
                                    │
                                    ▼
+--------------------------------------------------------------------------+
|                       3. RUNTIME API GATEWAY                             |
|       Azure APIM AI Gateway  •  Token Throttling  •  Content Safety      |
+--------------------------------------------------------------------------+
                                    │
                                    ▼
+--------------------------------------------------------------------------+
|                       4. POSTURE & THREAT TELEMETRY                      |
|       Defender for AI Service  •  Sentinel  •  Security Copilot          |
+--------------------------------------------------------------------------+
```

### A. Microsoft Entra Agent ID
- **The Concept:** Traditional service principals lack the context of autonomous agents. Entra Agent ID provides first-class identity governance for autonomous AI agents built in Copilot Studio, Azure AI Foundry, or LangChain.
- **Security Controls:**
  - Apply **Conditional Access** targeting Agent IDs to restrict runtime execution to approved tenant infrastructure.
  - Track **blast radius** and lateral movement potential within **Microsoft Defender XDR**.
  - Enforce least-privilege API scope assignments (e.g., granting read access to specific Dataverse tables rather than broad tenant access).

### B. Microsoft Purview Data Security Posture Management (DSPM) for AI
- **The Problem:** RAG (Retrieval-Augmented Generation) exposes overshared data. If an internal SharePoint site has permissions set to 'Everyone except external users', Copilot will retrieve confidential payroll or M&A files for unauthorized users.
- **The Solution:**
  - Purview DSPM for AI audits all SharePoint and OneDrive grounding sources.
  - Automatically identifies overexposed sensitive info types (PII, PCI, Intellectual Property).
  - Enforces **Restricted SharePoint Search** to limit indexing to curated, approved document libraries.

### C. AI Gateway in Azure API Management (APIM)
- **Deployment:** Positioned in front of Azure OpenAI and Microsoft Foundry models.
- **Key Policies:**
  - `llm-token-limit`: Enforces token consumption quotas and rate-limiting per consumer application.
  - `azure-openai-semantic-cache`: Caches identical semantic queries in Redis to reduce API costs and model load.
  - `azure-openai-emit-token-metric`: Publishes real-time token telemetry to Azure Monitor and Sentinel.
  - Real-time integration with **Azure AI Content Safety** to filter prompt injections, jailbreaks, and sensitive data leakage.

### D. Microsoft Defender for AI Service
- Integrated into Defender for Cloud Cloud Workload Protection (CWP).
- Monitors live model endpoints for:
  - Adversarial prompt injection attacks.
  - Data exfiltration attempts via prompt leakage.
  - Excessive token consumption attacks (Denial of Wallet).

---

## 2. 🌐 Zero Trust Network Architecture for Cloud & Hybrid
Exam SC-500 tests modern network designs that replace legacy perimeter firewalls with identity-driven controls:

1. **Microsoft Entra Private Access:**
   - Routes traffic via the Global Secure Access client directly to private applications.
   - Evaluates device health, user risk, and MFA on every single connection attempt.
   - Completely eliminates public inbound listening ports on edge firewalls.
2. **Azure Virtual Network Manager (AVNM):**
   - Centrally manages network security across hundreds of subscriptions.
   - **Security Admin Rules** override local NSGs, preventing development teams from accidentally opening SSH (22) or RDP (3389) to the Internet.
3. **Azure Firewall Premium:**
   - Deployed in the Hub of a Hub-and-Spoke or Virtual WAN topology.
   - Terminates TLS with certificates stored in Azure Key Vault for deep TLS Inspection.
   - Evaluates outbound traffic against 60,000+ known signatures in its IDPS engine.

---

## 3. 🔍 Posture Management: Defender CSPM & External Attack Surface Management
- **Defender CSPM Attack Path Analysis:**
  - Evaluates multi-cloud infrastructure as a unified graph.
  - Identifies multi-hop exploitation chains: e.g., Internet -> VM with unpatched CVE -> Overprivileged Managed Identity -> Sensitive Azure SQL Database.
- **Defender EASM (External Attack Surface Management):**
  - Discovers unknown internet-facing public assets from the outside in without credentials or agents.
