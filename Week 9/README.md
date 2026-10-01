# Week 9 – Organisational Governance of AI

## Overview

This week focused on the people and decision-making processes an organisation needs around its AI systems.

The activities returned to Saltbush Group. Earlier weeks identified a 60% versus 30% selection-rate gap in its hiring classifier and examined the governance controls that should surround it. Saltbush has now appointed Dev Raman as Head of AI, but still does not have a complete picture of the AI being used across the organisation.

I reviewed its software list, vendor release notes, purchase records and staff messages to identify AI systems. I then prepared an AI register, proposed system owners and screening outcomes, and reviewed the Governance and compliance section of the HR manager's draft AI policy.

I also drafted a replacement Governance and compliance section. The Moodle lesson reached its end with **6 out of 6 knowledge-check answers correct (100%)**. That result records the online lesson checks; it does not establish tutorial attendance or tutor-awarded portfolio marks.

The main issue is that AI governance needs to reach the people who purchase systems, manage business processes, review outcomes and respond to complaints. Appointing a Head of AI does not resolve those responsibilities by itself.

## Task 1 – Finding the AI

### What Counts as an AI System?

I applied the definition in the National AI Centre's AI policy template. The distinction is whether a system uses data to infer an output, such as a prediction, recommendation or generated response, with some autonomy. Ordinary spreadsheet calculations, fixed-rule macros and traditional reporting dashboards are excluded by the template.

