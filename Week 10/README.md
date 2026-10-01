# Week 10 – Assurance and Quality Management

## Overview

This week focused on what happens after an AI system has been approved and deployed. Approval is based on the evidence available at a particular time. Monitoring is needed to check whether the system continues to meet its requirements as the data, users and operating conditions change.

The activity returned to Saltbush Group one year after the governance work in Week 9. Following the earlier 60% versus 30% selection-rate gap, the vendor retrained the recruitment classifier. Its October test produced selection rates of 44% for Group A and 41% for Group B.

The AI Governance Committee approved the new version with a specific fairness condition: no group's selection rate could be more than 10 percentage points below the highest group's.

I examined twelve months of monitoring results, compared the recruitment team's summary with the underlying figures, considered the effect of small samples and applied ISO/IEC 42001 Clause 10.2 to the findings. I then used the owners and escalation arrangements proposed in Week 9 to explain who should act.

I reached the end of the Week 10 Moodle lesson, with both completion requirements marked done: viewing the lesson and going through the activity to the end. This records lesson completion; portfolio assessment and tutor marks remain separate.

## Task 1 – Comparing the Summary with the Monthly Data

### My Initial Reading of the Summary

If I only read the summary provided to Dev, I would conclude that the classifier was meeting its targets and did not need intervention.

| Summary measure | Reported result | Reported target/status |
| --- | --- | --- |
| Applicants processed | 6,500 | No target stated |
| Agreement with recruiters | 94.2% twelve-month average, compared with 91% in October | At least 85%; green |
| Group A–B selection-rate gap | 7.0 percentage-point twelve-month average | No more than 10; green |
| Availability | 99.8% | At least 99.5%; green |
| Average response time | 1.3 seconds | Under 2 seconds; green |

The summary also states that every measure has remained green, that Christmas recruitment ran without problems and that no action is needed.

Those conclusions are stronger than the evidence supports.

### Calculating the Monthly Fairness Gap

For Group A and Group B, I calculated:

`Gap in percentage points = Group A selection rate − Group B selection rate`

Group A has the higher reported rate in every month, so a result above 10 breaches the approval condition for Group B.

| Month | Applicants | Group A rate | Group B rate | A–B gap | A–B comparison against the condition |
| --- | ---: | ---: | ---: | ---: | --- |
| October | 310 | 44% | 41% | 3 pp | Within threshold |
| November | 2,720 | 42% | 40% | 2 pp | Within threshold |
| December | 280 | 45% | 41% | 4 pp | Within threshold |
| January | 350 | 44% | 40% | 4 pp | Within threshold |
| February | 330 | 45% | 40% | 5 pp | Within threshold |
| March | 320 | 45% | 39% | 6 pp | Within threshold |
| April | 340 | 46% | 39% | 7 pp | Within threshold |
| May | 360 | 46% | 38% | 8 pp | Within threshold |
| June | 350 | 46% | 37% | 9 pp | Within threshold |
| July | 370 | 47% | 36% | **11 pp** | **Breach** |
| August | 380 | 47% | 35% | **12 pp** | **Breach** |
| September | 390 | 47% | 34% | **13 pp** | **Breach** |

The annual figure is arithmetically reproducible:

`(3 + 2 + 4 + 4 + 5 + 6 + 7 + 8 + 9 + 11 + 12 + 13) ÷ 12 = 7.0 pp`

However, that is the mean of twelve monthly gaps. It conceals the recent deterioration and three consecutive months above the threshold. It does not demonstrate that the classifier remained within its approval condition.

The criterion applies to every group. The summary only compares A and B, so it also leaves out Group C. Passing the A–B comparison alone would not establish compliance with the full condition.

### What the Summary Leaves Out or Misrepresents

