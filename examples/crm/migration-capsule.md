# MIGRATION CAPSULE

## Task Goal

Add customer activity tracking table.

## Risk Tier

Tier 3

Human approval required.

---

## Scope

Create migration files only.

Do not execute migrations.

---

## Allowed Files

- migrations/**

---

## Forbidden Areas

- app/**
- components/**
- customers/**
- authentication/**
- infrastructure/**

---

## Required Contracts

- RLS must be enabled
- Audit fields required
- Rollback script required
- Existing customer data must remain intact

---

## Verification

Must verify:

- Migration syntax is valid
- Rollback migration exists
- RLS policies included
- No destructive operations present

---

## Stop Conditions

If existing customer data may be modified:

STOP.

Escalate to human review.

If data loss risk exists:

STOP.

Escalate to human review.

If authentication changes are required:

STOP.

Create a separate Migration Capsule.
