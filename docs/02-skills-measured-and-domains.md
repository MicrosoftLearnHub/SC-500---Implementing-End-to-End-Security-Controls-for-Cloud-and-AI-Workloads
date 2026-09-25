# 🎯 Skills Measured & Domain Blueprint: Exam SC-500

Official exam skills breakdown as defined by the Microsoft Learn Exam SC-500 Curriculum.

---

## 📈 Domain Weightings Summary Table

| Domain | Weighting | Focus Area |
| :--- | :---: | :--- |
| **Domain 1** | **20–25%** | **Manage Identity, Access, and Governance** |
| **Domain 2** | **25–30%** | **Secure Storage, Databases, and Networking** |
| **Domain 3** | **20–25%** | **Secure Compute (including AI Workloads)** |
| **Domain 4** | **20–25%** | **Manage and Monitor Security Posture** |

---

## 🔍 Detailed Domain Breakdown

### 1. Manage Identity, Access, and Governance (20–25%)
- **Secure access to resources by using Microsoft Entra ID:**
  - Implement and configure Privileged Identity Management (PIM) for Entra roles and Azure resources.
  - Implement Conditional Access policies (including risk-based conditions, device compliance, and session controls).
  - Implement and configure authentication methods, including multifactor authentication (MFA), FIDO2 passwordless, and Microsoft Authenticator.
  - Implement and configure identity for applications, including enterprise applications, app registrations, and Service Principals.
  - Manage OAuth permission grants, consent settings, and permission classifications.
  - Implement and configure user-assigned and system-assigned managed identities for Azure resources.
- **Secure secrets and keys by using Azure Key Vault:**
  - Deploy Key Vault instances and configure soft-delete, purge protection, and diagnostic logging.
  - Configure Key Vault settings, network firewalls, and Private Endpoints.
  - Configure access to Key Vault using Azure Role-Based Access Control (Azure RBAC) vs Key Vault access policies.
  - Manage cryptographic keys, secrets, and certificates, including automated rotation policies.
  - Scan for secrets across VMs and code repos by using Defender Cloud Security Posture Management (Defender CSPM).
  - Implement and configure Microsoft Defender for Key Vault to detect anomalous access patterns.
- **Implement governance to enforce security and regulatory compliance:**
  - Implement and configure security controls using Azure Policy (built-in and custom policy definitions with Audit, Deny, and DeployIfNotExists effects).
  - Evaluate regulatory compliance benchmarks (CIS Microsoft Azure Foundations, NIST SP 800-53, ISO 27001) in Microsoft Defender for Cloud.
  - Implement resource locks (CanNotDelete, ReadOnly) to protect critical security infrastructure.
  - Manage Azure built-in role assignments and create custom Azure RBAC and Microsoft Entra roles.
  - Evaluate and remediate overprivileged access assignments using Azure RBAC and PIM access reviews.
  - Configure security controls for backup protection using Azure Backup security features (immutability, soft delete, multi-user authorization).
  - Implement and configure security controls by using infrastructure as code (Bicep, ARM, Terraform).

---

### 2. Secure Storage, Databases, and Networking (25–30%)
- **Implement security for storage accounts:**
  - Configure Azure Storage security settings (disable shared key access, enforce TLS 1.3, disable public blob access).
  - Configure Azure Storage firewall rules and virtual network service endpoints.
  - Implement Microsoft Defender for Storage threat protection configurations (near real-time malware analysis and sensitive data threat detection).
  - Manage access to storage using Microsoft Entra authorization, shared access signatures (SAS) with stored access policies, and customer-managed keys (CMK).
- **Implement security for databases:**
  - Implement platform-level security configurations in Azure SQL Database and Azure SQL Managed Instance.
  - Configure database auditing, vulnerability assessment, and Transparent Data Encryption (TDE) with customer-managed keys.
  - Configure Microsoft Defender for Databases protection across Azure database services (Azure SQL, Cosmos DB, PostgreSQL, MySQL).
- **Implement security for Azure network services:**
  - Implement and manage Network Security Groups (NSGs) and Application Security Groups (ASGs).
  - Implement and configure network access policies by using Azure Virtual Network Manager (AVNM) security admin rules.
  - Configure security for an Azure Virtual WAN secured virtual hub.
  - Implement and configure security for Virtual Private Network (VPN) and ExpressRoute connections.
  - Implement and configure Microsoft Entra Private Access (Global Secure Access / Security Service Edge).
  - Configure Azure Private Endpoints to secure access to Azure PaaS resources.
  - Configure Azure Private Link services to secure access to proprietary network resources.
  - Implement and configure Azure Firewall (Standard/Premium with TLS inspection and IDPS).
  - Evaluate effective security rules and troubleshoot connectivity using Azure Network Watcher diagnostics.

---

