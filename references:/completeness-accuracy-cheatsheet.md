# Completeness vs. Accuracy Cheat Sheet

> A structured guide for assessing, documenting, and separating completeness
> and accuracy considerations across ITGC and data interface controls.
>
> Claude must ALWAYS evaluate whether completeness, accuracy, or both apply.

---

## 1. Core Definitions

| Dimension | Question | Focus Areas |
|---|---|---|
| **Completeness** | Are all required records included? | Record counts · Missing records · File arrival · Filtering logic · Upstream exclusions |
| **Accuracy** | Are the records correct? | Field-level correctness · Transformation logic · Aggregation logic · Allocation sequencing · Attribute mapping |

---

## 2. Quick Decision Framework

| Scenario | What Applies |
|---|---|
| Data moving between systems? | Completeness + Accuracy required |
| Access review? | Completeness of population + Accuracy of entitlements |
| Routing logic? | Accuracy (attribute-based) · Completeness usually less relevant |
| Monitoring? | Accuracy of trigger logic · Not data completeness |
| Change monitoring? | Accuracy of version validation · Not record completeness |

---

## 3. Common Evidence Types

### Completeness Evidence
- Raw source record counts
- Batch logs
- Pre-job vs. post-job counts
- File arrival confirmations
- Staging vs. final table comparison
- Reconciliation reports
- Ingestion logs
- DLQ monitoring

### Accuracy Evidence
- KDE value comparison
- Code logic inspection
- SQL transformation scripts
- Allocation ordering validation
- Attribute mapping tables
- Before / after field comparison
- Reviewer sign-offs
- Pivot table aggregations

---

## 4. When Completeness Evidence Is Weak

If direct source counts are unavailable, rely on:

- Downstream reconciliation controls
- Monitoring alerts
- Exception reports
- Audit trail logs

| Instead of... | Use... |
|---|---|
| "Completeness ensured" | "Completeness risk reasonably mitigated through..." |

---

## 5. When Accuracy Evidence Is Weak

### Red Flags
- Manual Excel manipulation
- No transformation documentation
- Reviewer summary only (no raw file)
- No field-level comparison

### Mitigation Approach
- Perform independent recalculation
- Inspect code directly
- Reperform tie-out
- Perform a targeted sample

---

## 6. Separation Language Guide

**Incorrect:**
```
The tester determined the data is complete and accurate.
```

**Correct:**
```
The tester determined that record counts reconciled between source and
target (completeness). The tester further determined that sampled key
data elements agreed between systems (accuracy).
```

Always document completeness and accuracy as separate, distinct conclusions.

---

## 7. When Both Apply — High-Risk Controls

Both dimensions are required for:

- Payment allocation
- Exposure aggregation
- Approval routing
- Master file generation
- Data warehouse ingestion

### Required Steps

- [ ] Reconcile counts (completeness)
- [ ] Validate field-level values (accuracy)
- [ ] Inspect logic (processing integrity)

---

## 8. Common Audit Pitfalls

| Pitfall | Why It's a Problem |
|---|---|
| Assuming no variance = completeness | Absence of exception does not confirm all records arrived |
| Confusing monitoring with completeness | Monitoring detects failures — it does not confirm record inclusion |
| Ignoring upstream filtering | Records may be excluded before reaching the tested output |
| Assuming lift-and-shift = no logic change | Migration can introduce unintended rounding or filtering behavior |
| Treating reviewer sign-off as accuracy proof | Sign-off confirms review occurred — not that fields are correct |

---

## 9. Escalation Indicators

Escalate if any of the following are present:

- No source of record identified
- Counts vary without explanation
- Hard-coded filters observed
- No monitoring tied to a failure condition
- Reviewer reviewing their own access
- Retroactive change approvals noted

---

*This cheat sheet provides structured reasoning guidance for IT audit workflows.
It does not replace professional judgment or formal audit standards.*
