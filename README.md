📘 ITGC Control Testing Skill

itgc-control-testing is a structured Claude Skill designed to generate audit-ready ITGC documentation from technical evidence such as logs, screenshots, query outputs, flow diagrams, and code snippets.

This project standardizes how completeness, accuracy, and control execution are evaluated and documented across recurring SOX / ITGC testing workflows.

🚀 What This Skill Does

This skill helps generate:

✔ Tester obtained and inspected statements

✔ Completeness and accuracy documentation

✔ Light-touch independent C&A procedures

✔ Sample-based test matrices (Excel-friendly)

✔ Change monitoring validation write-ups

✔ Access review documentation

✔ Allocation / transaction sequencing validation

✔ Monitoring & alert validation documentation

✔ Migration / update testing documentation

The outputs are structured, defensible, and suitable for formal audit workpapers.

🧠 Why This Exists

IT control testing often requires:

Repeated documentation patterns

Clear separation of completeness vs accuracy

Structured sampling matrices

Consistent tone and defensibility

Risk-aware gap identification

Instead of rewriting similar narratives repeatedly, this skill encodes best practices into reusable documentation logic.

The result: faster execution, improved consistency, and reduced review friction.


📂 Project Structure
itgc-control-testing/
│
├── SKILL.md
│
├── assets/
│   ├── tester-writeup-templates.md
│   ├── test-matrix-template.md
│
├── references/
│   ├── completeness-accuracy-cheatsheet.md
│   ├── common-evidence-types.md
│   ├── control-objective-mapper.md

🏗️ Core Components
1️⃣ SKILL.md

Defines:

Activation triggers

Documentation standards

Structured workflow

Output formatting rules

Guardrails to prevent overstatement

2️⃣ Templates (assets/)

Provides reusable modules for:

Phase I QA

Phase II QA

Allocation validation

Discrepancy rationales

Monitoring validation

Change management testing

Access review sampling

All matrices are Excel-friendly and structured for repeatable sampling work.

3️⃣ Reference Logic (references/)

Improves Claude’s judgment by mapping:

Control objective → appropriate matrix

Completeness vs accuracy decision logic

Common evidence types → what they prove (and don’t prove)

Risk flags and escalation indicators

This reduces audit overstatement and improves defensibility.

🧩 Example Use Cases

This skill can be triggered with prompts like:

"Write a tester obtained and inspected statement."

"Make sense of this QA evidence."

"Draft completeness and accuracy considerations."

"Generate a population tie-out matrix."

"Build a routing logic validation matrix."

"Document change monitoring testing."

🔍 Design Principles

This skill follows several core principles:

1️⃣ Separate Completeness from Accuracy

Never conflate record inclusion with field correctness.

2️⃣ Do Not Overstate Assurance

Conclusions are scoped strictly to evidence reviewed.

3️⃣ Map Control Objective First

Documentation structure depends on control type.

4️⃣ Flag Gaps Professionally

Evidence limitations are identified without confrontation.

5️⃣ Excel-Friendly Output

Sampling matrices are formatted for immediate reuse.

📊 Control Types Supported

Data interface controls

Financial allocation controls

Approval routing logic

Access reviews (privileged & standard)

Change monitoring

Code validation

Monitoring & alerting

Migration / modernization testing

⚖️ Guardrails

This skill is designed to avoid:

Assuming completeness without record counts

Treating reviewer sign-off as proof of accuracy

Assuming code is deployed without deployment evidence

Conflating monitoring with data validation

Overstating assurance beyond inspected artifacts

🎯 Intended Audience

IT auditors

Technology risk professionals

SOX compliance teams

Governance & controls practitioners

Risk-aware product or platform teams

🛠️ How to Use

Install or load the skill into Claude Code.

Provide technical evidence or describe the control being tested.

Ask for structured documentation or matrices.

Review outputs and tailor to your specific environment.

💡 Philosophy

Controls are ultimately product safeguards.

This skill treats:

Data completeness as system integrity

Accuracy as deterministic processing

Monitoring as operational resilience

Change validation as deployment governance

By encoding structured risk thinking into documentation workflows, this project bridges technical systems and control design.

📌 Disclaimer

This project provides documentation structure and workflow guidance. It does not replace professional judgment, control design evaluation, or formal audit standards.
