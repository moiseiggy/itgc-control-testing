
Tester Write-Up Templates
These templates are designed for consistent, defensible ITGC documentation aligned to SOX audit standards.
Claude should select and adapt the appropriate template based on evidence type and control objective.

1️⃣ General Tester Obtained and Inspected Template
The tester obtained and inspected [type of evidence] to evaluate [control objective]. The tester determined that [objective-supported observation]. The tester noted that [specific supporting detail observed in the evidence]. Based on the procedures performed and evidence inspected, the tester determined that the control appears to be designed and/or operating effectively for the in-scope period.
Use when:
Reviewing logs
Reviewing screenshots
Reviewing SQL outputs
Reviewing system configurations
Reviewing monitoring evidence

2️⃣ Completeness Considerations Template
Completeness:
The tester obtained and inspected [source data / extract / query output] to evaluate the completeness of the population. The tester determined that the data was sourced directly from [system-of-record / production database / system query] without manual pre-filtering prior to extraction. The tester noted that record counts and execution timestamps were documented and reconciled to [staging table / review output / aggregation file]. Based on the procedures performed, the tester determined that the population appears complete for the in-scope period.
If relying on downstream controls:
Direct source record counts were not available; therefore, completeness reliance was placed on ingestion logs and downstream validation controls designed to detect missing or incomplete records.

3️⃣ Accuracy Considerations Template
Accuracy:
The tester obtained and inspected [transformation logic / aggregation process / review workbook / output file] to evaluate the accuracy of the population. The tester determined that standardized processing logic was applied consistently across the dataset. The tester noted that before-and-after record counts, validation checks, and/or reconciliation procedures were documented as part of management’s QA process. Based on the procedures performed, the tester determined that the population appears accurate for the in-scope period.

4️⃣ Phase I QA (Raw Data Extraction Validation)
Use when reviewing raw extraction scripts or initial data pulls.
The tester obtained and inspected evidence of management’s Phase I quality assurance procedures over the raw data extraction process. The tester determined that user access data was extracted directly from [system name] via [query/script/tool], and record counts were documented at the time of extraction. The tester noted that the extracted record count agreed to the staging/raw dataset and no manual filtering occurred prior to data landing. Based on the procedures performed, the tester determined that management’s Phase I QA supports completeness of the extracted population.

5️⃣ Phase II QA (Transformation / Aggregation Validation)
Use when reviewing transformation scripts, aggregation files, or ETL logs.
The tester obtained and inspected evidence of management’s Phase II quality assurance procedures over the data transformation and aggregation process. The tester determined that processing logic (e.g., de-duplication, HR matching, classification, aggregation) was executed via standardized scripts without manual manipulation of the dataset. The tester noted that before-and-after record counts and reconciliation checks were documented to validate expected differences. Based on the procedures performed, the tester determined that management’s Phase II QA supports the accuracy of the transformed population.

6️⃣ Discrepancy Rationale Template
Use when record counts differ or exceptions are observed.
The tester noted a variance between [dataset A] and [dataset B] of [X records]. Management indicated that the variance was due to [duplicate removal / system IDs excluded / terminated users removed / expected filtering criteria]. The tester inspected supporting documentation and confirmed that the variance aligns with documented transformation logic. Based on the procedures performed, the tester determined that the discrepancy is reasonable and does not impact the control objective.

7️⃣ Update Testing / Change Validation Template
Use for update testing or post-remediation validation.
The tester obtained and inspected updated configuration settings and/or revised processing logic to evaluate changes implemented during the current period. The tester determined that the updated logic aligns with documented requirements and did not introduce unintended impact to unaffected components. The tester noted that sample-based validation was performed to confirm expected output following the change. Based on the procedures performed, the tester determined that the updated control design and operation remain effective.

8️⃣ Monitoring & Alerting Validation Template
Use for PagerDuty, Splunk, CloudWatch, monitoring Lambda, etc.
The tester obtained and inspected evidence of monitoring and alerting configurations for the in-scope process. The tester determined that alerts are configured to trigger upon failure conditions (e.g., job failure, missing file, threshold breach). The tester noted that evidence of a successfully triggered and resolved alert was provided, including timestamps and remediation details. Based on the procedures performed, the tester determined that monitoring controls are designed and operating effectively.

9️⃣ Code Logic Inspection Template
Use when reviewing GitHub, stored procedures, or Lambda logic.
The tester obtained and inspected the relevant code logic to evaluate whether processing aligns with documented business rules. The tester determined that the code references in-scope fields and applies transformation logic consistent with control requirements. The tester noted that no unauthorized modifications were observed within the reviewed version. Based on the procedures performed, the tester determined that the logic supports the control objective.
If Git blame used:
The tester inspected version history and confirmed no changes to the relevant logic occurred during the in-scope period.

🔟 Allocation / Transaction Sequencing Validation Template
Use for PFC, Snowflake transaction ordering, balance allocation testing.
The tester obtained and inspected transaction-level data to evaluate allocation and sequencing logic. The tester determined that transactions were ordered using [Posted_Sequence_Number / Transaction_Ordering_Key], and allocation amounts were applied consistent with documented business rules. The tester noted that payment allocation amounts corresponded to reductions in principal and/or interest balances as expected. Based on the procedures performed, the tester determined that allocation logic appears to be functioning accurately.

1️⃣1️⃣ Light-Touch Independent C&A Template
The tester independently reperformed a tie-out of record counts from [source extract] to [raw/staging dataset] and to the final review output for one in-scope sample. The tester confirmed that key attributes were preserved throughout processing and that no unexplained variances were identified. Based on the procedures performed, the tester determined that completeness and accuracy appear reasonable.

1️⃣2️⃣ Management C&A Reliance Template
The tester obtained and inspected evidence of management’s documented quality assurance procedures, including row count validations, reconciliation checks, and approval sign-offs. The tester determined that management performed structured review procedures prior to control execution. Based on the procedures performed, the tester determined that reliance on management’s QA is reasonable.

1️⃣3️⃣ Downstream Control Reliance Template
Use when direct source completeness is unavailable.
Direct record counts from the upstream source system were not obtainable due to system constraints. The tester therefore obtained and inspected evidence of downstream reconciliation controls and ingestion logs designed to detect missing or incomplete data. Based on the procedures performed and absence of exception reports, the tester determined that completeness risk is reasonably mitigated.

Documentation Standards Reminder
All outputs must:
Separate completeness from accuracy when applicable.
Tie directly to observed evidence.
Avoid absolute statements (e.g., “ensures”).
Avoid implying full system coverage unless explicitly demonstrated.
Use neutral, audit-defensible language.

If you'd like, next we can build:
test-matrix-template.md (very powerful for recurring sampling work)
completeness-accuracy-cheatsheet.md (quick logic guide for Claude)
Or create a regression prompt test suite to stress-test this skill
This is shaping up to be a very strong repeatable automation framework for your workflow.

