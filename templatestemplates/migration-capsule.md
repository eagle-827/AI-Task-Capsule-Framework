# MIGRATION CAPSULE

> **Framework Directive:** This document governs high-risk operations. The AI agent must operate under extreme caution. Data loss prevention, security integrity, and strict idempotency are the highest priorities.

## 📋 Metadata

- **Task Reference:** [Issue #45, PR #12, Ticket ID, or Internal Reference]
- **Type:** Database Schema / Authentication / Security Policy / Infrastructure
- **Risk Tier:** [Tier 3 (High Risk) / Tier 4 (Extreme Risk)]
- **Human Approval Required:** Yes
- **Context:** [Explain the business or technical requirement driving this structural change. Reference specific architectural decisions and previous Read/Write Capsules if applicable.]

---

## 🎯 Task Goal

[Insert the exact structural change required.]

### Example

Implement a soft-delete mechanism for the `users` table including a new `deleted_at` column, supporting RPC functions, and updated Row Level Security (RLS) policies.

---

## ⚠️ Human Approval Gate

Execution of generated artifacts against any environment requires explicit human review and approval.

### Authorized Actions

The AI agent may:

- Generate migration drafts
- Draft SQL scripts
- Review schemas
- Analyze security implications
- Produce verification plans
- Produce rollback plans

### Unauthorized Actions

The AI agent must not:

- Execute migrations
- Apply infrastructure changes
- Deploy to any environment
- Connect to production systems
- Perform destructive operations

without explicit human approval.

---

## 🧭 Scope

### Allowed Files

You are authorized to modify or create only the following files or paths:

```text
supabase/migrations/[TIMESTAMP]_descriptive_name.sql
prisma/migrations/**
infrastructure/terraform/**
```

Add additional files only with explicit approval.

### Frozen Areas

The following systems rely on established contracts and must not be modified as a side effect of this task:

```text
auth/**
security/**
production/**
```

Examples:

- Provider-managed authentication tables
- Existing security invariants
- Established RLS ownership boundaries
- Production infrastructure configurations

### Forbidden Actions

#### No Destructive Operations

Do not use:

```sql
DROP TABLE
DROP COLUMN
TRUNCATE
```

unless explicitly authorized.

#### No Unsafe Deletes

Do not execute:

```sql
DELETE FROM table_name
```

without tightly constrained and reviewed WHERE clauses.

#### No Security Weakening

Do not:

- Broaden SELECT access
- Broaden INSERT permissions
- Broaden UPDATE permissions
- Broaden DELETE permissions
- Weaken authentication requirements

#### No Production Execution

Do not connect to, modify, or execute commands against production environments.

---

## 🏗️ Required Migration Contracts

### Safety Requirements

#### Idempotency

All structural changes must be safely repeatable.

Examples:

```sql
CREATE TABLE IF NOT EXISTS
CREATE OR REPLACE FUNCTION
CREATE POLICY IF NOT EXISTS
```

#### Safe Defaults

Any new column added to populated tables must:

- Be nullable

OR

- Provide a valid DEFAULT value

#### Non-Blocking Operations

Use online or concurrent operations whenever supported by the underlying database.

#### Foreign Key Safety

Prefer:

```sql
ON DELETE RESTRICT
ON DELETE SET NULL
```

over:

```sql
ON DELETE CASCADE
```

unless explicitly required.

#### Backward Compatibility

Existing consumers must continue functioning throughout migration rollout whenever possible.

---

## 🛠️ Implementation Plan

1. Draft the structural changes.
2. Draft associated policies or functions.
3. Validate compatibility with existing contracts.
4. Produce verification scripts.
5. Produce rollback scripts.
6. Prepare migration package for human review.

---

## 🔐 Security Review

Verify that the migration:

- Does not weaken access controls.
- Does not expose sensitive information.
- Does not bypass authentication requirements.
- Does not violate least-privilege principles.
- Does not expand user permissions unexpectedly.
- Does not introduce privilege escalation paths.

Document all security implications.

---

## ✅ Verification & Rollback

### Verification Plan

Provide a safe verification strategy.

Requirements:

- Prefer read-only validation.
- Query metadata tables and system catalogs.
- Validate schema shape.
- Validate constraints.
- Validate indexes.
- Validate policies.
- Validate permissions.

### Verification Script

When testing mutations locally:

```sql
BEGIN;

-- verification queries

ROLLBACK;
```

No permanent test data should remain after verification.

### Rollback Considerations

Provide a DEV ONLY rollback plan that reverses the migration.

Requirements:

- Rollback must be clearly marked.
- Rollback must not execute automatically.
- Rollback assumptions must be documented.
- Data-loss risks must be explicitly disclosed.

---

## 🛑 Stop Conditions & Escalation Rules

Immediately halt drafting and request human intervention if any of the following occur.

### 1. Naming Collision

The requested object already exists and conflicts with the intended design.

### 2. Data Loss Risk

The migration requires:

- Dropping populated columns
- Dropping populated tables
- Destructive data transformation
- Irreversible schema changes

### 3. Security Conflict

The requested change would:

- Weaken security boundaries
- Violate RLS principles
- Bypass authentication controls
- Expose protected data

### 4. Tooling Limitation

The required operation is unsupported by the current:

- Database engine
- ORM
- Infrastructure tooling
- Platform capabilities

### 5. Scope Expansion

Additional files, services, repositories, or environments are required beyond the approved scope.

### 6. Architectural Conflict

The migration violates:

- Existing contracts
- Domain boundaries
- Security architecture
- Repository governance rules

---

## 📤 Deliverable Checklist

Before submission:

- [ ] Migration draft completed.
- [ ] Verification plan included.
- [ ] Verification script included.
- [ ] Rollback plan included.
- [ ] Security review completed.
- [ ] Risks documented.
- [ ] Scope compliance verified.
- [ ] Human review requested.
- [ ] Ready for approval.

---

AI Task Capsule Framework • Migration Capsule Template