| Issue | What the monthly evidence shows | Why it matters |
| --- | --- | --- |
| A widening fairness gap | The A–B gap rises from 3 pp in October to 13 pp in September. It exceeds 10 pp from July onwards. | A favourable annual average hides current nonconformity. |
| Group B's declining selection rate | Group B falls from 41% to 34%, while Group A rises from 44% to 47%. | Looking only at the difference misses the direction of each group's outcomes. |
| Group C is absent | In August, none of its three applicants is shortlisted. | All groups are covered by the criterion. Small numbers require careful interpretation, not exclusion. |
| Complaints increase | Complaints rise from 2 in October to 11 in September; 58 are recorded across the year. | Feedback may reveal harms that the vendor dashboard does not measure. |
| Overrides fall | Overrides decrease from 9% to 3%, while agreement increases from 91% to 97%. | These measures are complements, not independent evidence that the model and recruiters have both improved. |
| Recruitment context changes | Dublin contributes no applicants in October–December, then rises from 20 in January to 130 in September. | The applicant mix changes, but there are no location-level selection rates to assess the effect. |
| Christmas is presented as problem-free | November processes 2,720 applicants and records five complaints, 96% agreement and 4% overrides. | Low aggregate disparity and smooth processing do not establish that review was meaningful or that no applicant experienced a problem. |

November accounts for about **41.8% of all applicants**. The 94.2% agreement figure matches an equal-month average, rounded to one decimal place. It is not labelled as an applicant-weighted annual rate. Monitoring reports should state how their averages are calculated.

Complaint counts also need denominators. October has about **0.65 complaints per 100 applicants**, compared with **2.82 in September**. The increase is therefore not explained simply by September having more applicants. Even so, the supplied data does not link individual complaints to application dates, groups, locations or particular outcomes. These rates are descriptive signals for investigation, not confirmed rates of model-caused harm.

### Four Types of Monitoring

| Monitoring type | Does Saltbush monitor anything relevant? | Does it appear in the summary? | My assessment |
| --- | --- | --- | --- |
| Performance | It records agreement with recruiters, but no independently established ground truth, precision or recall is supplied. | Agreement is included and marked green. | The reported measure is not a validated measure of prediction accuracy. |
| Fairness | It records monthly A/B selection rates and Group C shortlist counts. | Only the annual A–B average appears. | The summary removes the trend, recent breaches and Group C. |
| Operational | Availability and response time are reported. | Both appear and meet their stated targets. | These support claims about service operation, not fairness or decision quality. Monthly operational detail is not supplied. |
| Feedback | Recruiter overrides are recorded and HR separately logs complaints. | Complaints are omitted. Agreement indirectly reflects the inverse of overrides, but no override trend or reasons are shown. | Useful warning signals are collected but not brought together in the review. |

### Why Agreement Is Not Ground Truth

The activity defines agreement as the percentage of recommendations recruiters leave unchanged. Overrides are the percentage they change. They add to 100% in every supplied month.

A recruiter might leave a recommendation unchanged because it is sound. They might also do so because they trust the system too much, are under time pressure or do not have enough information to challenge it.

The pattern is consistent with possible automation bias or reduced scrutiny, which connects with Topic 7. It does not prove that explanation. Saltbush would need evidence such as review times, override reasons, recruiter workload, interviews with staff and an independent review of sampled cases.

To assess performance, I would define an appropriate reference outcome for the intended shortlisting task and have qualified reviewers assess a representative sample without seeing the classifier's recommendation first. The review should include rejected applicants and different groups and locations. Historical hiring decisions should not automatically be treated as unbiased ground truth.

### Applying Clause 9.1

The Clause 9.1 extract in the activity asks the organisation to specify what it measures, the methods it uses, when measurement happens and when results are evaluated, with documented evidence retained.

Saltbush collects monthly figures, but the annual summary shows why collection alone is insufficient. The organisation also needs a scheduled review that tests the actual approval condition, identifies breaches and sends them to somebody with authority to act.

I would retain the monthly rates and denominators, report all groups, connect complaints and overrides to the same review, and record the resulting decisions. The annual committee review should evaluate that ongoing process rather than be the first time the monthly deterioration becomes visible.

