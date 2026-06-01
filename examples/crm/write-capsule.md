# WRITE CAPSULE

## Task Goal

Add customer tag management feature.

## Risk Tier

Tier 1

## Scope

Implement customer tagging functionality only.

---

## Allowed Files

- customers/**
- tags/**
- crm/**

---

## Forbidden Areas

- billing/**
- authentication/**
- database/**
- infrastructure/**

---

## Required Contracts

- Existing customer data model must remain unchanged
- No direct database schema modifications
- No authentication changes
- No unrelated refactoring

---

## Verification

Confirm:

- Feature works as specified
- Existing customer records remain intact
- No unrelated files modified
- Tests pass

---

## Stop Conditions

If database schema changes are required:

STOP.

Escalate to a Migration Capsule.

If authentication changes are required:

STOP.

Escalate to human review.