### 3. Secure Compute & AI Workloads (20–25%)
- **Implement security for AI workloads:**
  - Identify overexposure of organizational data in SharePoint and OneDrive.
  - Identify risks related to Microsoft Copilot and AI apps using Microsoft Purview Data Security Posture Management (DSPM) for AI.
  - Enable and configure real-time protection for Microsoft Copilot Studio agents.
  - Implement Conditional Access policies specifically for Microsoft Entra Agent ID.
  - Analyze blast radius and lateral movement for security risks related to Entra Agent ID by using Microsoft Defender XDR.
  - Manage Entra Agent ID access, lifecycle, and permissions.
  - Configure and deploy AI Gateway in Azure API Management for Microsoft Foundry and Azure OpenAI.
  - Enable Defender for AI Service in Cloud Workload Protection within Defender for Cloud.
  - Configure guardrails and content filters for agent security in Microsoft Foundry.
  - Monitor AI security posture using the Data and AI security dashboard in Defender for Cloud.
  - Manage agents in the Microsoft 365 admin center.
- **Implement security for servers and virtual machines (VMs):**
  - Implement and configure Azure Disk Encryption (ADE) with Key Vault keys and Server-Side Encryption (SSE).
  - Plan and implement Azure Bastion for secure, agentless RDP/SSH access.
  - Enable and enforce Just-in-Time (JIT) VM access.
  - Extend security controls to hybrid and multicloud servers using Azure Arc.
  - Onboard servers to Microsoft Defender for Servers (Plan 1 / Plan 2).
  - Configure Defender for Servers settings (vulnerability scanning via Qualys/Defender Vulnerability Management, and Defender for Endpoint EDR).
  - Implement and manage agentless scanning for VMs in Defender for Servers.
  - Configure VM security features (Trusted Launch, Secure Boot, virtual TPM [vTPM], and Confidential Computing).
  - Enforce OS baseline configurations on Azure-managed servers using Azure Machine Configuration.
- **Implement security for application platform services:**
  - Detect misconfigurations and runtime risks in container workloads by using Defender for Containers.
  - Implement and configure security controls for Azure Kubernetes Service (AKS) (Microsoft Entra Workload ID, network policies, Azure RBAC for Kubernetes).
  - Implement and configure security controls for Azure Container Registry (ACR) (quarantine, private endpoints, token-scoped access).
  - Implement and configure security controls for Azure Container Instances (ACI) and Azure Container Apps.
  - Implement and configure security controls for Azure Functions and Logic Apps (managed identities, VNet integration, access restrictions).
  - Implement and configure security controls for Azure App Service (App Service Environment, mutual TLS, IP filtering).
  - Implement and configure Azure Web Application Firewall (WAF) on Azure Front Door and Application Gateway.
  - Implement security policies for back-end API protection by using Azure API Management (JWT validation, IP restrictions, mutual certificate auth).

---

### 4. Manage and Monitor Security Posture (20–25%)
- **Manage security posture by using Defender for Cloud:**
  - Identify security risks and prioritize remediation using Defender Cloud Security Posture Management (Defender CSPM).
  - Evaluate compliance against security frameworks (CIS, NIST, PCI-DSS) by using Defender for Cloud.
  - Enable and configure Defender for Cloud workload protection plans.
  - Connect hybrid cloud and multicloud environments (AWS accounts and Google Cloud projects) to Defender for Cloud.
  - Configure Microsoft Defender Vulnerability Management settings for cloud virtual machines.
  - Discover unprotected external assets and public vulnerabilities using Microsoft Defender External Attack Surface Management (Defender EASM).
- **Implement activity and event collection in Microsoft Sentinel:**
  - Create and architect workspaces in Microsoft Sentinel.
  - Assign Role-Based Access Control (RBAC) roles in Microsoft Sentinel (Sentinel Reader, Responder, Contributor).
  - Implement and use Content Hub solutions and analytical rule templates.
  - Configure and use Microsoft data connectors for Azure resources, Defender XDR, and Entra ID.
  - Implement and configure Syslog and Common Event Format (CEF) event collections using the Azure Monitor Agent (AMA).
  - Implement and configure collection of Windows Security events using Data Collection Rules (DCRs) and Windows Event Forwarding (WEF).
  - Create custom log tables (analytics and basic logs) in the Log Analytics workspace to manage ingestion costs.
  - Implement Automation Rules and SOAR Playbooks (Azure Logic Apps) in Microsoft Sentinel.
  - Implement data retention and archiving policies in Microsoft Sentinel data stores.
  - Query Microsoft Purview Audit events in Defender XDR and Sentinel.
- **Implement Microsoft Security Copilot:**
  - Configure workspaces and provision Security Compute Units (SCUs) for Microsoft Security Copilot.
  - Manage permissions, administrator roles, and user access in Security Copilot.
  - Enable and configure first-party Microsoft plugins (Defender, Sentinel, Purview, Entra, Intune).
  - Enable and configure Microsoft agents and verified custom plugins from the Security Store.
