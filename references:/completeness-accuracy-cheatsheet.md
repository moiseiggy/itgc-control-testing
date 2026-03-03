Completeness vs Accuracy Cheat Sheet
This document guides how to assess, document, and separate completeness and accuracy considerations in ITGC and data interface controls.
Claude must ALWAYS evaluate whether completeness, accuracy, or both apply.

1️⃣ Core Definitions
Completeness
Are all required records included?
Focus on:
Record counts


Missing records


File arrival


Filtering logic


Upstream exclusions



Accuracy
Are the records correct?
Focus on:
Field-level correctness


Transformation logic


Aggregation logic


Allocation sequencing


Attribute mapping



2️⃣ Quick Decision Framework
Ask:
Is data moving between systems?
 → Completeness + Accuracy required


Is this an access review?
 → Completeness of population + Accuracy of entitlements


Is this routing logic?
 → Accuracy (attribute-based logic), completeness usually less relevant


Is this monitoring?
 → Accuracy of trigger logic (not data completeness)


Is this change monitoring?
 → Accuracy of version validation (not record completeness)



3️⃣ Common Completeness Evidence
Raw source record counts


Batch logs


Pre-job vs post-job counts


File arrival confirmations


Staging vs final table comparison


Reconciliation reports


Ingestion logs


DLQ monitoring



4️⃣ Common Accuracy Evidence
KDE value comparison


Code logic inspection


SQL transformation scripts


Allocation ordering validation


Attribute mapping tables


Before/after field comparison


Reviewer sign-offs


Pivot table aggregations



5️⃣ When Completeness Is Weak
If direct source counts unavailable:
You must rely on:
Downstream reconciliation controls


Monitoring alerts


Exception reports


Audit trail logs


Never state:
“Completeness ensured”
Instead state:
“Completeness risk reasonably mitigated through…”

6️⃣ When Accuracy Is Weak
Red flags:
Manual Excel manipulation


No transformation documentation


Reviewer summary only (no raw file)


No field-level comparison


Mitigation approach:
Perform independent recalculation


Inspect code


Reperform tie-out


Perform targeted sample



7️⃣ Separation Language Guide
Incorrect:
The tester determined the data is complete and accurate.
Correct:
The tester determined that record counts reconciled between source and target (completeness).
 The tester further determined that sampled key data elements agreed between systems (accuracy).

8️⃣ Common Audit Pitfalls
Assuming no variance = completeness


Confusing monitoring with completeness


Ignoring upstream filtering


Assuming lift-and-shift means no logic change


Treating reviewer sign-off as accuracy proof



9️⃣ When Both Apply (High-Risk Controls)
Examples:
Payment allocation


Exposure aggregation


Approval routing


Master file generation


Data warehouse ingestion


You must:
Reconcile counts (completeness)


Validate field-level values (accuracy)


Inspect logic (processing integrity)



🔟 Escalation Indicators
Escalate if:
No source of record identified


Counts vary without explanation


Hard-coded filters observed


No monitoring tied to failure condition


Reviewer reviewing their own access


Retroactive change approvals

