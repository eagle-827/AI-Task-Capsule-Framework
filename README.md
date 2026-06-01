## Problem

AI coding agents often:

- modify unrelated files
- introduce architecture drift
- bypass security boundaries
- create hidden technical debt

AI Task Capsule Framework provides a contract-based execution model that constrains AI agents before implementation begins.

# AI Task Capsule Framework

A governance framework for AI-assisted software development.

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

The AI Task Capsule Framework provides a standardized methodology for constraining autonomous coding agents and LLM-driven development tools. It establishes a contract-based execution model designed to preserve repository integrity and ensure human oversight throughout the software development lifecycle.

Designed for maintainers who want to use AI coding agents without sacrificing repository safety, architectural consistency, or human oversight.

---

## Why This Exists

Autonomous AI coding agents introduce specific systemic risks to long-lived codebases:

* **Architecture Drift**
  Agents may prioritize immediate task completion over established architectural patterns, leading to a gradual erosion of system design.

* **Scope Creep**
  Without rigid boundaries, AI agents often refactor unrelated files, introducing unexpected side effects.

* **Unsafe Modifications**
  Direct access to sensitive areas such as database migrations, authentication logic, or environment configurations can lead to data loss or security vulnerabilities.

* **Hidden Technical Debt**
  Bypassing abstractions or introducing inconsistent dependencies creates maintenance burdens that may only become visible during future audits.

* **Uncontrolled Autonomy**
  Modern agents can chain actions together rapidly, making human intervention reactive rather than proactive.

This framework provides a lightweight governance layer between human maintainers and AI agents.

---

## Core Principles

The framework is built on five pillars of governance:

1. **Explicit Scope**
   Every task is confined to a predefined set of allowed files and directories.

2. **Explicit Permissions**
   Capabilities such as reading, writing, executing commands, or modifying schemas are granted per task, not per session.

3. **Explicit Stop Conditions**
   Clearly defined scenarios where the agent must halt execution and return control to a human.

4. **Human Approval Gates**
   Critical state transitions require human verification before being committed or applied.

5. **Risk-Based Execution**
   Tasks are categorized into risk tiers, determining the level of constraint and the type of Capsule required.

---

## Design Goals

The AI Task Capsule Framework is intentionally:

* Tool-agnostic
* Language-agnostic
* Repository-agnostic

The framework is designed to work across different AI coding agents, programming languages, frameworks, and repository structures.

Its goal is not to replace engineering judgment, but to create clear operational boundaries between human maintainers and AI agents.

---

## The Capsule System

A Task Capsule is a structured Markdown document that acts as a runtime contract between a human maintainer and an AI agent.

### Read Capsule

Used for:

* Audits
* Architecture discovery
* Root-cause analysis
* Codebase investigation

### Write Capsule

Used for:

* Feature implementation
* Bug fixes
* Refactoring within approved boundaries
* Documentation updates

### Migration Capsule

Used for:

* Database schema changes
* Security policy updates
* Authentication changes
* Infrastructure modifications

---

## Workflow

The framework follows a sequential, gated progression:

### 1. Read Capsule → Audit & Discovery

The agent investigates the codebase and identifies required changes without modifying state.

### 2. Strategy Review

A human reviews findings, risks, and architectural recommendations.

### 3. Write Capsule → Controlled Implementation

The agent implements the approved strategy within the explicitly defined scope.

### 4. Migration Capsule → High-Risk Change Management

Database or security changes are drafted and reviewed before execution.

### 5. Verification → Human Review

Changes are verified against the original Capsule constraints and Stop Conditions.

### 6. Merge

Approved changes are merged using the repository's standard review process.

---

## Getting Started

To integrate the framework into a repository:

1. Create a governance directory such as:

   ```text
   .workbase/
   ```

   or

   ```text
   .github/ai-governance/
   ```

2. Assign a Risk Tier using:

   ```text
   docs/AI-RISK-TIERS.md
   ```

3. Select the appropriate Capsule template from:

   ```text
   templates/
   ```

4. Complete the Capsule and provide it as the primary instruction to the AI agent.

5. Enforce the Stop Conditions throughout execution.

6. Require human approval before applying high-risk changes.

---

## Roadmap

### v0.1

* Read Capsule
* Write Capsule
* Migration Capsule
* Risk Tiers
* Stop Conditions

### v0.2

* Repository Templates
* GitHub Workflow Examples
* Multi-Agent Guides

### v0.3

* CI/CD Integration Patterns
* Governance Extensions
* Team Collaboration Workflows

---

## Non-Goals

The AI Task Capsule Framework does not attempt to:

* Replace human engineering judgment
* Automatically approve code changes
* Enforce repository policies through software
* Replace existing code review processes
* Eliminate the need for architectural decision-making

Instead, it provides a structured governance layer for human-directed, AI-assisted development.

---

## Project Structure

```text
AI-Task-Capsule-Framework/
│
├── templates/
│   ├── read-capsule.md
│   ├── write-capsule.md
│   └── migration-capsule.md
│
├── docs/
│   ├── AI-RISK-TIERS.md
│   └── STOP-CONDITIONS.md
│
├── LICENSE
└── README.md
```

---

## Contributing

The AI Task Capsule Framework is an evolving open-source project.

Contributions are welcome, including:

* New capsule templates
* Governance patterns
* Multi-agent workflows
* CI/CD integration examples
* Repository safety practices

If you have discovered techniques that improve AI reliability, reduce architecture drift, or strengthen repository governance, please consider contributing.

Pull requests, issues, and discussions are encouraged.

---

## License

Released under the MIT License.

See LICENSE for details.
