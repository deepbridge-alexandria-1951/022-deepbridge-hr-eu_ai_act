# EU AI Act from an HR Perspective

## Overview

The **EU AI Act** (Regulation 2024/1689) is the world's first comprehensive AI legislation. It classifies AI systems by risk level and imposes compliance requirements proportional to that risk.

---

## Risk Classification Framework

| Risk Level | Definition | HR Examples |
|-----------|-----------|------------|
| **Prohibited** | Unacceptable risk; banned outright | Subliminal manipulation; real-time biometric surveillance for emotion detection in interviews |
| **High-Risk** | Significant risk to fundamental rights | Recruitment filtering, performance monitoring, automated termination recommendations |
| **General-Purpose** | Foundation models with broad capabilities | GPT-4, Mistral 7B (require transparency) |
| **Minimal Risk** | Low/no impact on rights | Resume parsing, calendar scheduling, chatbot FAQs |

---

## High-Risk AI in HR: Mandatory Requirements

### 1. **Risk Assessment & Management**
- Document all AI systems used in hiring, evaluation, termination decisions.
- Conduct **DPIA** (Data Protection Impact Assessment) before deployment.
- Identify and mitigate bias in training data (gender, race, age, disability).
- Update risk assessment annually or when material changes occur.

### 2. **Data Governance**
- **Data Quality**: Ensure training datasets are representative and unbiased.
- **Data Minimization**: Collect only essential personal data for the AI task.
- **Retention**: Delete HR AI training data after model lifecycle ends.
- **Transparency Logs**: Maintain audit trails of all model decisions (→ PostgreSQL audit logs).

### 3. **Transparency & Documentation**
- Maintain a **Register of High-Risk AI Systems** with:
  - System name, purpose, risk classification.
  - Training data sources and size.
  - Performance metrics and known limitations.
  - Bias testing results.
- Provide **plain-language summaries** to affected employees.

### 4. **Human Oversight**
- **No Fully Autonomous Decisions**: Humans must review and approve all AI outputs affecting employment (hiring, termination, pay decisions).
- Implement **override mechanisms** allowing employees to contest AI decisions.
- Designate **AI accountability officers** within HR.

### 5. **Testing & Monitoring**
- **Pre-deployment Testing**: Benchmark AI performance across demographic groups (gender, age, disability, ethnicity).
- **Post-deployment Monitoring**: Continuously monitor for performance drift and bias emergence.
- **Bias Audit Frequency**: At least annually; more frequently if impact is high.
- **Performance Metrics**: Accuracy, fairness (demographic parity, equalized odds), explainability.

### 6. **Bias Mitigation**
- Use balanced, representative training datasets.
- Apply fairness constraints during model training.
- Implement **algorithmic audits** by independent third parties.
- Provide employees with **explanation rights** when AI significantly impacts them.

### 7. **Cybersecurity & Data Protection**
- Secure API endpoints with authentication (mTLS, API keys).
- Encrypt data in transit and at rest.
- Implement **access controls** (role-based, least privilege).
- Maintain **audit logs** with immutable timestamps for all AI operations.
- Comply with **GDPR** (lawful basis, consent, data retention).

---

## HR AI Systems Classification Examples

| System | Risk Level | Reason |
|--------|-----------|--------|
| Resume screening (automated filtering) | **High** | Directly affects hiring decisions; high impact on candidates |
| Performance rating (AI-assisted evaluation) | **High** | Influences pay, promotion, termination; potential discrimination |
| Skills gap analysis (recommendation engine) | **General** | Advisory only; human makes training decisions |
| Workload distribution prediction | **General** | Operational insight; no autonomous personnel action |
| Employee wellness chatbot | **Minimal** | Low-stakes; advisory only; limited personal data |
| Background check automation | **High** | Security-sensitive; impacts employment eligibility |
| Salary benchmarking AI | **General** | Informational; no individual employment decision |

---

## Implementation Checklist for HR Departments

### Phase 1: Inventory & Assessment
- [ ] **Audit**: List all AI/ML systems currently used in HR workflows.
- [ ] **Classification**: Map each system to EU AI Act risk tier.
- [ ] **Identify High-Risk Systems**: Flag candidates for compliance.
- [ ] **DPIA**: Complete Data Protection Impact Assessment for high-risk systems.