The name of a product is not enough to decide. The release notes and the way staff actually use it matter. [National AI Centre, AI policy guide and template](https://www.ai.gov.au/sites/default/files/2026-06/AI-policy-guide-and-template.docx).

### Reviewing the Software List

| Item | AI system? | Reason |
| --- | --- | --- |
| Recruitment platform, shortlisting module | Yes | The classifier ranks applicants and recommends who should receive an interview. |
| RouteWise 5.2 | Yes | Its release notes describe machine learning that uses delivery history, traffic and weather to predict arrival windows and optimise routes. |
| ShiftSmart 3 | Yes | Auto-Roster uses predictive analytics, worker reliability scores, pick rates and predicted absence to allocate shifts. |
| Where's My Parcel chat | Yes | Version 2.1 uses a large language model to generate answers from tracking data and delivery/refund policies. |
| Microsoft 365 | Yes, for the Copilot feature | Copilot has been enabled for office staff and generates summaries from workplace information. This does not make every Microsoft 365 function an AI system. |
| PayMaster | No, on the supplied evidence | It calculates pay from timesheets and award rates. No inference or learned prediction is described. |
| Stock reorder workbook | No, on the supplied evidence | The workbook uses standard Excel formulas to calculate reorder quantities. |
| Sales performance dashboard | No, on the supplied evidence | It reports weekly sales by store and region. No predictive or generative feature is described. |
| Invoice routing macro | No, on the supplied evidence | It moves invoices into folders using a fixed rule based on supplier name. |
| Warehouse management system | No, on the supplied evidence | StoreTrack is described as managing stock locations and barcode scanning. No AI capability is shown. |

These exclusions are based on the functions described in the pack. They would need to be revisited if a supplier added predictive features or staff began using the systems differently.

### AI Outside the Software List

I identified two additional items.

| Item | Status | Why it belongs in the register |
| --- | --- | --- |
| Free AI interview notetaker | In use without approval | Recruiters record interviews on their phones, generate notes and paste the summaries into the recruitment platform. The app and provider are not identified. |
| Candidate Insights add-on | Proposed | The vendor proposes analysing recorded interviews to score enthusiasm and confidence. A quote exists, but it has not been approved. |

The six electric forklifts also appear in the purchase records. Being electric does not make a forklift an AI system, and the scenario provides no evidence of autonomous operation or AI features.

This gives **seven AI systems or proposed features** from Dev's evidence pack: five from the software list and two from the other records.

### Why the Purchase Records Matter

ShiftSmart was approved as a software upgrade and Copilot as a licence adjustment. Those descriptions hide the significance of the new capabilities.

ShiftSmart now makes recommendations about workers' shifts. Copilot makes existing organisational information easier to retrieve and summarise. Both changes should have triggered AI screening even though the purchases were made through ordinary software processes.

A financial approval tells me that somebody approved expenditure. It does not establish that fairness, privacy, security or human oversight were assessed.

### Completing the AI Register

I recorded all seven systems in the National AI Centre's template and added the required Topic 3 tool, giving eight exercise entries. I retained the template's description and example rows.

For each entry, I recorded its name and known version, operational status, supplier, purpose, intended use, limitations, prohibited uses, foreseeable misuse, data and affected stakeholders. Missing versions and unknown providers are recorded explicitly.

The register date is **1 October 2026**, the date this portfolio register was prepared. It is not a claim that Saltbush registered these systems on that date.

### Bringing Forward the Topic 3 Tool

My [Week 3 portfolio](https://github.com/mrchristopherhen/AI-Governance-and-Assurance/tree/main/Week%203) identifies **OpenAI ChatGPT**, examined as a consumer product while signed out.

For this week's hypothetical extension, I assumed Saltbush customer-service staff have begun pasting customer enquiry emails into consumer ChatGPT to draft replies without approval. That use is an assumption for the activity; it is not part of Dev's evidence pack.

I recorded the model/version as unknown. I would also check the current account arrangements, provider terms and privacy controls before approving the use. The observations recorded in Week 3 should not be treated as a fresh test of today's settings.

## Task 2 – System Owners and Screening Outcomes

I selected people whose existing roles give them responsibility for the business process or shared service involved. These are proposed assignments for the activity, rather than evidence that Saltbush has already appointed them.

The screening categories are Saltbush's internal **normal, elevated and prohibited** categories. They are not a direct replacement for the EU AI Act's legal classifications. An elevated internal screening outcome can be justified by privacy, customer or operational risks even when a use does not fall within an EU high-risk category.

| AI system | Proposed system owner | Screening outcome | Reason | Governance Committee approval? |
| --- | --- | --- | --- | --- |
| Recruitment shortlisting module | Kath Brennan, HR Manager | Elevated | It influences access to interviews, and the earlier fairness gap needs investigation and controls. | Yes, review and reapproval with evidence of fairness testing and meaningful recruiter oversight. |
| RouteWise 5.2 | Lina Haddad, Transport Planning Manager | Normal | Its stated use is operational route planning and arrival prediction. | No routine committee approval under a documented delegation. Escalate safety concerns or a change to worker assessment. |
| ShiftSmart 3 | Mele Taufa, Warehouse Operations Manager | Elevated | It allocates shifts using personal scores and absence predictions, with a reported adverse outcome after carer's leave. | Yes, including fairness, employment, privacy and human-review controls. |
| Where's My Parcel chat 2.1 | Grace Mbeki, Customer Experience Manager | Elevated | It generates customer-facing statements about tracking and refund policies, creating accuracy and privacy risks. | Yes, before reapproval of the stated customer-facing scope. |
| Microsoft 365 Copilot | Anh Tran, IT Manager | Elevated | It has broad organisational reach and has surfaced confidential HR information to a finance analyst. | Yes, with an access review, information-owner input and controlled use cases. |
| Free interview notetaker | Sam Whitford, Recruitment Lead | Elevated | It processes interview recordings without an established approval or verified safeguards. | Yes, before any approved restart. Pause new recordings while the use is assessed. |
| Candidate Insights | No operational owner required for a prohibited use | Prohibited | The proposed enthusiasm/confidence scoring raises workplace emotion-inference concerns. | No approval to deploy. The committee and Legal should record the rejection and close the proposal. |
| Consumer ChatGPT, hypothetical customer-email drafting | Grace Mbeki, Customer Experience Manager | Elevated | The assumed use sends customer information to an unapproved external service. | Yes, before permitting this use with personal information. |

### Why I Did Not Allocate Every System to Dev

Dev should coordinate AI governance, support screening and ensure that the framework works across Saltbush. He cannot personally manage every recruitment decision, roster, customer response and document permission.

Kath has authority over recruitment. Lina understands transport operations. Mele manages the distribution centres. Grace owns the customer-service processes, and Anh manages the shared Microsoft 365 environment.

Sam is a suitable proposed owner for resolving the notetaker issue because he leads the recruiters using it. He would need documented authority to stop the practice and implement an approved alternative, with Kath's support. Naming him does not retrospectively approve the app.

For ShiftSmart, Mele should work with Niamh Kelly in Dublin, HR and Legal. The organisation-wide owner remains clear while local responsibilities are documented.

### Borderline Screening Decisions

I classified RouteWise as normal for the use described. That still requires a named owner, proportionate checks and a way for planners or drivers to challenge unsuitable routes. If Saltbush started using its predictions to rate drivers or impose unsafe schedules, I would rescreen it.

I took a more cautious view of Where's My Parcel. A tightly restricted tracking assistant could reasonably receive normal screening, but this version generates answers about refund policies. I chose elevated until Saltbush has tested its answers, disclosure, privacy controls and escalation to staff.

A screening decision should be based on the actual use and potential harm, with its reasoning recorded. It should not be chosen simply because a product looks familiar.

### Candidate Insights and the EU AI Act

I retained a prohibited outcome for the proposed emotion-scoring use. EU guidance explains that the workplace emotion-recognition prohibition can cover recruitment. Its application depends on the technical basis, including biometric data, and the relevant jurisdiction. The brochure does not establish every technical detail, so Legal would need to confirm those details rather than infer them from the product name. No medical or safety purpose is described. [European Commission, prohibited AI practices guidance, section 7](https://ai-act-service-desk.ec.europa.eu/sites/default/files/2025-08/guidelines_on_prohibited_artificial_intelligence_practices_established_by_regulation_eu_20241689_ai_act_english_ied3r5nwo50xggpcfmwckm3nuc_112367-1.PDF).

Saltbush should keep the proposal in its register with the reason for rejection. The Governance Committee can review whether the classification is correct; it cannot approve an exception to an applicable legal prohibition.

### Responding to the Staff Messages

| Report | What it establishes | My proposed response |
| --- | --- | --- |
| Recruiters use a free interview notetaker | Unapproved AI use and a flow of interview audio to an unidentified provider. | Sam should pause new recordings, identify the apps and accounts, preserve relevant records, and work with Farah and Anh to assess notice, permissions, retention, security and any required incident response. |
| A worker receives worse shifts after carer's leave | A credible concern about an adverse outcome and a weak escalation pathway. It does not prove the cause or unlawful discrimination. | Mele should arrange human review of the roster, investigate relevant data and scoring, consult HR and Farah, and provide a route to challenge and correct unfair outcomes. |
| Copilot retrieves an HR redundancy document | A reported confidentiality/access concern. It does not establish that Copilot bypassed permissions. | Anh and the HR information owner should check access permissions, sharing, logs and scope of exposure. Farah should assess privacy implications and Rob should track the incident and corrective actions. |

For the hypothetical ChatGPT use, I would stop identifiable customer information being entered while the use is reviewed and offer an approved way to draft replies using suitable data. This is consistent with the OAIC's recommendation against entering personal, especially sensitive, information into public generative AI tools. [OAIC guidance](https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-the-use-of-commercially-available-ai-products).

## Task 3 – Reviewing Kath's Draft AI Policy

Kath's draft creates some useful starting points. It recognises a need for approval and gives RouteWise and the customer chatbot named owners. However, it leaves important gaps in authority, independent review, coverage and incident handling.

I identified the following faults. Where the source does not prescribe a particular organisational design, I have explained my reasoning rather than presenting my recommendation as a mandatory rule.

| Fault | What is wrong and why it matters | Source or reasoning and proposed improvement |
| --- | --- | --- |
| 1. No clear AI policy owner | Dev is described as an adviser. Nobody is explicitly given authority to govern AI across business areas. | The NAIC template separates policy ownership from advice. Appoint Dev as policy owner with executive-backed authority, resources and escalation rights. Keeping budgets in business areas can work if these powers are clear. |
| 2. Policy approval is confused with tool approval | The policy approvers entry says Helen signs off every new tool. It does not identify who approves the policy or its revisions. | These are different decisions in the NAIC template. Specify the policy approver and separately define system approval delegations. |
| 3. Kath monitors decisions she helps make | Kath chairs the committee, requests HR products and acts as compliance monitor. She would be checking arrangements in which she has a direct interest. | This is my assessment of a self-review risk. Allocate compliance monitoring to Rob Ellery and preserve an independent route for challenge, especially for HR systems. |
| 4. The committee lacks relevant perspectives | HR has both Kath and Sam, while Risk and Compliance, Legal/Privacy and Operations are absent despite operational and employee risks. | The AICD/HTI guide supports cross-functional expertise. Include Rob, Farah, Anh and relevant business representatives, with conflicts managed. A fixed membership list is my design recommendation. |
| 5. Every tool follows a slow approval route | A quarterly committee and CEO sign-off for everything could create delays as the inventory grows to 50 systems. Urgent issues have no faster route. | My scalability assessment: use risk-based delegation, timely elevated-risk review and an urgent escalation process. A quarterly meeting can remain useful for oversight, but should not be the only decision opportunity. |
| 6. Privacy work is duplicated and misallocated | The committee conducts a full privacy review even though Farah already conducts privacy impact assessments for systems handling personal information. | Dev's organisation chart identifies an existing specialist process. Keep Farah responsible for that assessment; the committee should use its findings alongside fairness, safety and other risk evidence. |
| 7. The classifier has a committee as its owner | Collective oversight does not identify the person who must arrange testing, monitor results and organise corrective action. | The activity and NAIC template call for a person accountable for each system. Assign Kath as proposed owner, with Sam managing recruitment operations and the committee providing oversight. |
| 8. Candidate Insights is treated as approvable | The draft marks it elevated and pending approval despite the proposed emotion-scoring use. | Apply the prohibited outcome discussed in Task 2. Record the reason, obtain Legal's scope confirmation and prevent procurement or activation. |
| 9. The system list is incomplete | ShiftSmart, Copilot and the free interview notetaker are missing. | The release notes, purchases and staff messages establish these uses. Add them, identify owners and assess existing deployment. Include the hypothetical Topic 3 tool for this exercise. |
| 10. Intake covers only new tools and is burdensome | A 12-page form for every request may encourage people to bypass governance. It also misses new features, changed uses and shadow AI already running. | The evidence shows that upgrades and informal use introduced AI. Start with short triage and require detail proportionate to risk. Screen new uses and significant changes as well as purchases. |
| 11. Staff duties and incident handling are inadequate | The draft omits the all-personnel role and assumes owners will notice anything unusual. The warehouse complaint shows why this fails. | The NAIC template includes staff training/reporting and incident procedures. Give staff a clear reporting channel, escalation route and protection from having concerns ignored. Define investigation, containment, stop authority and manual alternatives. |
| 12. Monitoring, review and vendor responsibilities are unclear | There is no policy review cycle, reporting process or explanation of how vendor obligations connect to Saltbush's responsibilities. | Add review triggers, monitoring records and documented supplier responsibilities. The NAIC template covers review and third-party accountability; the AICD/HTI guide supports reporting to leadership. Vendor technical support does not replace Saltbush's ownership of its use. |

The principal sources for this review were the [NAIC policy template](https://www.ai.gov.au/sites/default/files/2026-06/AI-policy-guide-and-template.docx), the [AICD/HTI guide, pages 27 and 31–34](https://www.aicd.com.au/content/dam/aicd/pdf/news-media/research/2026/director-guide-to-ai-governance.pdf), and the [Moodle evidence pack and draft policy](https://moodle.federation.edu.au/mod/lesson/view.php?id=9121455).

## Task 4 – Writing a Better Governance and Compliance Section

The following is my proposed replacement for Saltbush's Governance and compliance section. It uses the three headings requested in the activity. The roles and processes below are policy proposals for the fictional scenario.

### Roles and Responsibilities

| NAIC role | Proposed allocation | How it would work at Saltbush |
| --- | --- | --- |
| AI policy owner | Dev Raman, Head of AI | Maintains the policy and coordinates governance across business areas, with authority granted by the CEO and Board. |
| Policy approvers | Board of Directors, chaired by Margaret Oduya | Approves the policy, risk appetite and substantive policy changes. Helen implements the framework through management. |
| Compliance monitor | Rob Ellery, Risk and Compliance Manager | Checks evidence, follows incidents and corrective actions, and reports concerns. Staff should not independently audit work they designed or approved; an independent reviewer is needed where conflicts arise. |
| AI governance committee / authority | Dev as chair, with Rob, Farah, Anh and relevant business representatives | Reviews elevated uses and disputes, documents decisions and conditions, and escalates material matters. System owners present evidence; conflicted members do not approve their own proposal without independent challenge. |
| AI system owner | The named individuals in Task 2 | Remain accountable for each system's operation, documentation, monitoring and corrective action throughout its lifecycle. |
| All employees and volunteers, including contractors within scope | Everyone using or affected by the policy | Uses approved tools within approved purposes, completes training and reports incidents or unexpected outcomes through the stated channels. |

The Board and CEO retain their own oversight and management responsibilities. Business areas retain delivery budgets, but must fund the controls required for their approved uses. Dev may require additional assessment and escalate unresolved resourcing or risk disputes to Helen and the Board.

Rob will report material incidents, missing assessments, overdue actions and unresolved concerns to Dev and the committee, with direct escalation to Helen or the Board where necessary. A quarterly board report will cover the AI inventory, significant changes, incidents, monitoring results and corrective actions. Serious concerns must be escalated promptly rather than held for that report.

Vendors must have documented responsibilities for supplying information about capabilities and limitations, supporting testing, notifying Saltbush of material changes, reporting incidents, supporting investigation and providing agreed disablement or rollback arrangements. System owners must obtain and review that evidence. Saltbush remains accountable for how it deploys and uses the system.

Dev will lead an annual policy review and an earlier review after a significant incident, material change in AI use or relevant legal change. Substantive revisions require Board approval. These reporting intervals and delegations are my proposed design for Saltbush.

### New AI Use Case Procedures

Staff must submit a short initial screening record to Dev before procuring, enabling or materially changing an AI use. The record must identify the purpose, data, affected people, supplier and proposed accountable owner. Dev coordinates screening with the owner and seeks Farah's legal/privacy advice and Rob's risk advice where needed.

| Screening outcome | Required route |
| --- | --- |
| Normal | The named owner approves within documented delegated authority after proportionate assessment, testing and registration. Matters outside the delegation or with unresolved risks go to Dev. |
| Elevated | The owner provides an impact/risk assessment, relevant privacy and security reviews, test results, monitoring plan and human-oversight arrangements. The Governance Committee records approval, conditions or rejection before deployment or reapproval. |
| Prohibited | The use must not proceed. Record the rejected proposal and reason, and refer any classification dispute to Farah and the Governance Committee. Neither a budget approval nor CEO sign-off can override an applicable legal prohibition. |

The committee must provide timely decisions between scheduled meetings when needed. Members with a conflict must disclose it and must not provide the sole approval for their own proposal. Helen resolves resourcing disputes and refers matters outside the organisation's risk appetite to the Board, without authorising a prohibited use.

The process applies to embedded features, vendor upgrades, changed purposes and unapproved AI discovered after deployment. Existing use must be registered and reviewed. The owner, with Dev and the committee, must decide and document whether interim restrictions, human review or suspension are needed while approval is resolved.

Farah's existing privacy impact assessment process will supply the privacy review where required. The committee will use that work rather than commission a duplicate review. Approval is conditional on the documented use, data and controls; significant changes require rescreening.

### Incident Management

All personnel must be able to report concerns through a clearly published AI concern form or service-desk route, or directly to the system owner or Rob. Reports must be accepted even when staff cannot identify the system or prove the cause. Training must explain this process and staff must be able to bypass an unresponsive or conflicted owner.

Rob will log reports and track them to resolution. The owner must assess impact, preserve relevant evidence and arrange containment. Owners and Anh must have documented authority and technical means to pause unsafe operation; a serious incident must not wait for a committee meeting. Critical processes must have an available manual alternative.

For the warehouse complaint, this policy would work as follows:

1. The team leader reports the concern to Mele or directly to Rob if the owner is unavailable or the concern is not being addressed.
2. Mele arranges prompt human review and preserves the relevant roster, input data and decision records.
3. HR and Farah assess the employment and privacy implications, with Niamh involved for Dublin where relevant.
4. Mele, supported by Anh and the supplier, can suspend automated rostering and use a documented manual process if continuing poses unacceptable risk.
5. Rob tracks the investigation and corrective actions. Dev and the committee receive material issues promptly, with serious matters escalated to Helen and the Board.
6. The affected worker receives an explanation and a way to challenge the outcome. The owner verifies that any correction has addressed the problem.

Farah determines applicable legal notification and redress requirements. The owner communicates with affected people as appropriate and records the investigation, cause, actions and evidence of effectiveness. Elevated systems need committee approval for restart after a material incident, supported by testing and updated controls. Rob checks that actions are closed, and Dev incorporates lessons into policy and training.

The scenario does not establish that these controls currently exist or that the reported shift pattern has already been investigated.

### Reducing Shadow AI

A long form and a blanket warning would not address why recruiters adopted the notetaker in the first place. They wanted to save time.

Saltbush should provide a practical route to request useful tools, clear rules about permitted information, suitable approved alternatives and training based on real work. It should also ask staff about informal AI use and check procurement and software changes so that its register stays current.

Reporting needs to be easy enough that staff will raise concerns before harm spreads. The finance analyst's message and the warehouse team leader's complaint are useful governance evidence, even though neither is a completed investigation.

## Week 9 Reflection

This week connected the earlier risk and fairness activities to the people who need to act on their findings.

The most useful part was comparing the software list with the release notes and staff messages. The software list made ShiftSmart look like ordinary rostering software. The release notes showed that it used predictions about workers, and the staff message raised a concern about a real consequence within the scenario. Each source added information that the others did not provide.

The same issue appeared with Copilot. Approving more Microsoft licences may seem routine, but the resulting access to organisational information can expose weaknesses in data permissions. The appropriate response is to investigate the configuration and information access, rather than assume that the model itself bypassed security.

I also found that giving somebody a title does not automatically give them authority. Dev cannot coordinate AI governance effectively if he can only advise while every business area makes its own decisions without common rules. System owners need enough authority, knowledge and resources to carry out their responsibilities, and compliance monitoring needs a route to challenge those decisions.

The policy review showed why governance has to be practical. A committee that meets quarterly, a 12-page intake form and CEO approval for every tool may appear thorough, but those arrangements can become a bottleneck. A proportionate process should make routine approvals manageable while giving elevated risks more scrutiny and preventing prohibited uses.

The strongest connection to Week 5 is the need for evidence. The AI register makes systems visible, but recording an owner or a screening category is only the starting point. Saltbush still needs assessments, testing, monitoring, reporting and corrective action that work in practice.

For me, the key question is now: when an AI system causes a problem, can the organisation identify who must respond, what authority they have, where concerns go and how affected people obtain a remedy?

## References

- Federation University Australia. (2026). [Topic 9 – Lab Activity – Org Structures and Roles](https://moodle.federation.edu.au/mod/lesson/view.php?id=9121455). ITECH2119 Moodle. Scenario evidence and Tasks 1–4; university login required.
- National AI Centre. (2026). [AI policy guide and template](https://www.ai.gov.au/sites/default/files/2026-06/AI-policy-guide-and-template.docx).
- National AI Centre. (2026). [AI systems register and spreadsheet template](https://www.ai.gov.au/staying-safe-and-responsible/essential-ai-practices/ai-systems-register).
- National AI Centre. (n.d.). [Guidance for AI adoption: implementation guidance](https://www.ai.gov.au/staying-safe-and-responsible/essential-ai-practices/guidance-ai-adoption-implementation-guidance).
- Australian Institute of Company Directors & Human Technology Institute. (2026). [A director's guide to AI governance](https://www.aicd.com.au/content/dam/aicd/pdf/news-media/research/2026/director-guide-to-ai-governance.pdf) (Version 2, pp. 27, 31–34).
- European Commission. (2025). [Guidelines on prohibited artificial intelligence practices established by Regulation (EU) 2024/1689](https://ai-act-service-desk.ec.europa.eu/sites/default/files/2025-08/guidelines_on_prohibited_artificial_intelligence_practices_established_by_regulation_eu_20241689_ai_act_english_ied3r5nwo50xggpcfmwckm3nuc_112367-1.PDF) (Section 7).
- Office of the Australian Information Commissioner. (2025). [Guidance on privacy and the use of commercially available AI products](https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/guidance-on-privacy-and-the-use-of-commercially-available-ai-products).
- [Week 3 – Australian Law, Privacy and AI Systems](https://github.com/mrchristopherhen/AI-Governance-and-Assurance/tree/main/Week%203). Earlier portfolio entry used to identify the previously audited tool.
