# Week 5 – AI Management Systems and ISO/IEC 42001

## Overview

This week focused on **AI management systems (AIMS)** and how ISO/IEC 42001:2023 can be used to govern AI throughout an organisation.

The activities continued with the Saltbush Group hiring classifier from Week 4. The classifier is supplied by an external vendor and is used to recommend which applicants should be shortlisted for an interview. In Week 4, the fairness audit identified a **60% selection rate for Group A and 30% for Group B**, which showed why looking only at overall accuracy can hide important differences between groups.

This week moved beyond identifying the problem and looked at the governance system that should exist around the classifier. I completed an ISO/IEC 42001 gap analysis, compared my assessment with an overly positive assessment from an HR manager, mapped the main ISO clauses to actions Saltbush should take, examined an ISO/IEC 42001 certificate, audited a Statement of Applicability, and designed a monitoring trigger for future fairness issues.

---

# Task 1 – ISO/IEC 42001 Gap Analysis

I completed the **VerifyWise ISO 42001 Gap Analysis** for Saltbush Group across Clauses 4 to 10.

The results showed that Saltbush is a long way from having an effective AI management system.

## Readiness Report

| Item | Result |
|---|---|
| **Overall readiness score** | **2%** |
| **Readiness level** | **Not ready** |
| **Fully implemented** | 0 |
| **Partially implemented** | 1 |
| **Planned** | 0 |
| **Not started** | 28 |
| **Not applicable** | 1 |
| **Total controls assessed** | 30 |

## Domain Scores

| Clause | Domain | Score |
|---|---|---:|
| **4** | Context of the organisation | 0% |
| **5** | Leadership | 0% |
| **6** | Planning | 0% |
| **7** | Support | 0% |
| **8** | Operation | 8% |
| **9** | Performance evaluation | 0% |
| **10** | Improvement | 0% |

The results are consistent with the scenario. Saltbush purchased and deployed an AI system, but there is very little evidence that an AI-specific governance structure was created around it.

Almost every control was rated **Not started**.

I made two exceptions:

- **8.3 AI system design and development** was marked **Not applicable** because Saltbush purchased the classifier from an external vendor and did not design or develop it.
- **8.7 AI system operation and monitoring** was marked **Partially implemented** because the vendor provides overall accuracy reports and HR records applicant complaints quarterly.

I only gave 8.7 partial credit because some monitoring activity exists. It does not mean the current monitoring is adequate.

The Clause 8 score of 8% therefore makes sense when compared with the detailed assessment. Most operational controls have not been implemented, one was treated as not applicable, and only one received partial credit.

---

## Comparing My Assessment with the HR Manager

The HR manager's assessment gave Saltbush a readiness score of **43%** and described the organisation as **Partially ready**.

Nothing about Saltbush changed between the two assessments. The difference came from how the available evidence was interpreted.

| Control | HR rating | What may have influenced the rating | What I would ask | My rating |
|---|---|---|---|---|
| **5.1 Leadership and commitment** | Fully implemented | The Board approved the purchase of the classifier. | What AI-specific leadership or oversight has occurred since the purchase was approved? | **Not started** |
| **5.3 Roles, responsibilities and authorities** | Partially implemented | Geoff was informally treated as the organisation's "AI guy." | Who is currently named and documented as responsible for the classifier now that Geoff has left? | **Not started** |
| **6.1.4 AI system impact assessment** | Not applicable | The organisation may have assumed an impact assessment was unnecessary because a recruiter makes the final decision. | Where is the decision not to conduct an impact assessment documented and justified? | **Not started** |
| **7.2 Competence** | Fully implemented | Recruiters received a vendor demonstration. | Did the training cover bias, limitations, human oversight and escalation, or only how to operate the software? | **Not started** |
| **8.5 Third-party relationships** | Fully implemented | Saltbush has a contract and an active relationship with the vendor. | Does the relationship include AI-specific risk management, fairness requirements, audit rights or access to subgroup performance information? | **Not started** |
| **8.7 AI system operation and monitoring** | Partially implemented | Vendor accuracy reports and quarterly complaint reporting already exist. | Are complaints and performance data reviewed together, and is there a defined point where the organisation must act? | **Partially implemented** |
| **9.1 Monitoring, measurement, analysis and evaluation** | Partially implemented | HR already records complaints and receives vendor accuracy information. | Does Saltbush measure fairness or selection rates between groups? | **Not started** |

