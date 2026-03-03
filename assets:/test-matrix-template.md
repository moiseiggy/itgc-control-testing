ITGC Test Matrix Templates
This document provides standardized matrix structures for recurring sample-based ITGC testing.
Claude should select and adapt the appropriate matrix based on control type and objective.
All matrices must:
Clearly state objective


Identify population source


Identify attributes tested


Separate completeness vs accuracy where applicable


Avoid vague conclusions


Be Excel-copy friendly (pipe-delimited tables)



1️⃣ General Sample-Based Control Test Matrix
Use for:
Data interface testing


Monitoring validation


Allocation validation


Routing logic testing


Control execution samples



Control Objective:
[State objective clearly]
Population Source:
[System / Query / Report Name]
Sample Selection Method:
[Random / Risk-based / Specific scenario / Test of one / Threshold-based]

Test Matrix
Sample ID
Key Attributes Tested
Expected Result
Evidence Inspected
Result (Pass/Fail)
Tester Conclusion
S1
[List attributes]
[Expected behavior]
[Logs / Query / Screenshot]
Pass
[Concise outcome]
S2












2️⃣ Completeness & Accuracy Tie-Out Matrix
Use when validating:
Pre-job vs Post-job files


Raw → Staging → Final


Batch file → System load


Snowflake ingestion


PFC batch completeness



Control Objective:
Ensure complete and accurate transfer of data from [Source] to [Target]

Record Count Reconciliation
Stage
Record Count
Source of Evidence
Variance
Explanation
Conclusion
Raw Source










Staging










Final Output












KDE Attribute Validation
Sample ID
KDE 1
KDE 2
KDE 3
Source Value
Target Value
Match (Y/N)
Notes


3️⃣ Access Review Sampling Matrix
Use for:
AD


Snowflake


Oracle


ServiceNow


DynamoDB


Mainframe


Windows Server



Control Objective:
Validate completeness and accuracy of user access review.

Population Validation
Step
Population Count
Source
Reviewed Count
Match (Y/N)
Notes


Sample Testing
User ID
Role / Permission
Reviewer Decision
Evidence of Review
Terminated?
Appropriate Access?
Conclusion


4️⃣ Change Monitoring / Git Validation Matrix
Use for:
Git blame validation


Code change monitoring


SAFE change samples


Deployment verification



Control Objective:
Validate that unauthorized changes did not occur during FYXX.

File / Component
Last Modified Date
Modified By
In Scope Period?
Evidence Source
Conclusion


If validating deployment:
Change ID
Change Date
Approval Evidence
Deployment Evidence
Post-Implementation Validation
Conclusion


5️⃣ Allocation Logic Testing Matrix (FS-006 Style)
Use for:
Payment allocation


Interest vs principal logic


$10 tolerance rule


MEA / MPE aggregation


Transaction ordering



Control Objective:
Validate allocation logic processes transactions according to documented business rules.

Sample ID
Transaction Type
Input Amount
Allocation Sequence Expected
Allocation Observed
Variance
Conclusion

If tolerance-based:
Sample ID
Payment Amount
Tolerance Threshold
Expected Behavior
Observed Behavior
Conclusion


6️⃣ Routing Logic / Approval Grid Validation Matrix (COMM-064 / 099 Style)

Control Objective:
Validate approval routing logic functions based on defined attributes.

Sample ID
Risk Rating
Exposure
LGD
Product Type
Grid Expected
Grid Observed
Match (Y/N)
Conclusion


7️⃣ Monitoring & Alert Testing Matrix

Control Objective:
Validate monitoring alerts trigger on failure conditions.

Job Name
Failure Simulated?
Alert Triggered?
Alert Timestamp
Escalation Evidence
Resolution Evidence
Conclusion


8️⃣ Population Completeness (Raw to Review VLOOKUP) Matrix
Use when validating raw dataset inclusion in review workbook.

Raw Record ID
Present in Review? (Y/N)
Exception?
Explanation
Conclusion


9️⃣ Light-Touch C&A Reperformance Matrix

Independent Reperformance
Step
Source Count
Recalculated Count
Match (Y/N)
Notes


Key Attribute Validation
Record ID
Attribute
Source Value
Final Value
Match (Y/N)


Matrix Design Rules
Claude must:
Keep tables Excel-friendly (pipe-delimited).


Avoid merged cells.


Avoid narrative inside tables.


Keep conclusions concise.


Not overstate assurance.


Separate completeness and accuracy when applicable.


Tie conclusions to evidence.

