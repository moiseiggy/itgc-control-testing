# ITGC Control Testing Skill

> A structured Claude Skill that generates audit-ready ITGC documentation
> from technical evidence — logs, query outputs, screenshots, architecture
> diagrams, and code snippets.

---

## Why This Skill Exists

IT control testing demands consistent documentation patterns, clean separation
of completeness vs. accuracy, and conclusions that are strictly defensible
against inspected evidence.

This skill encodes those best practices into reusable documentation logic —
so your team moves faster, writes better, and reviews less.

**Outcome:** Faster execution. Improved consistency. Reduced review friction.

---

## What It Generates

- Tester obtained and inspected statements
- Completeness and accuracy documentation
- Light-touch independent C&A procedures
- Excel-friendly sample-based test matrices
- Change monitoring validation write-ups
- Access review documentation
- Allocation / transaction sequencing validation
- Monitoring & alert validation documentation
- Migration / modernization testing documentation

All outputs are structured and suitable for formal audit workpapers.

---

## Project Structure

    itgc-control-testing/
    |
    |-- SKILL.md
    |
    |-- assets/
    |   |-- tester-writeup-templates.md
    |   +-- test-matrix-template.md
    |
    +-- references/
        |-- completeness-accuracy-cheatsheet.md
        |-- common-evidence-types.md

---

## Core Components

### SKILL.md
Activation triggers, documentation standards, workflow structure, and
guardrails to prevent overstatement.

### Templates (assets/)
Reusable documentation modules for:
- Phase I & II QA
- Allocation validation
- Discrepancy rationales
- Monitoring validation
- Change management testing
- Access review sampling

All matrices are formatted for Excel copy/paste.

### Reference Logic (references/)
Maps control objectives to appropriate matrices, completeness vs. accuracy
decision logic, and evidence types to what they prove — and what they do NOT.
Reduces overstatement. Improves defensibility.

---

## Example Prompts
"Write a tester obtained and inspected statement."
"Make sense of this QA evidence."
"Draft completeness and accuracy considerations."
"Generate a population tie-out matrix."
"Build a routing logic validation matrix."
"Document change monitoring testing."

---

## Design Principles

| Principle | What It Means |
|---|---|
| Separate C&A | Completeness and accuracy are evaluated independently |
| Don't Overstate | Conclusions are scoped strictly to inspected artifacts |
| Map Objective First | Documentation structure follows control type |
| Flag Gaps Professionally | Limitations surfaced without confrontational tone |
| Stay Structured | Matrices formatted for immediate reuse |

---

## Control Types Supported

- Data interface controls
- Financial allocation controls
- Approval routing logic
- Access reviews (standard & privileged)
- Change monitoring
- Code validation
- Monitoring & alerting
- Migration / modernization testing

---

## Guardrails

This skill will NOT:
- Assume completeness without record counts
- Treat reviewer sign-off as proof of accuracy
- Assume code is deployed without deployment evidence
- Conflate monitoring with data validation
- Overstate assurance beyond inspected artifacts

---

## How to Use

1. Load the skill into Claude Code
2. Provide technical evidence or describe the control
3. Request structured documentation or matrices
4. Review and tailor output to your environment

---

## Philosophy

Controls are product safeguards.

This skill treats data completeness as system integrity, accuracy as
deterministic processing, monitoring as operational resilience, and change
validation as deployment governance.

It bridges technical systems and structured risk evaluation.

---

## Intended Audience

IT auditors · Technology risk professionals · SOX compliance teams
Governance & controls practitioners · Risk-aware product and platform teams

---

*This project provides documentation structure and workflow guidance.
It does not replace professional judgment, control design evaluation,
or formal audit standards.*
