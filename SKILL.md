| name | description |
|---|---|
| itgc-control-testing | Generate ITGC/IT audit control testing documentation from evidence (screenshots, logs, diagrams), including tester write-ups, completeness and accuracy considerations, light-touch C&A steps, and test programs/matrices. Use when the user asks to "write a tester obtained and inspected statement", "make sense of this evidence", "completeness and accuracy", "C&A procedures", "population tie-out", or "draft control testing steps". |

# ITGC Control Testing Skill

> Generate structured, defensible ITGC/IT audit documentation from
> evidence — screenshots, logs, query outputs, flow diagrams, code
> snippets, QA documentation, access review workbooks, and more.
>
> All outputs align with SOX/ITGC audit standards and are suitable
> for direct inclusion in formal workpapers.

---

## Activation Triggers

Use this skill when asked to:

- "Write a tester obtained and inspected statement"
- "Tester determined statement"
- "Make sense of this evidence"
- "Completeness and accuracy" / "C&A procedures"
- "Population tie-out"
- "Phase I QA" / "Phase II QA"
- "Access review completeness"
- "Draft control testing steps"
- "Test of design write-up"
- "Nature of testing of control"
- "Test matrix"
- "Discrepancy rationale"
- "Light-touch C&A"
- "Update testing documentation"

---

## Core Workflow

### Step 1 — Identify the Evidence Type

Determine what artifact is being reviewed:

Raw system extract · SQL query output · ETL or Lambda log · Access review
workbook · Aggregated review output · Reconciliation evidence · Change
ticket / deployment record · Architecture diagram · QA documentation ·
Monitoring alert / PagerDuty screenshot · Code logic snippet

> Always explicitly state what the evidence represents before drafting conclusions.

---

### Step 2 — Identify the Control Objective

Determine which objective the evidence supports:

Completeness · Accuracy · Authorization · Change management · Monitoring ·
Segregation of duties · Data integrity · Allocation logic · Population
coverage · Execution validation

> If not explicitly provided, infer from context — but never overstate.

---

### Step 3 — Apply Structured Documentation Standards

All outputs must:

- Use formal audit tone
- Avoid speculative language
- Avoid over-claiming beyond evidence inspected
- Clearly distinguish completeness from accuracy
- Tie conclusions directly to observed evidence
- Note limitations where applicable

---

## Output Modules

### Module A — Tester Obtained and Inspected Statement

> The tester obtained and inspected [type of evidence] to evaluate
> [control objective]. The tester determined that [objective-supported
> observation]. The tester noted that [specific evidence observed].
> Based on the procedures performed and evidence inspected, the tester
> determined that [clear conclusion aligned to objective].

**Never claim:**
- "Ensures" unless explicitly demonstrated
- Full coverage if only a sample is shown
- Source completeness if relying on downstream controls

---

### Module B — Completeness Considerations

> **Completeness:**
> The tester obtained and inspected [source evidence]. The tester
> determined that the population was generated from [system-of-record /
> direct extract]. The tester noted that [row counts / execution logs /
> reconciliation / no manual filtering]. Based on the procedures performed,
> the tester determined that the population appears complete for the
> in-scope period.

**If limitations exist, append:**

> Direct source record counts were not available; completeness reliance
> was placed on downstream validation controls and ingestion logs.

---

### Module C — Accuracy Considerations

> **Accuracy:**
> The tester obtained and inspected [transformation logic / output files /
> aggregation process]. The tester determined that standardized processing
> logic was applied. The tester noted that [before/after counts, validation
> checks, reconciliations]. Based on the procedures performed, the tester
> determined that the population appears accurate.

---

### Module D — Phase I QA (Raw Data Validation)

Focus areas:
- Data source extraction
- Record counts and timestamps
- Confirmation of no pre-filtering
- Matching raw dataset to staging

---

### Module E — Phase II QA (Transformation / Aggregation Validation)

Focus areas:
- Cleaning logic
- De-duplication
- HR matching
- Aggregation steps
- Before / after counts
- Exception handling

---

### Module F — Light-Touch C&A

**Independent C&A:**
- Reperform one tie-out from source → raw → final output
- Validate row counts
- Confirm key fields preserved throughout processing

**Management C&A:**
- Evidence of QA checklist
- Evidence of reviewer approval
- Timestamp validation
- Exception tracking

---

### Module G — Test Program / Test Steps

Structure testing steps as follows:

1. Identify the control objective
2. Identify the population source
3. Perform completeness validation
4. Perform accuracy validation
5. Inspect monitoring (if applicable)
6. Conclude operating effectiveness

Each step must include:
- Attributes tested
- Evidence inspected
- Sample selection method
- Expected result

---

## Guardrails

| Do NOT | Instead |
|---|---|
| Infer system-of-record without support | State what system was identified in evidence |
| Assume upstream completeness | Validate or note reliance on downstream controls |
| Conclude effectiveness without evidence tie | Scope conclusion to what was inspected |
| State code reviewed in production unless confirmed | Note environment as QA or unconfirmed |

**If ambiguity exists, state:**
> "Based on the evidence provided..."

---

## Advanced Handling

### If Evidence Shows Discrepancies
1. Identify the discrepancy clearly
2. State management's rationale
3. Evaluate reasonableness
4. Conclude whether the control objective is still met

### If Testing Update / Remediation
1. Distinguish between prior logic and updated logic
2. Confirm whether scope is limited to changed components
3. Validate no unintended impact to adjacent components

---

## Output Formatting

When relevant, separate outputs into these sections:

| Section | Purpose |
|---|---|
| **Completeness** | Record count reconciliation and population integrity |
| **Accuracy** | Field-level and transformation validation |
| **Tester Determined** | Conclusion tied to inspected evidence |
| **Independent C&A** | Reperformed tie-out procedures |
| **Management C&A** | Reliance on management QA |
| **Test Steps** | Structured testing program |
| **Conclusion** | Final operating / design effectiveness statement |

---

## Tone Requirements

| Use | Avoid |
|---|---|
| Concise, defensible language | Casual tone |
| Structured audit formatting | Overly technical engineering jargon |
| Neutral, evidence-based conclusions | Emotional or defensive phrasing |
| Professional audit terminology | Speculative or absolute statements |

---

## Default Assumptions

Unless specified otherwise:

- Control is SOX-relevant
- Testing period is defined
- Evidence is from production (unless stated as QA)
- Objective is either completeness or accuracy

---

## Success Criteria

This skill is considered successful when:

- Outputs require minimal manual editing before workpaper insertion
- Completeness and accuracy are clearly separated
- Conclusions are defensible in audit review
- Language aligns with ITGC documentation standards

---

*This skill provides documentation structure and workflow guidance for
IT audit and SOX testing workflows. It does not replace professional
judgment, control design evaluation, or formal audit standards.*