Source for the scenario, monthly figures and clause extracts: [Federation University, Learning activity – Topic 10](https://moodle.federation.edu.au/mod/lesson/view.php?id=9128317).

## Task 2 – Trend or Noise?

### Group C in August

Group C has no shortlisted applicants out of three in August, giving a selection rate of 0%.

This is an isolated result from a very small sample. In every other supplied month, Group C's rate is either 40% or approximately 42.9%. Its September result returns to three shortlisted out of seven.

With only three applicants, changing the outcome for one person changes the August rate by **33.3 percentage points**. That makes the monthly percentage highly unstable.

For the activity's trend-versus-noise comparison, I would treat this as a possible small-sample fluctuation rather than evidence of an established Group C trend. However, the data cannot prove that the result is harmless noise. The three applicants still deserve a fair process, and their outcomes may reveal a problem when reviewed individually.

### The Group A–B Gap

The A–B difference is a much stronger trend. Following November, it increases from 4 pp in December and January to 13 pp in September. It remains above the approval threshold for the final three months.

The recent group sizes are also substantially larger than Group C's August sample.

| Month | Group A applicants | Group B applicants | A–B gap |
| --- | ---: | ---: | ---: |
| July | 200 | 163 | 11 pp |
| August | 207 | 170 | 12 pp |
| September | 211 | 172 | 13 pp |

Repeated deterioration across these months is more concerning than a single percentage based on three observations. It justifies investigation and corrective action, although the aggregate figures do not establish the cause.

### Which Results Breach the Criterion?

**Both do.**

| Finding | Comparison with the highest group | Literal result under the written criterion |
| --- | --- | --- |
| Group C, August | Group A is 47%; Group C is 0%. The gap is 47 pp. | Breach |
| Group B, July | Group A is 47%; Group B is 36%. The gap is 11 pp. | Breach |
| Group B, August | Group A is 47%; Group B is 35%. The gap is 12 pp. | Breach |
| Group B, September | Group A is 47%; Group B is 34%. The gap is 13 pp. | Breach |

The rule contains no minimum sample size, rolling-window requirement or statistical-significance exception. I cannot add one retrospectively to make the August result pass.

### What Should Saltbush Act On?

I would prioritise a formal investigation of the sustained A–B deterioration, including immediate safeguards for current applicants and review of potentially affected recruitment rounds.

I would also record the Group C breach and review its three August cases, any complaints and the relevant data. The small sample changes the confidence I have in a group-level conclusion and the proportionate response; it does not justify ignoring the applicants.

Saltbush should improve its monitoring design prospectively. It could retain monthly counts while using longer rolling windows for small groups, reporting uncertainty and preserving a route for individual complaints to trigger action. Any revised criterion should be justified and formally approved, with its effective date recorded. The original breaches should remain in the record.

This connects with Week 5's monitoring-trigger exercise: a useful trigger must be sensitive to persistent harm without pretending that a percentage based on three applicants is a stable estimate.

## Task 3 – Working Through ISO/IEC 42001 Clause 10.2

The main nonconformity is that the classifier no longer meets the committee's fairness condition. The monitoring process has also failed to present that deterioration accurately or connect it with other warning signals.

The following actions are my proposed response to the scenario. They are not claims that Saltbush has already investigated, retrained or corrected the system.

### a) React: Control the Problem and Address Its Consequences

This week, I would ask Kath Brennan, the classifier's system owner, to raise a formal nonconformity with Rob Ellery and Dev Raman immediately. The issue should not wait for next week's annual review.

| Immediate action | Proposed responsibility | Purpose |
| --- | --- | --- |
| Record the breaches and correct the green summary | Kath, supported by Sam Whitford and Rob | Give decision-makers an accurate record of the monthly findings, including Group C. |
| Pause reliance on classifier recommendations for shortlisting while the risk is assessed | Kath, with Anh Tran and the vendor implementing any required technical restriction | Prevent the unresolved problem from continuing to influence applicants. |
| Use the documented manual recruitment process | Sam and appropriately trained recruiters | Continue recruitment with consistent job-related criteria, sufficient review time and decisions not anchored on the classifier's ranking. |
| Preserve evidence | Sam, Anh and the vendor, coordinated by Kath | Retain relevant model/configuration versions, inputs, recommendations, recruiter actions, complaints and approval records for investigation. |
| Review potentially affected applicants | Kath and Sam, with Farah Siddiqui advising on appropriate remedies and communications | Start with breached periods and relevant complaints, then expand the review if the evidence indicates earlier or wider effects. |
| Review Group C's August cases separately | Sam, with Kath accountable | Check the three individual outcomes without assuming that either discrimination or harmless noise has been proved. |

Containment can begin before the full cause is known. A permanent technical fix should follow the investigation, because retraining the model may not address a problem caused by a changed applicant mix, poor data, configuration changes or ineffective human review.

### b) 1–2: Review the Nonconformity and Determine Its Causes

The monthly figures establish the disparity and reporting weakness. They do not establish why the selection outcomes changed.

| Possible cause or contributing factor | Why it is plausible | Evidence I would request and from whom |
| --- | --- | --- |
| A change in applicant mix or deployment context | Dublin begins contributing applicants in January and grows throughout the year. Different locations or job types may have different applicant populations. | Sam and the recruitment reporting team: selection counts and denominators by month, group, location, job type and recruitment campaign, with appropriate privacy controls. |
| Model, threshold or configuration changes | A changed scoring threshold, model version or integration could affect groups differently. | Vendor and Anh: release history, model versions, threshold settings, deployment dates, configuration logs and validation results for each change. |
| Data-quality or feature problems | Missing fields, different CV formats, language or qualification representation might affect results unequally. | Vendor, Anh and Sam: feature definitions, preprocessing rules, missing-data rates and input-quality checks by group and location. |
| Historical bias or unsuitable training data | Retraining may retain problematic labels or fail to represent the newer deployment population. | Vendor: training/validation provenance, subgroup coverage, labelling process and known limitations. Kath: evidence that acceptance testing reflected the intended use. |
| Reduced human scrutiny or automation bias | Agreement increases while overrides fall and complaints rise. | Sam: workload, review time, override reasons and reviewer guidance. Recruiters: interviews about how they actually use the recommendations. Independent reviewers: a sampled case assessment. |
| Errors or changes in the monitoring calculation | Rounded rates, changing denominators, group definitions or exclusions could distort comparisons. | Recruitment reporting team and vendor: exact shortlist counts, data dictionary, calculation logic, missing/excluded records and reconciliation to the application system. |
| Weak reporting and escalation | The summary averages away recent breaches, omits Group C and excludes complaints. HR reports complaints separately each quarter. | Kath, Rob and Dev: reporting instructions, review records, incident logs, threshold alerts and evidence of who received and acted on monthly results. |

The reported A/B percentages are rounded. I would obtain exact counts before reconstructing shortlist totals or performing formal statistical analysis. Multiplying a rounded rate by its denominator can produce an estimated count, not the actual number of applicants selected.

### What the Dublin Column Does and Does Not Show

Dublin's contribution grows from **20 of 350 applicants in January (5.7%)** to **130 of 390 in September (33.3%)**. This is a material change in the population being processed.

It gives Saltbush a reason to investigate whether the classifier performs differently across locations or whether the mix of jobs and applicants has changed. It does not prove that Dublin caused the fairness gap.

The dashboard does not provide group selection rates within each location. The aggregate difference could reflect changes within locations, changes in the mix between locations, or both. I would request those breakdowns and compare like-for-like roles before attributing a cause.

I would also distinguish the cause of the unfair outcome from the cause of late detection. Even if the vendor identifies a model fault, Saltbush still needs to explain why monthly breaches were converted into a green annual summary.

### b) 3: Could the Same Monitoring Problem Occur Elsewhere?

The transferable problem is the monitoring design: relying on averages, convenience measures or disconnected feedback can hide important risks. It is not a claim that every system has the same classifier defect.

I used the [Week 9 AI register and proposed owners](../Week%209/README.md) to identify the following checks.

| Other registered system | Proposed owner | Monitoring weakness to check | Evidence or improvement needed |
| --- | --- | --- | --- |
| ShiftSmart 3 | Mele Taufa | An overall efficiency figure could hide unfair shift allocation for particular workers, sites or people returning from leave. | Review shift outcomes, worker complaints, overrides and the basis of reliability/absence scores across appropriate groups and locations. |
| Where's My Parcel chat | Grace Mbeki | Fast responses or a high completion rate could hide incorrect tracking/refund answers or unresolved customer complaints. | Check sampled answers against the applicable records and policies; connect errors with complaint and escalation outcomes. |
| Microsoft 365 Copilot | Anh Tran | Usage and productivity measures could overlook confidentiality problems or inaccurate summaries. | Review permission/access concerns, relevant logs, reported disclosures and sampled output accuracy. Involve information owners and Farah. |
| RouteWise 5.2 | Lina Haddad | Average arrival accuracy could conceal poor performance on particular routes, sites, weather conditions or delivery periods. | Compare predictions with actual arrivals by relevant operating conditions, and review driver feedback, unsafe suggestions and overrides. |
| Free interview notetaker | Sam Whitford | Time saved could be treated as success while privacy problems and inaccurate applicant notes go unnoticed. | First confirm whether use was stopped or approved after Week 9. If an approved replacement is used, sample summaries against authorised source records and track corrections and complaints. |
| Consumer ChatGPT, hypothetical customer-email drafting | Grace Mbeki | Staff acceptance of drafted replies could be mistaken for correctness, while inappropriate information sharing remains unmeasured. | First confirm approval and permitted data. Review sampled drafts, corrections, customer feedback and inappropriate-input reports. This remains the hypothetical Week 9 extension. |
| Candidate Insights | No operational owner; prohibited proposal | A rejected feature might later be enabled through a bundle or upgrade. | Dev, Anh, Farah and Kath should verify that the prohibited use remains disabled and that procurement/change controls prevent its introduction. There is no authorised live deployment to monitor. |

These are areas to investigate. Week 10 provides monitoring results only for the shortlisting classifier, so I cannot claim that the same failures have been demonstrated in the other systems.

### c) Implement the Necessary Action

Corrective action should follow the evidence about the causes.

- If a model or configuration change caused the problem, correct or replace the affected version and test it against the approved use and representative applicant data before release.
- If input quality or deployment coverage is the cause, repair the data process and validate the system for the relevant locations and job types. Restrict use where adequate performance has not been demonstrated.
- If human oversight has weakened, change workload, training, review guidance and override procedures so recruiters can make an informed assessment.
- Correct the monitoring process in every case: retain monthly trends, include all groups and denominators, integrate feedback and assign a person to review and escalate breaches.

Each action should have an owner, an agreed deadline, evidence of implementation and an effectiveness check. The goal is to remove the cause and prevent recurrence, not simply produce a more favourable dashboard.

### d) Check Whether Corrective Action Was Effective

I would require independent review and documented evidence before the Governance Committee reapproves the classifier.

| Area | Evidence I would look for |
| --- | --- |
| Fairness | Results against the approved criterion for every relevant group, with exact counts, sample sizes and location/job breakdowns. Use an agreed evaluation period rather than declaring success after one favourable month. |
| Decision quality | A representative independent case review, including rejected applicants, using a clearly defined reference standard. Agreement with the classifier is not the test. |
| Human oversight | Reviewers have enough time and information to challenge recommendations, and their reasons and interventions are recorded. A higher override rate alone is not proof of success. |
| Feedback and remedies | Complaints and appeals are examined, affected cases receive appropriate review, and corrective actions address the issues identified. Fewer complaints alone could also reflect barriers to reporting. |
| Monitoring and escalation | A test using the historical monthly data generates the expected breach notifications, and named recipients acknowledge and act on them. This is a proposed check, not a test already performed against Saltbush's systems. |
| Continued effectiveness | Follow-up monitoring shows that the improvement persists and that it has not shifted harm to another group or location. |

Rob should check the evidence and track unresolved actions. The committee should document the basis for any restart, its conditions and when the next review is due.

### e) Change the AI Management System Where Needed

I would update Saltbush's monitoring and reporting procedures so the same governance weakness is less likely to recur.

The procedures should define the metric, denominator, group coverage, review frequency, responsible person and escalation threshold. Reports should distinguish model performance, fairness, operation and feedback, rather than allowing one reassuring measure to stand in for another.

They should also specify how small groups are reviewed, how new locations and uses trigger reassessment, and how supplier changes are recorded. Complaints, appeals and overrides should feed into the same review as the model metrics.

Finally, Dev and Rob should use the register to check whether the same reporting weakness exists in other systems. Updating only the classifier would leave the broader management-system problem unresolved.

## Task 4 – Escalating the Problem Through My Week 9 Policy

I used my proposed Week 9 structure, rather than Kath's original draft. In that structure, Kath owns the recruitment classifier, Dev owns the AI policy, Rob monitors compliance, and the Governance Committee approves elevated uses and restart after a material incident.

| Required decision | How I would apply the Week 9 policy |
| --- | --- |
| Who is first notified, and by whom? | In this scenario, Dev discovers the issue while reviewing the annual briefing, so he should notify Kath and Rob immediately and ask Sam to preserve the supporting records; under the improved routine process, Sam's recruitment team should identify the monthly breach and notify Kath and Rob, with Dev included promptly. |
| Who investigates? | Kath is accountable for the system investigation; Sam supplies recruitment and case evidence, Anh and the vendor investigate technical changes, Farah assesses relevant legal/privacy implications, and Rob tracks the nonconformity and independently challenges the evidence, supported by an independent reviewer where internal conflicts require it. |
| Who decides whether to suspend the classifier? | Kath has the owner authority to pause unsafe use, with Anh and the vendor implementing the restriction and Sam activating manual recruitment; this should not wait for the quarterly committee meeting, and the committee must approve any restart after the material incident. |
| Who reports what to the Board? | Rob supplies compliance findings, outstanding actions and any independent challenge; Dev should consolidate the AI risk and response report through Helen to the Board, with Rob retaining the direct escalation route provided in Week 9. |

### What the Board Needs to Know

The report should explain the three consecutive A–B breaches, the separate small-sample Group C finding, the rising complaints and the limitations of recruiter agreement as a performance measure.

It should also identify the affected periods and populations, containment measures, investigation owner, current uncertainty, corrective actions and conditions for restart. The Board should receive any material resource decision or unresolved risk that requires its attention.

A technical explanation alone would be insufficient. The report also needs to explain why the earlier summary presented the system as green and whether the same reporting weakness could affect other registered systems.

### Gaps I Would Clarify in My Week 9 Policy

My Week 9 section provided suspension authority, a reporting route, quarterly board reporting and urgent escalation for serious concerns. It did not explicitly name the person responsible for assembling and presenting the board report, or set a precise notification deadline for a fairness-condition breach.

I would clarify that **Dev owns the consolidated board report**, supported by Rob's compliance findings and presented through Helen, with Rob able to escalate directly where needed.

I would also propose that a confirmed breach of an approval condition is reported to the owner, Rob and Dev **on the working day it is identified**, with immediate containment where continued use creates unacceptable risk. The committee should approve and document this response rule. These are refinements to my policy, not claims that the original wording already specified them.

## Task 5 – Fixing the Monitoring

### Clause 9.1: Four Questions

| Question | Revised monitoring requirement |
| --- | --- |
| What needs to be monitored and measured? | Measure independently reviewed decision quality, selection rates and counts for every relevant group and location, system availability and response time, and complaints, appeals, overrides and their reasons. |
| By what method, so results are valid? | Use reconciled exact counts, stable definitions, a blinded representative case review and the approved fairness criterion, report small-sample uncertainty and relevant job/location breakdowns, and assess feedback alongside the quantitative results rather than treating unchanged recommendations as ground truth. |
| When is it measured? | Record decisions, operational events and feedback as they occur, produce group metrics monthly and weekly during high-volume campaigns, and repeat validation before significant model, configuration or deployment changes. |
| When are results analysed and evaluated, and by whom? | Sam reviews each reporting period promptly, Kath and Rob evaluate breaches on the working day identified and escalate them to Dev and the Governance Committee, and Dev provides the agreed board reports without delaying urgent issues for a scheduled meeting. |

These four sentences are my proposed replacement monitoring design. More frequent campaign checks supplement the monthly approval review; any change to the formal evaluation window or small-sample rule requires a documented decision rather than an informal change to the pass/fail calculation.

Results, methods, model versions, review decisions, alerts and actions should be retained as documented evidence.

### A Bias Source the Monitoring Still Cannot Establish

The remaining limitation I would choose is **bias in the definition of a suitable applicant and the reference decisions used to evaluate the classifier**.

Suppose recruiters and the model both apply an unjustified assumption about what makes somebody suitable for a job. They could agree on every case while reproducing that assumption. Even an independent reviewer can share the same flawed selection criteria if the review starts from the same definition of suitability.

The rewritten monitoring could expose unequal outcomes or disagreements. It cannot, from those measurements alone, establish that the underlying job criteria and reference labels are justified. High agreement, or even equal selection rates across the measured groups, would not settle that question.

The additional control is an independent review of the recruitment criteria and label provenance, involving job-analysis expertise, HR, relevant legal advice and affected stakeholders. That review should examine whether each criterion is relevant to the work, how historical decisions were produced and whether important harms fall outside the groups currently measured.

Blinding reviewers to the model's recommendation reduces anchoring, but it does not replace this broader review of the assumptions built into the task.

This is consistent with NIST's distinction between computational, human and systemic sources of bias: examining the model's measured outputs alone does not cover the whole problem. [NIST SP 1270](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.1270.pdf).

## Week 10 Reflection

This week showed me how a monitoring report can be numerically correct and still give decision-makers the wrong impression.

Saltbush's 7.0 percentage-point annual average can be reproduced from the monthly figures. The problem is what that average conceals. The classifier had exceeded its fairness condition for three consecutive months, yet the summary still described it as green and recommended no action.

I found the agreement measure particularly useful to examine. An unchanged recommendation may reflect a good decision, but it can also reflect limited scrutiny. Because agreement and overrides are complements here, presenting higher agreement as stronger performance leaves the quality of both the model and human review unresolved.

The Group C result also reinforced the importance of separating the written requirement from the strength of the evidence. Zero shortlisted applicants out of three is unstable as a group-level estimate, but it still breaches the criterion Saltbush actually adopted. The appropriate response is to record and examine it proportionately, then improve the monitoring design through a documented process.

Clause 10.2 helped connect detection to action. Saltbush needs immediate containment, an investigation into causes, suitable corrective action and evidence that the action worked. It also needs to ask whether the same monitoring weakness exists elsewhere.

This brings the earlier topics together. Risk classification helps determine the level of oversight. Human factors affect how people interpret and challenge AI. Fairness analysis provides evidence about outcomes. Governance assigns authority to act, and assurance checks whether the whole arrangement continues to work.

The main lesson for me is that monitoring becomes useful when its findings reach the right people and change what the organisation does. A dashboard that collects data but hides deterioration is not providing that assurance.

## References

- Federation University Australia. (2026). [Learning activity – Topic 10](https://moodle.federation.edu.au/mod/lesson/view.php?id=9128317). ITECH2119 Moodle. Source of the Saltbush scenario, October–September monitoring figures, task instructions and the Clause 9.1/10.2 extracts used in this entry; university login required.
- International Organization for Standardization. (2023). [ISO/IEC 42001:2023 – Artificial intelligence management systems](https://www.iso.org/standard/42001). Standard overview; the detailed clause extracts used here were supplied in the Moodle activity.
- Schwartz, R., Vassilev, A., Greene, K., Perine, L., Burt, A., & Hall, P. (2022). [Towards a standard for identifying and managing bias in artificial intelligence](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.1270.pdf) (NIST Special Publication 1270). National Institute of Standards and Technology.
- [Week 9 – Organisational Governance of AI](../Week%209/README.md). Previous portfolio entry used for the system owners, AI register and Governance and compliance section.
