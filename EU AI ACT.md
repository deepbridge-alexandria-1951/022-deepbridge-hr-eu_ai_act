# Regulatory Framework: HR + EU AI Act

## Template for Regulatory Analysis

### GDPR Compliance Layer

**Personal Data Processing:**
- Data category: [specify: performance, salary, health, etc.]
- Legal basis: [Article 6: consent, contract, legal obligation, vital interests, public task, legitimate interests]
- Processing purpose: [explicit, specific, legitimate]
- Retention period: [time-bound, measurable]
- Data subject rights: [access, rectification, erasure, portability, objection]

**Audit Trail Requirement (Article 5(2)):**
- Timestamp of each processing operation
- Data categories involved
- Processing method (manual, algorithmic, AI-driven)
- Outcome/decision recorded
- Retention per organizational retention policy

---

### EU AI Act Compliance Layer (Articles 5–6)

**High-Risk HR AI Systems:**
- Recruitment & selection automation
- Employee performance evaluation
- Compensation & promotion decisions
- Termination & restructuring recommendations

**Mandatory Safeguards:**
1. **Transparency:** Model version, decision confidence, input features disclosed
2. **Human Oversight:** Automated decisions require human review before execution
3. **Appeal Mechanism:** Employee right to contest AI-driven decision
4. **Non-Discrimination:** Bias testing on protected characteristics (gender, ethnicity, age)
5. **Documentation:** Technical documentation + impact assessment

---

### Combined HR + EU AI Act Compliance Checklist

| Control | GDPR Article | EU AI Act Article | Implementation |
|---------|--------------|-------------------|-----------------|
| **Consent for AI processing** | 6, 7 | 5 | Explicit opt-in for AI-driven decisions |
| **Automated decision logging** | 22 | 5, 6 | Every AI output logged with reasoning |
| **Right to human review** | 22 | 6 | Mandatory human validation before action |
| **Data minimization** | 5(1)(c) | 5 | Only necessary HR data inputs to model |
| **Non-discrimination audit** | – | 5 | Regular bias testing on protected classes |
| **Appeal/remedy process** | 22 | 6 | Documented appeal procedure >30 days |
| **Data retention limit** | 5(1)(e) | – | HR data deleted per policy (typ. 12 months) |
| **Audit trail** | 5(2) | 6 | Full compliance log with timestamps |

---

### Risk Mitigation Examples

**Example 1: Automated Hiring**
- ❌ **Violation:** AI model selects candidates without human review
- ✅ **Mitigation:** HR manager reviews AI ranking, provides final decision, logs reasoning

**Example 2: Salary Adjustment**
- ❌ **Violation:** AI recommends salary cuts based on performance score alone
- ✅ **Mitigation:** AI provides recommendation with confidence score, manager verifies, employee can appeal

**Example 3: Performance Classification**
- ❌ **Violation:** System automatically flags poor performers for termination
- ✅ **Mitigation:** System alerts manager, manager reviews with employee, decision logged, appeal option available

---

### Regulatory Reporting

**GDPR Data Processing Agreement (DPA):**
- AI model classified as "processor" or "joint controller"
- Responsibilities: data security, breach notification, audit cooperation

**EU AI Act Compliance Report:**
- Quarterly audit of HR AI decisions
- Bias testing results
- Appeal/override statistics
- Any incidents or deviations

---

## Notes

- This template applies to **on-premises HR AI systems only**
- Update annually or when regulations change
- All processing must be documented in PostgreSQL audit trail
- All decisions are subject to retrospective review