### Which HR Rating Came Closest?

I agree most strongly with the HR manager's rating for **8.7 AI system operation and monitoring**.

The vendor provides accuracy reports and HR records complaints, so some form of monitoring does exist. However, the two sources of information do not appear to be connected, and there is no evidence that Saltbush monitors outcomes by demographic group.

For that reason, I think **Partially implemented** is reasonable, but there is still significant work required.

### Would Clause 9 Have Detected the Week 4 Fairness Gap?

No.

Nothing currently being measured by Saltbush appears capable of identifying the **60% versus 30% selection-rate difference** found in Week 4.

The vendor reports high overall accuracy, but overall accuracy and fairness are not the same thing. A model could have strong overall performance while still producing substantially different outcomes for particular groups.

Saltbush therefore needs group-level monitoring rather than relying only on an overall accuracy figure.

---

# Task 2 – Clause Mapping

I also mapped the main ISO/IEC 42001 clauses to practical actions Saltbush could take for the hiring classifier.

| Clause | Main purpose | What Saltbush should do | Evidence | NIST AI RMF |
|---|---|---|---|---|
| **4 – Context** | Understand the organisation, interested parties and scope of the AIMS. | Define which recruitment processes and applicant groups are covered and identify relevant stakeholders such as applicants, recruiters, HR, the vendor and regulators. | AIMS scope and stakeholder register. | **MAP** |
| **5 – Leadership** | Establish direction, policy and accountability. | Create an AI-specific policy and assign a current owner for the classifier. | AI policy and documented system owner. | **GOVERN** |
| **6 – Planning** | Identify risks, impacts and treatment actions. | Conduct an AI impact assessment that includes fairness risks and establish how identified risks will be treated. | Impact assessment and risk-treatment plan. | **MAP** |
| **7 – Support** | Provide resources, competence, awareness and documentation. | Train recruiters on the classifier's limitations, possible bias, appropriate human oversight and escalation procedures. | Training materials and completion records. | **GOVERN** |
| **8 – Operation** | Put the planned controls into practice. | Record recruiter overrides and routinely monitor group-level selection outcomes instead of relying only on vendor accuracy reports. | Override records and operational fairness reports. | **MANAGE** |
| **9 – Performance evaluation** | Monitor, measure, audit and review the AIMS. | Regularly review fairness metrics, conduct internal audits and include the classifier in management reviews. | Monitoring reports, audit records and management review minutes. | **MEASURE** |
| **10 – Improvement** | Correct problems and continually improve the system. | Connect complaints and monitoring findings to a corrective-action process with clear owners and completion dates. | Corrective-action register. | **MANAGE** |

One important connection exists between Clauses **6 and 9**. Clause 6 requires Saltbush to decide how AI risks will be assessed and treated, while Clause 9 requires the organisation to measure the system and determine whether those controls are actually working.

At the moment, Saltbush is weak in both areas.

---

# Task 3 – Reading an ISO/IEC 42001 Certificate

For this activity, I examined **Anthropic's ISO/IEC 42001:2023 certificate**.

The certificate itself was publicly accessible through Anthropic's Trust Center. However, the **Statement of Applicability (SoA)** referenced by the certificate required access to be requested.

## Certificate Findings

| Item | Finding |
|---|---|
| **Certificate holder** | Anthropic |
| **Certificate issuer** | Schellman Compliance, LLC |
| **Accreditation** | ANAB, the ANSI National Accreditation Board |
| **Original registration** | 6 January 2025 |
| **Current issue date** | 13 November 2025 |
| **Expiration** | 5 January 2028 |
| **Certificate version** | Version 2 |
| **Statement of Applicability referenced** | Version 1.4, dated 31 July 2025 |
| **Products/services named** | Claude large language models and deployments through the Claude Development Platform, Claude for Work and Claude Code, together with supporting AI research and development activities |
| **Access limitation** | Certificate was publicly accessible, but the Statement of Applicability required access to be requested |

