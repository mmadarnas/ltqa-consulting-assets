# 📄 QA Governance and Strategy Manual (LTQA)

**Version:** 2.6 (Final Operational and Strategic Framework)
**Author:** [Tu Nombre]
**Date:** October 2025

---

### 1. Executive Summary & Philosophy

The objective of this QA framework is to establish a **Digital Governance Structure** that enables high-level consulting and personal projects with **minimal operating cost (OPEX)** while ensuring **full traceability** and **international standard compliance**.

Our QA philosophy emphasizes **Collaborative Quality (Shift-Left)** and **Data-Driven Decisions**, ensuring quality is integrated early and is transparent to all stakeholders.

---

### 2. Digital Identity & Governance Foundation

| Decision | Strategic Justification (The *Why*) | Standard |
| :--- | :--- | :--- |
| **Technical Documentation Language** | **ENGLISH** (for all code, issue names, and core documentation). | **Global Standard:** Ensures consistency and removes language barriers common in international tech teams. |
| **Project Management Core** | **JIRA Software (Free Plan)** | **Industry Standard:** Domain expertise in the most common issue tracker, ideal for smooth client integration. |
| **Knowledge Base** | **Docusapiens** (Hosting) and **Notion/Confluence** (Drafting) | **Transparency:** Demonstrates the ability to deploy an accessible, organized, and version-controlled documentation solution. |
| **Source Code & CI/CD** | **GitHub** & **GitHub Actions** | **DevOps Compliance:** Essential for code sharing, version control, and automating the software delivery process (CI/CD). |

### 2.1 Investment in Versatility and Adaptability

LTQA maintains proficiency in alternative platforms to ensure full adaptability to client requirements, proving that **the consultant adapts to the client's stack.**

| Platform / Technology | Purpose of the Investment | Application Practice (CV Value) |
| :--- | :--- | :--- |
| **Project Management** | **ClickUp, Trello** | Practice migrating workflows to demonstrate the **transferability of the QA Methodology** across different business tools. |
| **Test Management** | **TestRail, Zephyr, Testmo, Qase** | Maintain architectural knowledge to strategically **advise clients** on the best TMS solution based on their existing stack and budget. |
| **CI/CD Alternative** | **GitLab CI, Jenkins, Azure DevOps** | Demonstrate the ability to integrate automation frameworks (Karate/Playwright) into diverse deployment pipelines. |
| **Languages** | **Python, TypeScript** | Continuous learning to ensure seamless integration of QA with diverse backend architectures. |

### 2.2 QA Culture and Leadership Principles

| Principle | Justification |
| :--- | :--- |
| **Quality as Shared Responsibility** | Fosters the *Shift-Left* mindset where quality is owned by the entire team, from product design to DevOps delivery. |
| **Continuous Learning & Documentation** | Every pipeline failure or incident analysis is documented in the **Knowledge Base (Docusapiens)** to drive process improvement and prevent recurrence. |

### 2.3 Repository and Version Control Standards

The repository **`ltqa-consulting-assets`** is the **Central Methodology Office** and is **Public (MIT Licensed)**.

| Folder Structure | Asset Type | Purpose |
| :--- | :--- | :--- |
| `docs/governance/` | **General Library** | Houses the **Toolchain Strategy** and governance templates (source files for Docusapiens). |
| `docs/projects/[PROJECT_NAME]/` | **Project-Specific Strategy** | Holds the tailored QA Strategy and Test Plan for the specific client project. |
| `tests/e2e/framework_base/` | **Generic Reusable Asset** | Template for the automation framework, ready for client adaptation. |
| `tests/e2e/[PROJECT_NAME]_tests/` | **Specific Execution** | The executable code and test cases for the specific client project. |

#### CI/CD Directory Exception: Root Level

The `.github/workflows` directory is intentionally kept in the **repository root** (as required by GitHub) for the Continuous Integration (CI) configuration to function. This is an exception to the rule that all other assets must reside in the `/docs` or `/tests` folders.

#### .gitignore Governance (Security)

The `.gitignore` file is used to prevent sensitive credentials (e.g., API keys, environment variables), large output files, and framework dependencies (`node_modules`) from being committed to the public repository, ensuring security and efficiency.

---

### 3. The Quality Tool Stack (Technology Foundation)

| Category | Tool (Rationale) | Core Functionality Demonstrated (CV Value) |
| :--- | :--- | :--- |
| **Test Management** | **Xray Test Management** | **Non-negotiable Trazability:** Used for planning, execution, and coverage reporting *natively* within Jira. |
| **Primary UI Automation**| **Playwright (TypeScript)** | **Speed and Reliability:** Chosen for its superior performance in testing complex user interfaces, reducing testing time. |
| **API Automation** | **Karate DSL** and **Postman** | **Karate:** Robust BDD for simple, maintainable API automation. **Postman:** Essential for quick API exploration and debugging. |
| **Testing Environment** | **BrowserStack** (Trials/Open Source) | **Scalability:** Used to demonstrate competency in executing *cross-browser/device* tests via Cloud services. |
| **Database Verification** | **SQL** | Essential skill for validating data integrity directly in the database after service layer interactions. |

---

### 4. QA Workflow and Traceability Standard (The *How*)

This section details the operational flow, ensuring full traceability from Requirement to Defect closure.

#### 4.1 Traceability Flow (Requirement $\rightarrow$ Execution)

