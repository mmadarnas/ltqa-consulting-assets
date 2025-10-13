# 📝 Document: Let's Talk QA Toolchain and Governance Strategy

**Version:** 1.0
**Author:** María José Madarnás Álvarez
**Date:** October 2025

---

## 1. Executive Summary: Toolchain Mission

The objective of this toolchain is to establish a **Digital Governance Structure** and a **Testing Environment** based on the following criteria: **Minimum Operating Cost (OPEX)**, **Maximum Consulting Asset Generation**, and **Adaptability to the International Standard**. Every component is selected to **mitigate business risks** and support high-level consulting services.

---

## 2. Digital Identity and Governance Strategy

| Decision | What is it? | Strategic Justification (The Why) |
| :--- | :--- | :--- |
| **Technical Documentation Language** | **ENGLISH** for all issue names, workflows, fields, and code. | **Standardization and Scalability (Preventing Technical Debt):** English is the *lingua franca* of development. This rule prevents **Localization Technical Debt** (referencing the real-world case study) and ensures processes are consistent with the global industry standard. |
| **Contact Address** | Primary LTQA email is **`hello@letstalkqa.com`**. | **Consistency and Pragmatism:** Maintains brand coherence with EFP and was the most stable solution for ensuring immediate professional email flow. |
| **Brand Voice** | Pronoun **"I"** for blog content and **"Corporate Voice"** for technical documentation. | **Trust and Preparation:** "I" builds confidence as an individual expert. The Corporate Voice in documentation prepares the project for future team growth. |
| **Password Management** | Use of a **Dedicated Online Manager** (e.g., Bitwarden). | **Professional Security:** Required for robust encryption and the secure **sharing of client accesses** in a consulting capacity. |

---

## 3. Quality Toolchain (The QA Environment)

### 3.1. Project Management Tool Justification: Multi-Domain Strategy

A **Multi-Domain Strategy** is adopted for project management to maximize curricular value and adaptability, using Jira as the core.

| Tool | Primary Role | Strategic Justification | Governance URL |
| :--- | :--- | :--- | :--- |
| **JIRA Software (Free Plan)** | **CORE/STANDARD.** Main tool for issue management and QA workflow. | **Maximum Curricular Value:** Its domain expertise is essential for consulting. The Free Plan is used for functional simulation without incurring costs. | `https://letstalkqa.atlassian.net` (or .com) |
| **ClickUp (Free Plan)** | **VERSATILITY/CONTENT.** Used to practice non-QA workflows (e.g., content backlog) and generate comparative articles. | **Adaptability:** Demonstrates the ability to implement processes across different client platforms. | (To be configured) |
| **Trello (Free Plan)** | **SIMPLICITY/PRAGMATISM.** Used for simple task management practice and serving niche clients requiring a low-friction solution. | **Broad Reach:** Allows offering solutions across a wider spectrum of business sizes. | (To be configured) |

### 3.2. Engineering Tools Configuration

| Function | Chosen Tool | Associated Configuration Tasks |
| :--- | :--- | :--- |
| **Issue Types** | **Epic, Story, Task, Bug.** | All four types are used to trace the full complexity of product management and QA. |
| **Version Control** | **GitHub** | **Repository:** `ltqa-consulting-assets`. Email configured locally as `hello@letstalkqa.com` for brand traceability. |
| **Automation Security** | **`.gitignore`** | **CRITICAL:** Implements security rules to prevent credentials (`.env`, `/secrets/`) from being pushed to the public repository. |

---

## 4. Workflow Governance: Traceability Definition

The project uses **two differentiated Workflows** to ensure adequate traceability and accountability.

#### Flow 1: Tasks and Stories (Simple and Linear)

| Status (Jira Column) | Strategic Purpose |
| :--- | :--- |
| **Backlog** | Prioritized ideas or requirements, pending scheduling. |
| **To Do** | The issue has been scheduled and is ready for execution. |
| **In Progress** | Work is actively being executed. |
| **Ready for Review** | Work is completed and **awaits** the QA/Reviewer. (Measures **Wait Time/Bottleneck**). |
| **In Review** | The QA/Reviewer is **actively** testing or validating the issue. (Measures **QA Execution Time**). |
| **Done / Closed** | The issue has been verified, approved, and closed. |

#### Flow 2: Bugs (Verification and Traceability Flow)

This flow demonstrates a mature Bug life cycle.

| Status (Jira Column) | Strategic Purpose |
| :--- | :--- |
| **Backlog / To Do** | The Bug has been reported, validated, and scheduled for correction. |
| **In Progress** | The developer is working on the correction. |
| **Ready for Verification** | The correction code has been deployed and **awaits** re-testing by QA. |
| **In Verification** | QA is **actively** verifying the Bug correction. |
| **Reopened** | **Friction Loop.** QA failed the verification, and the Bug returns to `In Progress` with high priority. |
| **Closed** | The Bug has been verified, the correction is successful, and it is permanently closed. |

#### Resolution Statuses

When closing a Bug, one of these resolutions must be selected to document the reason for closure:

* **Fixed:** The correction was successful and verified by QA.
* **Won't Fix:** Management decision not to fix the defect (documents technical debt).
* **Duplicate:** The Bug was already reported.
* **Cannot Reproduce:** QA could not replicate the defect in the testing environment.

---

## 5. Repository Structure and Commit Governance

The repository **`ltqa-consulting-assets`** is the **Central Methodology Office** and is **Public (MIT Licensed)**.

| Folder Structure | Asset Type | Purpose |
| :--- | :--- | :--- |
| `docs/governance/` | **General Library** | Houses the **`ltqa-toolchain-strategy.md`** and generic governance templates. |
| `docs/projects/ltqa_website/`| **Specific Execution** | Holds the **QA Strategy** and **Test Plan** applied to the LTQA website (your first case study). |
| `tests/e2e/framework_base/` | **Generic Reusable Asset** | Template for your automation framework, ready for clients to download. |
| `tests/e2e/ltqa_website_tests/` | **Specific Execution** | The code that **actually tests** your LTQA website (the portfolio piece). |