## What Would I Check Before Trusting a Vendor's Certification?

A vendor saying **"we are ISO 42001 certified"** is not enough by itself.

Before relying on that claim, I would check three things.

1. **Does the certificate actually cover the product being purchased?**  
   The scope matters. A company may have certification for one part of its business without every product or service being included.

2. **Is the certificate current?**  
   I would check the issue and expiry dates and whether ongoing surveillance requirements are being met.

3. **What does the Statement of Applicability contain?**  
   The certificate shows that an AI management system has been certified within a particular scope, but the SoA provides important information about which controls are applicable and how they have been treated.

This activity showed me why certification should be treated as **evidence**, rather than automatic proof that a particular AI product is safe or suitable for every use.

A certificate also cannot tell Saltbush whether the classifier is producing a fairness problem today. That requires actual monitoring of the system's behaviour.

---

# Task 4 – Auditing a Statement of Applicability

Six months later, Saltbush produced a Statement of Applicability for the classifier.

I reviewed the entries against the supplied evidence and identified three that I do not think would survive a proper audit.

## A.2 Policies Related to AI

Saltbush claimed this control was included and used its **ICT Acceptable Use Policy** as evidence.

I do not think this is sufficient.

The policy covers general ICT issues such as passwords, internet use, personal devices, installing software and reporting security incidents. It was also last reviewed in **2019**, before the classifier was purchased.

It does not demonstrate that Saltbush has an AI-specific policy covering the hiring classifier.

### What Saltbush Would Need

Saltbush should create a current AI policy that covers issues such as:

- acceptable use of the classifier,
- human oversight,
- fairness,
- responsibilities,
- escalation, and
- monitoring.

---

## A.3 Internal Organisation

Saltbush used a Board minute approving the purchase of the classifier as evidence that responsibilities had been established.

I do not think a purchase approval demonstrates ongoing responsibility.

The scenario states that Geoff was previously treated as the informal "AI guy," but he has left and nobody has been formally named as responsible for the system.

### What Saltbush Would Need

Saltbush should have a current governance record, role description or similar document identifying:

- who owns the classifier,
- what they are responsible for,
- who monitors its performance, and
- who receives escalated concerns.

---

## A.5 Assessing Impacts of AI Systems

Saltbush excluded this control because a recruiter supposedly makes the final hiring decision.

I do not think this exclusion is justified.

The classifier influences who receives an interview, which can have a significant effect on applicants. The supplied evidence also indicates that recruiters process around **80 recommendations in approximately 20 minutes**, which raises questions about how much meaningful independent review is actually occurring.

The Week 4 fairness analysis also identified a **60% versus 30% selection-rate difference**, providing another reason why an impact assessment is necessary.

### What Saltbush Would Need

Saltbush should conduct and document an AI impact assessment covering the classifier's effect on applicants, including fairness and human oversight.

---

## Entries That Were Better Supported

Three entries were better supported by the evidence provided:

- **A.4 Resources for AI systems:** the supplier hosts and maintains the platform, which supports the specific claim being made.
- **A.8 Information for interested parties:** the careers page informs applicants that an automated tool is used and provides a contact channel.
- **A.10 Third-party and customer relationships:** contractual documents allocate responsibilities between Saltbush and the vendor.

However, an entry being supported does not automatically mean the underlying arrangement is good.

### Which Supported Entry Still Leaves Saltbush Exposed?

I think **A.10 Third-party and customer relationships** creates the greatest concern.

The contract places responsibility for determining whether the classifier's outputs are suitable onto Saltbush, while the vendor refuses to provide training-data details, subgroup performance information or model documentation because it considers that information commercially sensitive.

This leaves Saltbush responsible for the outcome while limiting its ability to independently assess the system.

I would recommend that Saltbush seek stronger contractual requirements around:

- fairness testing,
- subgroup performance information,
- audit rights, and
- access to information needed to assess AI risk.

### Where Should the Vendor's Refusal to Provide Information Be Recorded?

The vendor's refusal to provide information about training data and subgroup performance is particularly relevant to **A.7 Data for AI systems**.

