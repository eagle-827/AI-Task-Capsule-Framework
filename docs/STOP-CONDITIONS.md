# Stop Conditions

This document defines the mandatory halt conditions used by the AI Task Capsule Framework.

Whenever one of the following conditions is encountered, the AI agent must immediately stop execution and return control to a human reviewer.

---

# 1. Scope Boundary Violation

The requested task cannot be completed within the Allowed Files list.

Examples:

* Additional files are required.
* Hidden dependencies are discovered.
* A broader refactor becomes necessary.

Required Action:

STOP and request scope expansion approval.

---

# 2. Architectural Conflict

The requested implementation conflicts with existing architecture, design patterns, or repository conventions.

Examples:

* Existing state management would be bypassed.
* Duplicate infrastructure would be introduced.
* Established abstractions would be violated.

Required Action:

STOP and request architectural review.

---

# 3. Security Risk

A security issue is discovered.

Examples:

* Credential leakage
* Exposed secrets
* Authentication bypass
* Authorization weakness
* Unsafe API exposure

Required Action:

STOP immediately and escalate.

---

# 4. Migration Requirement

The task unexpectedly requires database or infrastructure changes.

Examples:

* New tables required
* Schema updates required
* Storage changes required

Required Action:

STOP and create a Migration Capsule.

---

# 5. Dependency Requirement

The task requires a package, framework, library, or service that is not already approved.

Examples:

* New npm package
* New Python dependency
* New external service

Required Action:

STOP and request approval.

---

# 6. Verification Failure

The implementation cannot be verified successfully.

Examples:

* Build failure
* TypeScript failure
* Test failure
* Lint failure

Required Action:

STOP and report findings.

---

# 7. Ambiguous Requirements

The task goal is unclear or open to multiple interpretations.

Examples:

* Missing acceptance criteria
* Conflicting requirements
* Incomplete specification

Required Action:

STOP and request clarification.

---

# 8. Data Integrity Risk

The change may result in data loss, corruption, or irreversible mutation.

Examples:

* Delete operations
* Migration risks
* Data transformation uncertainty

Required Action:

STOP and require explicit approval.

---

# 9. Human Approval Gate

The task enters a tier that requires human authorization.

Examples:

* Tier 2 implementation
* Tier 3 migration
* Tier 4 security changes

Required Action:

STOP until approval is received.

---

# Golden Rule

If there is uncertainty regarding safety, scope, architecture, data integrity, or security:

STOP.

Do not guess.

Do not assume.

Do not continue.

Return control to a human reviewer.

---

Powered by the AI Task Capsule Framework
