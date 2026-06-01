# AI Risk Tiers

This document defines the risk classification system used by the AI Task Capsule Framework.

The purpose of the classification model is to ensure that higher-risk tasks receive stronger governance, stricter constraints, and additional human oversight.

---

# Tier 0 — Read Only

Risk Level: Minimal

Description:

The AI agent is permitted only to inspect, analyze, audit, trace, and report.

Allowed Activities:

* Read files
* Search code
* Analyze architecture
* Generate reports
* Produce implementation plans

Forbidden Activities:

* File modification
* Database changes
* Configuration changes
* Git operations
* Package installation

Examples:

* Root cause analysis
* Architecture audit
* Dependency review
* Security review
* Documentation review

Required Capsule:

* Read Capsule

Human Approval:

* Not required before analysis
* Required before implementation

---

# Tier 1 — Isolated Implementation

Risk Level: Low

Description:

The AI agent may modify a limited and explicitly defined set of files.

Allowed Activities:

* Small feature implementation
* Bug fixes
* UI adjustments
* Localized refactoring

Restrictions:

* No schema changes
* No dependency changes
* No authentication changes
* No infrastructure modifications

Examples:

* Component update
* Styling improvements
* Local utility refactor

Required Capsule:

* Write Capsule

Human Approval:

* Required before merge

---

# Tier 2 — State & Logic

Risk Level: Moderate

Description:

The AI agent may modify business logic, reducers, services, repositories, or state management systems.

Examples:

* State architecture updates
* Complex feature implementation
* Repository layer modifications
* Synchronization logic

Additional Requirements:

* Impact analysis required
* Verification required
* Human review mandatory

Required Capsule:

* Write Capsule

Human Approval:

* Required before implementation

---

# Tier 3 — Data & Infrastructure

Risk Level: High

Description:

Changes that affect data integrity, persistence, synchronization, infrastructure, or deployment.

Examples:

* Database schema updates
* Migration generation
* Storage architecture changes
* Deployment configuration updates

Required Capsule:

* Migration Capsule

Human Approval:

* Mandatory before execution

---

# Tier 4 — Security Critical

Risk Level: Critical

Description:

Changes affecting security boundaries, authentication systems, authorization models, encryption, secrets, or infrastructure security.

Examples:

* Authentication providers
* RBAC systems
* RLS policies
* Secret management
* Security middleware

Required Capsule:

* Migration Capsule

Additional Requirements:

* Security review
* Explicit approval gate
* Independent verification

Human Approval:

* Mandatory

---

# Escalation Rule

If uncertainty exists between two tiers, always choose the higher tier.

When a task crosses multiple tiers, the highest applicable tier governs the entire task.

Safety takes precedence over convenience.

---

Powered by the AI Task Capsule Framework