Saltbush should document that it requested the information, that the vendor declined to provide it, and what this means for Saltbush's ability to assess the classifier.

Leaving that evidence out of the Statement of Applicability would make the document appear stronger than the actual governance arrangements.

---

# Task 5 – Designing and Stress-Testing a Monitoring Trigger

The final activity required a monitoring rule that could identify a future fairness problem without overreacting to very small samples.

## Version 1

My initial rule was:

> Calculate each group's selection rate at the end of every month. If any two groups differ by more than 10 percentage points, notify the AI governance lead within two business days and review the affected recruitment round within five business days.

I then tested the rule against three different recruitment periods.

## March

March had only **9 applicants**, with **3 applicants in Group B** and none shortlisted.

This produced a large selection-rate difference, but the sample was extremely small. With only three people in Group B, changing the outcome for one applicant would move the group's selection rate by more than 30 percentage points.

The first rule could therefore generate an escalation based largely on small-sample variation.

## November

November had approximately **2,400 applicants across 60 sites over nine days**.

The organisation-wide selection rates were:

- **Group A:** 41%
- **Group B:** 38%

The three percentage-point difference would not trigger the rule.

However, a monthly organisation-wide check creates another problem. A large recruitment campaign could begin and finish before the monthly review occurs, and problems at individual sites could be hidden inside the overall result.

## June

June had approximately **300 applicants**.

The selection rates were:

- **Group A:** 44%
- **Group B:** 31%

The **13 percentage-point difference** would trigger the first rule.

This appears more useful because the sample is larger. However, the June data also contained another group with only four applicants, which creates the same small-sample problem identified in March.

---

## Version 2

After testing the first rule, I revised it.

> Calculate group selection rates weekly using a rolling 30-day window and review the results both organisation-wide and by site. A full escalation occurs when the organisation's documented fairness threshold is exceeded and both groups have enough observations for the comparison to be meaningful. Results involving smaller groups should still be recorded and reviewed over a longer rolling period so they are not ignored simply because the group is small.

I prefer this version because it addresses the main weaknesses identified during testing.

- **March:** the small Group B result is recorded and monitored without immediately treating three applicants as strong evidence of a system-wide problem.
- **November:** weekly and site-level monitoring reduces the risk that a short recruitment campaign or local problem disappears inside a monthly organisation-wide average.
- **June:** the larger Group A and Group B difference would still require investigation, while the very small third group would continue to be monitored over a longer period.

The organisation would still need to define and justify the actual fairness threshold and minimum sample requirements as part of its risk-management process. I would not choose those values simply because they make the current data pass or fail.

---

# Week 5 Reflection

This week showed me the difference between **having AI-related documents and actually having AI governance**.

Saltbush already had many things that could make the organisation appear governed. The Board approved the purchase, recruiters received a demonstration, a vendor contract exists, accuracy reports are supplied, complaints are recorded and responsibilities appear in parts of the contract.

The problem is that most of those things do not provide evidence of the specific controls ISO/IEC 42001 is asking for.

A Board approving a purchase is not the same as ongoing leadership. A software demonstration is not the same as training staff about AI risks. Having a vendor contract does not mean third-party AI risk is properly managed. High overall accuracy also does not prove the system is fair.

I found the Statement of Applicability activity particularly useful because it demonstrated how governance documentation can look convincing until the evidence behind each claim is examined.

The biggest lesson for me is that **AI assurance depends on evidence**. An organisation needs to be able to show not only that a policy, process or control exists, but that it actually applies to the AI system being assessed and is working as intended.

This also connects directly with Week 4. The 60% versus 30% selection-rate gap was not difficult to calculate, but Saltbush's existing governance processes would never have looked for it. ISO/IEC 42001 provides a structure for making sure risks like that are identified, measured, reviewed and acted on instead of being hidden behind an overall accuracy figure.

---

# References

- International Organization for Standardization. (2023). *ISO/IEC 42001:2023 Information technology – Artificial intelligence – Management system*. ISO.
- National Institute of Standards and Technology. (2023). *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*.
- VerifyWise. (2026). *ISO 42001 Gap Analysis Tool*.
- Anthropic. (2026). *Trust Center: ISO/IEC 42001 certification*.

---
