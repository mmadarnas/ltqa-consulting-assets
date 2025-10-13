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
| **Technical Documentation Language** | **ENGLISH** for all issue names, workflows, fields, and code. | **Standardization and Scalability (Preventing Technical Debt):** This rule prevents **Localization Technical Debt** and ensures processes are consistent with the global industry standard. |
| **Contact Address** | Primary LTQA email is **`hello@letstalkqa.com`**. | **Consistency and Pragmatism:** Maintains brand coherence and was the most stable solution for ensuring professional email flow. |
| **Password Management** | Use of a **Dedicated Online Manager** (e.g., Bitwarden). | **Professional Security:** Required for robust encryption and the secure **sharing of client accesses** in a consulting capacity. |

---

## 3. Quality Toolchain (The QA Environment)

### 3.1. Project Management and Knowledge Strategy

| Tool / Method | Primary Role | Strategic Justification |
| :--- | :--- | :--- |
| **JIRA Software (Free Plan)** | **CORE/STANDARD.** Main tool for issue management and QA workflow. | **Maximum Curricular Value:** Its domain expertise is essential for consulting. The Free Plan is used for functional simulation without incurring costs. |
| **Notion (or Confluence)** | **Knowledge Base (Central Documentation).** Used for housing QA strategy documents, design standards, and *post-mortems*. | **OPEX Management & Flexibility:** Notion is highly flexible and free for single users, aligning with the low-OPEX strategy while demonstrating the need for a central knowledge repository. |
| **Trello / ClickUp** | **Versatility & Comparison Practice.** Used for practicing management styles and generating comparative content. | **Adaptability:** Demonstrates commitment to implementing processes across diverse client platforms beyond Jira. |
| **Xray / Zephyr Scale (TMS)** | **Test Management System (TMS).** Used for managing test cases and traceability within Jira. | **Full Traceability:** Integrating a Jira-native TMS is crucial for demonstrating the ability to link *Stories* to *Test Cases* and *Bugs*, a key consulting deliverable. |

### 3.2. Automation Strategy and Technology Investment

The strategy is defined by a commitment to mastering industry-leading frameworks. This broad approach is an **investment in client adaptability**.

| Tool / Language | Primary Purpose | Strategic Justification |
| :--- | :--- | :--- |
| **Playwright (TypeScript)** | **Primary E2E Framework Investment.** Selected for the LTQA site case study. | **Market Standard & Modernity:** Chosen for superior code safety and Playwright's all-in-one nature. Demonstrates **commitment to modern QA engineering standards.** |
| **Cypress** | **Secondary E2E Framework.** Added to the learning roadmap for comparison and proficiency development. | **Client Adaptability:** Covers both major market solutions to facilitate advising on migrations or managing existing projects. |
| **Python (Selenium/Pytest)**| **Service Layer Versatility.** Added to the learning roadmap for API testing utility scripts and expertise in legacy systems. | **Versatility Requirement:** Shows commitment to integrating QA into diverse engineering environments (Backend Services, Data Science). |
| **Gherkin / Cucumber** | **Behavior-Driven Development (BDD) Methodology.** | **Clarity of Requirements:** Implementation of BDD ensures that test cases are written in a business-readable format, improving collaboration between product, development, and QA. |
| **Postman** | **API Functional Testing.** Used for direct service layer testing and documentation. | **Industry Standard & Accessibility:** Postman is the highest priority tool for quick client demos and API testing documentation. |

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

### Repository Structure Exception: Root Level

The `.github/workflows` directory is intentionally kept in the repository root because GitHub requires it for the Continuous Integration (CI) configuration to function. This is an exception to the rule that all assets must reside in the `/docs` or `/tests` folders.

- **File:** `.github/workflows/playwright.yml`
- **Purpose:** CI/CD configuration for running automated tests on every code push (demonstrating proper DevOps integration).

### .gitignore Governance (Security)

This file prevents sensitive credentials and large output files from being committed to the public repository.