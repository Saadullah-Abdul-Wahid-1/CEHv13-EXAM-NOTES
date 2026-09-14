# Cloud Computing Security

## 📌 Introduction
Cloud computing shifts infrastructure and platform responsibilities to a provider, but security
is always **shared** — understanding exactly who secures what (per service model) is one of the
most heavily tested and practically important cloud security concepts.

---

## 🎯 Objectives
- Understand the Shared Responsibility Model across IaaS/PaaS/SaaS.
- Identify common cloud misconfigurations and their impact.
- Learn cloud-specific attack vectors (SSRF to metadata, account hijacking).
- Apply IAM, encryption, and monitoring best practices.

---

## 🔐 Shared Responsibility Model
| Service Model | Provider Responsibility | Customer Responsibility |
|---|---|---|
| **IaaS** | Physical infra, virtualization/hypervisor | Guest OS patching, app security, IAM, data |
| **PaaS** | Infra + runtime/platform | Application code, data, access config |
| **SaaS** | Nearly the entire stack | Data, user access management |

---

## 🔍 Common Cloud Risks
- **Misconfigured storage** (e.g., public S3 buckets) – one of the most common breach causes.
- **VM/hypervisor escape** – breaking out of an isolated VM to the host or co-located VMs.
- **SSRF to instance metadata service** – leaking temporary IAM credentials via a vulnerable app.
- **Leaked API keys/secrets** in public code repositories.
- **Cloud account hijacking** via weak/reused credentials.
- **Container/orchestration misconfiguration** (e.g., Kubernetes RBAC issues).

---

## 🧰 Tools & Practices
- **CSPM (Cloud Security Posture Management)** tools – continuously scan for misconfigurations.
- Cloud-native IAM policy analyzers.
- **SOC 2** audit reports – common way providers demonstrate independently audited controls.

---

## 🧪 Hands-on Labs
- **Lab 1: Bucket Permission Audit** – review a lab storage bucket's ACL/policy for unintended
  public access.
- **Lab 2: IAM Least-Privilege Review** – audit a set of IAM roles/policies for over-broad
  permissions.
- **Lab 3: Metadata Service Exposure** – identify whether a lab web app is vulnerable to SSRF
  reaching the instance metadata endpoint.
- **Lab 4: Secret Scanning** – run a secret-scanning tool against a sample repository to find
  leaked keys.

---

## 🛡️ Defensive Countermeasures
- Apply least-privilege IAM roles/policies; enforce MFA for all accounts.
- Disable public access on storage by default; audit permissions regularly.
- Encrypt data at rest and in transit.
- Never commit API keys/secrets to source control; use secret managers.
- Monitor for anomalous login activity and use CSPM for continuous configuration checks.

---

## 📄 Reporting
- Service model in scope and the corresponding shared-responsibility boundary.
- Misconfigurations found (storage, IAM, network) with evidence.
- Business impact of each finding.
- Remediation: least privilege, encryption, CSPM adoption.

---

## ⚠️ Disclaimer
This content is for **educational and authorized security testing only**, performed only against
cloud environments/accounts you own or have explicit permission to test.