1.  **Requirement $\rightarrow$ Design (Jira/Xray):** Every **User Story** in Jira must be linked to a minimum of one **Xray Test**.
2.  **Automation Code (GitHub):** Automation scripts are stored and versioned in **GitHub**.
3.  **Execution and CI/CD (GitHub Actions):** Testing is integrated into the CI pipeline.
4.  **Reporting (Xray API - Critical Step):** The CI/CD pipeline is configured to **automatically send test results** (e.g., JUnit reports) from the code execution back to Xray, instantly updating the Jira dashboard. *This step closes the traceability loop.*

#### 4.2 Flow 1: Tasks and User Stories

This flow is used for implementing new features and defining the expected hand-off between development and QA.

| Status (Jira Column) | Explanation | Strategic Purpose |
| :--- | :--- | :--- |
| **Backlog** | Ideas or requirements prioritized, pending **planning and commitment** for a *sprint*. | Input for Sprint Planning. |
| **To Do** | The issue has been **planned and committed** to the current sprint/iteration, ready for execution by a developer. | Developer's queue. |
| **In Progress** | Work is actively being executed (coding). | Measures **Development Time**. |
| **Ready for Review** | Work is completed by the developer and **awaits** the QA/Reviewer. | Measures **Wait Time/Bottleneck** before QA engagement. |
| **In Review** | The QA/Reviewer is **actively** testing or validating the issue. | Measures **QA Execution Time** for the feature. |
| **Done / Closed** | The issue has been verified, approved, and closed. | Verified and complete. |

#### 4.3 Flow 2: Defect Management

We utilize a mature bug life cycle, incorporating a **Triage** step to validate defects before they enter the development stream.

| Status (Jira Column) | Explanation | Strategic Purpose |
| :--- | :--- | :--- |
| **Backlog** | New Bug has been reported and is awaiting initial assessment. | New input queue. |
| **Triage / Validation** | **Initial screening is actively being performed** by the QA Lead or PO to confirm validity, priority, and completeness of information. | **Gated Entry:** Ensures development time is not wasted on invalid/duplicate issues. |
| **Awaiting Info** | The Bug is valid but requires more data (e.g., reproduction steps, environment details) from the reporter before it can be actioned by the developer. | **Process Control:** Prevents Bugs lacking details from entering the active workflow. |
| **To Do** | The Bug has been validated and prioritized. It is ready for assignment to a developer. | Developer's prioritized queue. |
| **In Progress** | The developer is working on the correction. | Active fix. |
| **Ready for Verification** | The correction code has been deployed to the QA environment and **awaits** re-testing by QA. | Hand-off to QA. |
| **In Verification** | QA is **actively** verifying the Bug correction. | Active QA verification cycle. |
| **Reopened** | **Friction Loop.** QA failed the verification, and the Bug returns to `In Progress` with high priority. | Highlights process failure / code quality issue. |
| **Closed** | The Bug has been verified and permanently closed. | Complete fix. |

**Resolution Statuses (for Closure):** When closing a Bug, one of these resolutions must be selected to clearly document the reason for closure:

| Resolution Status | Explanation | Strategic Implication |
| :--- | :--- | :--- |
| **Fixed** | The correction was successful and verified by QA. | The intended resolution path. |
| **Won't Fix** | Management decision not to fix the defect (e.g., low priority, complexity). | **Documents Technical Debt**; requires clear sign-off. |
| **Duplicate** | The Bug was already reported. | Efficiency metric; prevents redundant work. |
| **Cannot Reproduce** | QA could not replicate the defect in the testing environment (often leads to the Bug moving back to **Awaiting Info**). | Requires further investigation into environmental stability or replication steps. |

#### 4.4 Management of Test Environments

| Environment (EXAMPLE) | Purpose | Deployment Rules |
| :--- | :--- | :--- |
| **Development** | Unit/early integration testing. | Continuous deployment (CD) from the development branch. |
| **Staging/QA** | **Full Regression and Xray Test Execution.** | Deployment is controlled and stable. **All Xray Test Plans are executed here.** |
| **Production** | Monitoring and Canary/Smoke Testing. | Controlled deployment only after Xray metrics approval. |

---

### 5. Technical Standards (Implementation)

#### 5.1 Automation Code Standards

| Aspecto | LTQA Standard |
| :--- | :--- |
| **Primary Language** | **JavaScript (JS)** and **TypeScript (TS)**. *This is foundational for UI automation (Playwright/Cypress).* |
| **API Framework** | **Karate DSL** is used for its simplified BDD syntax. |
| **Database Verification** | Basic **SQL** queries are utilized within automation scripts to verify data integrity. |

#### 5.2 Governance Quality Metrics

We monitor key metrics to ensure data-driven decision-making (reflected in the Jira/Xray Dashboard).

| Metric | Purpose | Monitoring Tool |
| :--- | :--- | :--- |
| **Requirement Coverage (%)** | Measures the % of requirements covered by passing tests. **This is our Go/No-Go Decision.** | Xray Gadgets |
| **Automation Ratio (%)** | Measures the % of active test cases that are automated. **Measures QA maturity.** | Xray / Jira Calculation |
| **Defect Removal Efficiency (DRE)** | Measures the effectiveness of QA in finding defects before deployment. | Jira (Bug Workflow) |
| **Defect Leakage (Fuga de Defectos)** | Measures the amount of defects found in Production. **Measures process quality.** | Jira (Bug Workflow) |