### Phase 2: Documentation
- [ ] **System Register**: Create and maintain register of high-risk AI systems.
- [ ] **Training Data Log**: Document origin, composition, size of training datasets.
- [ ] **Risk Assessment Report**: Detail identified risks and mitigation strategies.
- [ ] **Technical Specifications**: Record model architecture, hyperparameters, performance metrics.

### Phase 3: Technical Implementation
- [ ] **Audit Logging**: Deploy PostgreSQL audit table (timestamp, user, action, model ID, input, output, decision).
- [ ] **API Security**: Enable authentication and encryption on AI endpoints.
- [ ] **Data Minimization**: Remove unnecessary personal data from training sets.
- [ ] **Explainability Layer**: Implement explanation generation for AI decisions.
- [ ] **Override Mechanism**: Build workflow allowing HR staff to reject AI recommendations.

### Phase 4: Testing & Validation
- [ ] **Bias Audit**: Test AI performance across protected characteristics (gender, age, race, disability).
- [ ] **Fairness Metrics**: Calculate demographic parity, equal opportunity, calibration.
- [ ] **Performance Baseline**: Establish accuracy, precision, recall benchmarks.
- [ ] **Third-Party Review**: Commission independent audit of high-risk systems.

### Phase 5: Governance & Monitoring
- [ ] **AI Officer Appointment**: Designate accountability lead for AI compliance.
- [ ] **Transparency Documentation**: Create plain-language summaries for employees.
- [ ] **Ongoing Monitoring**: Set up dashboard to track bias, performance drift, audit logs.
- [ ] **Update Cycle**: Schedule annual re-assessment; more frequent if issues arise.
- [ ] **Incident Response**: Define escalation procedure for AI system failures or bias detection.

### Phase 6: Employee Rights & Remediation
- [ ] **Explanation Rights**: Provide employees the right to request explanations of AI decisions.
- [ ] **Contest Mechanism**: Implement formal appeals process for AI-derived decisions.
- [ ] **Communication**: Inform employees where/how AI is used in HR decisions.
- [ ] **Remedy Path**: Define how discrimination claims related to AI are handled.

---

## Compliance Mapping: EU AI Act ↔ GDPR ↔ NIS 2 ↔ DORA

| Framework | HR AI Requirement |
|-----------|------------------|
| **EU AI Act** | High-risk systems require risk assessment, testing, monitoring, documentation, human oversight. |
| **GDPR** | Lawful basis for processing HR data; data minimization; retention limits; data subject rights (access, correction, erasure). |
| **NIS 2** | Secure AI systems against cyber threats; incident reporting for material security failures. |
| **DORA** | Operational resilience: AI system availability, disaster recovery, third-party risk management (e.g., Ollama provider SLAs). |

---

## Red Flags: Prohibited AI in HR

**Do NOT deploy:**
- Real-time facial recognition for emotion analysis in interviews.
- Subliminal messaging in recruitment communications.
- Fully autonomous termination without human review.
- AI systems trained on biased data with no mitigation applied.
- Systems circumventing employee privacy expectations (covert monitoring).

---

## Key Deliverables for Compliance

1. **Audit Log Schema**: PostgreSQL table recording all AI operations (see `hr_gdpr_validator.py`).
2. **AI System Register**: Spreadsheet or database of all deployed AI systems and their risk tier.
3. **DPIA Template**: Reusable template for Data Protection Impact Assessment.
4. **Bias Audit Report**: Annual third-party certification of fairness metrics.
5. **Transparency Notice**: Employee-facing document explaining AI use in HR.

---

## Timeline

| Phase | Deadline | Action |
|-------|----------|--------|
| **Audit & Inventory** | Q1 2025 | Identify and classify all HR AI systems. |
| **DPIA & Risk Assessment** | Q2 2025 | Complete documentation for high-risk systems. |
| **Technical Remediation** | Q3 2025 | Deploy audit logging, API security, bias monitoring. |
| **Independent Audit** | Q4 2025 | Third-party validation of compliance and fairness. |
| **Ongoing Compliance** | 2026+ | Annual re-assessment, continuous monitoring. |

---

## References

- [EU AI Act (2024/1689)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
- [GDPR Article 22 (Automated Individual Decision-Making)](https://gdpr-info.eu/art-22-gdpr/)
- [EDPB Guidelines 05/2022 on Child Data Processing](https://edpb.ec.europa.eu/sites/default/files/consultation/edpb_guidelines_202205_childrensdata_en.pdf)

---

**Document Version**: 1.0 | **Last Updated**: October 2026 | **License**: MIT
