

name: itgc-control-testing
description: Generate ITGC/IT audit control testing documentation from evidence (screenshots, logs, diagrams), including tester write-ups, completeness and accuracy considerations, light-touch C&A steps, and test programs/matrices. Use when the user asks to "write a tester obtained and inspected statement", "make sense of this evidence", "completeness and accuracy", "C&A procedures", "population tie-out", or "draft control testing steps".





ITGC Control Testing Skill
Purpose
This skill assists in generating structured, defensible ITGC/IT audit documentation from evidence such as:
Screenshots


Logs


Query outputs


Flow diagrams


Code snippets


QA documentation


Access review workbooks


Data pipeline logs


Change monitoring evidence


The outputs produced by this skill must align with SOX/ITGC audit documentation standards and be suitable for inclusion in formal workpapers.

When To Use This Skill
Automatically activate this skill when the user requests:
"write a tester obtained and inspected statement"


"tester determined statement"


"make sense of this evidence"


"completeness and accuracy"


"C&A procedures"


"population tie-out"


"phase I QA"


"phase II QA"


"access review completeness"


"draft control testing steps"


"test of design write-up"


"nature of testing of control"


"test matrix"


"discrepancy rationale"


"light-touch C&A"


"update testing documentation"



Core Workflow
When invoked, follow this structured process:

Step 1: Identify the Evidence Type
Determine what kind of artifact is being reviewed:
Raw system extract


SQL query output


ETL or Lambda log


Access review workbook


Aggregated review output


Reconciliation evidence


Change ticket / deployment record


Architecture diagram


QA documentation


Monitoring alert / PagerDuty screenshot


Code logic snippet


Explicitly state what the evidence represents before drafting conclusions.

Step 2: Identify the Control Objective
Determine which objective the evidence supports:
Completeness


Accuracy


Authorization


Change management


Monitoring


Segregation of duties


Data integrity


Allocation logic


Population coverage


Execution validation


If not explicitly provided, infer from context but do not overstate.

Step 3: Apply Structured Documentation Standards
All outputs must:
Use formal audit tone


Avoid speculative language


Avoid over-claiming beyond evidence


Clearly distinguish completeness vs accuracy


Tie conclusions directly to observed evidence


Note limitations where applicable



Output Modules
Use the appropriate module below based on context.

Module A: Tester Obtained and Inspected Statement
Structure:
The tester obtained and inspected [type of evidence] to evaluate [control objective]. The tester determined that [objective-supported observation]. The tester noted that [specific evidence observed]. Based on the procedures performed and evidence inspected, the tester determined that [clear conclusion aligned to objective].
Never claim:
"ensures" unless explicitly demonstrated.


Full coverage if only a sample is shown.


Source completeness if relying on downstream controls.



Module B: Completeness Considerations
Structure:
Completeness:
 The tester obtained and inspected [source evidence]. The tester determined that the population was generated from [system-of-record / direct extract]. The tester noted that [row counts / execution logs / reconciliation / no manual filtering]. Based on the procedures performed, the tester determined that the population appears complete for the in-scope period.
If limitations exist:
Direct source record counts were not available; completeness reliance was placed on downstream validation controls and ingestion logs.

Module C: Accuracy Considerations
Structure:
Accuracy:
 The tester obtained and inspected [transformation logic / output files / aggregation process]. The tester determined that standardized processing logic was applied. The tester noted that [before/after counts, validation checks, reconciliations]. Based on the procedures performed, the tester determined that the population appears accurate.

Module D: Phase I QA (Raw Data Validation)
Focus on:
Data source extraction


Record counts


Timestamp


No pre-filtering


Matching raw to staging



Module E: Phase II QA (Transformation / Aggregation Validation)
Focus on:
Cleaning logic


De-duplication


HR matching


Aggregation steps


Before/after counts


Exception handling



Module F: Light-Touch C&A (Independent + Management)
Independent C&A:
Reperform one tie-out from source → raw → final output


Validate row counts


Confirm key fields preserved


Management C&A:
Evidence of QA checklist


Evidence of reviewer approval


Timestamp validation


Exception tracking



Module G: Test Program / Test Steps
When drafting testing steps:
Structure as:
Identify control objective.


Identify population source.


Perform completeness validation.


Perform accuracy validation.


Inspect monitoring (if applicable).


Conclude operating effectiveness.


Include:
Attributes tested


Evidence inspected


Sample selection method


Expected result



Guardrails
Do NOT:
Infer system-of-record unless explicitly supported.


Assume upstream completeness without evidence.


Conclude effectiveness without tying to evidence.


State that code was reviewed in production unless confirmed.


If ambiguity exists, state:
Based on the evidence provided...

Tone Calibration
Outputs must be:
Concise


Defensible


Structured


Audit-ready


Professional


Neutral


Evidence-based


Avoid:
Casual tone


Overly technical engineering jargon


Emotional or defensive phrasing



Advanced Handling
If evidence shows discrepancies:
Identify discrepancy clearly.


State management’s rationale.


Evaluate reasonableness.


Conclude whether control objective is still met.


If testing update/remediation:
Distinguish between prior logic and updated logic.


Confirm whether scope is limited to changed components.


Validate no unintended impact.



Expected Output Formatting
When relevant, separate sections as:
Completeness


Accuracy


Tester Determined


Independent C&A


Management C&A


Test Steps


Conclusion


Use bold headers for clarity.

Default Assumptions
Unless specified otherwise:
Control is SOX-relevant.


Testing period is defined.


Evidence is production unless stated QA.


Objective is either completeness or accuracy.



Success Criteria
This skill is considered successful when:
Outputs require minimal manual editing before workpaper insertion.


Completeness vs accuracy are clearly separated.


Conclusions are defensible in audit review.


Language aligns with ITGC documentation standards.


