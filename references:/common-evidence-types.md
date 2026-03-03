Common Evidence Types in ITGC Testing
This document helps Claude interpret what evidence is being reviewed and what it typically proves (or does NOT prove).

1️⃣ SQL Query Output
Usually proves:
Data presence


Field values


Record counts


Does NOT prove:
Upstream completeness


Transformation logic unless script reviewed


That query wasn’t manually filtered


Best practice:
Ask for query text


Confirm no WHERE clause exclusions unless documented


Tie counts to system-of-record



2️⃣ Code Snippet (Java, Go, Python, Lambda, SQL)
Usually proves:
Processing logic


Conditional statements


Routing logic


Allocation sequence


Does NOT prove:
Code deployed to prod


That version hasn’t changed


That monitoring exists


Best practice:
Confirm environment (QA vs Prod)


Inspect version history


Tie to change ticket if applicable



3️⃣ Screenshot of UI
Usually proves:
Configuration setting


Status


User entitlement


Alert existence


Does NOT prove:
System-wide enforcement


Backend logic


That alert triggers properly


Best practice:
Pair with log evidence


Validate backend logic if control critical



4️⃣ PagerDuty / Alert Screenshot
Usually proves:
Alert configured


Alert triggered


Alert resolved


Does NOT prove:
Trigger logic covers all failure scenarios


Escalation was appropriate


Root cause fixed


Best practice:
Request one triggered example


Inspect escalation path


Validate service key alignment



5️⃣ Pivot Table / Aggregated Review Workbook
Usually proves:
Reviewer performed review


Aggregation performed


Does NOT prove:
Raw data complete


No filtering before pivot


No hidden rows


Best practice:
Request raw extract


Reperform pivot independently


Perform raw-to-review VLOOKUP



6️⃣ Git Blame / Version History
Usually proves:
Last modified date


Author of change


Does NOT prove:
Deployed to production


That related files unchanged


That configuration files unchanged


Best practice:
Confirm branch/environment


Confirm no changes in FY period


Tie to release log



7️⃣ Architecture Diagram
Usually proves:
Intended design


System components


Data flow logic


Does NOT prove:
Operational effectiveness


That implementation matches diagram


That monitoring covers all hops


Best practice:
Validate with logs


Confirm actual job names


Confirm active vs legacy components



8️⃣ Batch Log / Job Log
Usually proves:
Job ran


Success/failure status


Record counts


Does NOT prove:
Field-level accuracy


That upstream data was correct


That failure conditions properly handled


Best practice:
Inspect error handling logic


Confirm monitoring on job failure


Tie count to downstream table



9️⃣ Impact Analysis / SAFE Document
Usually proves:
Management documented change rationale


Risk evaluation occurred


Does NOT prove:
Testing performed


Change deployed properly


Code matches documentation


Best practice:
Inspect test evidence


Confirm production deployment


Confirm reviewer approval date



🔟 Reviewer Sign-Off
Usually proves:
Review occurred


Reviewer acknowledged


Does NOT prove:
Review was substantive


Reviewer inspected raw data


Reviewer independent


Best practice:
Inspect review notes


Confirm no self-review


Confirm population tie-out



Final Rule for Claude
Never assume evidence proves more than it actually demonstrates.
If evidence only proves configuration — do not imply operational testing.
If evidence only proves logic — do not imply completeness.
If evidence only proves monitoring — do not imply accuracy.
Always scope conclusions to what was actually inspected.

