# AAA Platform Registry

## Authoritative Skill & Agent Registry

This repository is the **official registry** for all Skills and Agents
that participate in the AAA Platform ecosystem.

All entries in this registry are:
- Validated against the AAA Platform Core constitutional schema
- Considered authoritative for execution, billing, and audit
- Subject to automated compliance checks

---

## Relationship to AAA Platform Core

This registry is governed by the following repository:

- **aaa-platform-core** — Constitutional rules and executable schemas

Any Skill or Agent registered here **MUST comply** with the specifications
defined in `aaa-platform-core`.

In the event of conflict, **aaa-platform-core takes precedence**.

---

## What Is Registered Here

This repository contains **declarative manifests only**.

### Registered entities MAY include:
- Skills (atomic executable capabilities)
- Agents (orchestrated compositions of skills)

### This repository MUST NOT contain:
- Runtime code
- Secrets or credentials
- Infrastructure configuration
- Environment-specific implementation details

---

## Directory Structure

```text
registry/
  shared/
    notify.sms.json
  drycleanone/
    order.create.json
  taxend/
    ato.prefill.json

---

## Validation & Enforcement

All registry entries are automatically validated via CI.

Validation includes:

- JSON Schema validation against `aaa-platform-core`
- Rejection of non-compliant manifests
- Enforcement of execution, billing, audit, policy, and error rules

Pull requests that fail validation **WILL NOT** be merged.

---

## Change Process

Adding a New Skill or Agent:

1. Create a new manifest under `registry/`
2. Ensure compliance with the core schema
3. Submit a pull request
4. Pass automated validation


Modifying Existing Entries:

- Backward compatibility MUST be preserved
- Breaking changes REQUIRE a new major version
- Deprecation MUST follow the rules defined in the core specification


---

## Authority

Entries in this repository are **authoritative**.

Runtimes, platforms, and billing systems MUST rely on this registry
as the source of truth for what may be executed within the AAA Platform.

Non-compliant or unregistered entities MUST NOT be executed.

---

## Status

This repository is part of the AAA Platform foundational infrastructure.

Its structure, validation rules, and governance model are expected
to evolve via versioned, reviewed changes.
