# WRITE CAPSULE

> **Framework Directive:** This document is a strict execution contract. The AI agent must operate exclusively within the constraints defined below. Implementation is authorized only for the specified scope.

## 📋 Metadata

* **Task Reference:** [Issue #45, PR #12, Ticket ID, or Internal Reference]
* **Type:** Implementation / Bug Fix / Refactor
* **Risk Tier:** [Tier 1 (Isolated) / Tier 2 (State & Logic)]
* **Human Approval Required:** Yes
* **Context:** [Briefly explain the business logic, feature request, bug report, or design requirements. Reference the previous Read Capsule if applicable.]

---

## 🎯 Task Goal

[Insert a clear, focused implementation objective.]

### Example

Implement a new shopping cart dropdown component using existing UI primitives and connect it to the current application state management system.

---

## 🧭 Scope

### Allowed Files

You are authorized to modify only the following files or directories:

```text
src/components/SpecificComponent.tsx
src/hooks/useSpecificLogic.ts
tests/SpecificComponent.test.tsx
```

Add additional files only with explicit approval.

### Frozen Areas

The following areas are considered frozen and must not be modified:

```text
database/**
infrastructure/**
auth/**
security/**
```

### Forbidden Actions

#### No Unrelated Changes

Do not:

* Refactor unrelated code
* Fix unrelated bugs
* Modify unrelated files
* Perform opportunistic cleanup

#### No Dependency Changes

Do not:

* Install packages
* Remove packages
* Upgrade dependencies
* Modify package manifests

unless explicitly authorized.

#### No Schema Changes

Do not:

* Create migrations
* Modify schemas
* Alter ORM models
* Change database contracts

Use a Migration Capsule instead.

#### No Architecture Drift

Do not:

* Introduce new patterns
* Replace existing architectural decisions
* Introduce competing abstractions
* Create alternative state management systems

#### No Type-Safety Bypass

Do not use:

* any
* @ts-ignore
* @ts-expect-error

unless explicitly approved.

---

## 🏗️ Implementation Requirements

### Required Contracts

Document all implementation constraints.

Examples:

* The component must accept a `className` prop.
* Existing public APIs must remain unchanged.
* Existing data contracts must remain backward compatible.
* Existing user flows must remain functional.

### Execution Plan

1. Define the minimal required change.
2. Implement only within the approved scope.
3. Preserve existing architecture.
4. Verify functionality.
5. Prepare for human review.

---

## ✅ Verification

Before completion, verify:

* [ ] Code compiles successfully.
* [ ] Linting passes.
* [ ] Formatting standards are preserved.
* [ ] Existing tests pass.
* [ ] New functionality behaves as expected.
* [ ] No frozen areas were modified.
* [ ] No unintended files were changed.

---

## 🛑 Stop Conditions & Escalation Rules

Immediately halt execution and request human intervention if any of the following occur.

### 1. Scope Breach Required

The task cannot be completed without modifying files outside the Allowed Files list.

### 2. Dependency Required

A new package, utility, service, or framework dependency is required.

### 3. Migration Required

The task requires:

* Schema changes
* Database migrations
* Authentication modifications
* Security policy changes

A Migration Capsule is required.

### 4. Cascading Failure

Changes cause unrelated:

* Tests
* Type checks
* Builds
* Runtime systems

to fail.

### 5. Architectural Conflict

The requested implementation conflicts with:

* Existing architecture
* Repository conventions
* Security requirements
* Domain boundaries

### 6. Ambiguous Requirements

The implementation goal cannot be completed without making assumptions that are not explicitly approved.

---

## 📤 Deliverable Checklist

Before submitting the final response:

* [ ] Summary of modifications provided.
* [ ] Verification completed.
* [ ] Changed files listed.
* [ ] Risks documented.
* [ ] Human review requested.
* [ ] Ready for merge approval.

---
