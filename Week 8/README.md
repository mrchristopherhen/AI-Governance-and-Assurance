# Week 8 – Bias, Fairness, Transparency and Explainability

## Overview

This week focused on four related but different ideas in AI governance: bias, fairness, transparency and explainability.

I examined these ideas through four case studies in the Week 8 Moodle Book: COMPAS criminal-risk scoring, the Dutch childcare-benefits scandal, SafeRent tenant screening and Google's Gemini image-generation incident. I then audited the supplied COMPAS spreadsheet by examining representation, documenting cleaning decisions, constructing confusion matrices, changing the prediction threshold and comparing COMPAS with a simple logistic-regression model.

The activities required me to:

- distinguish bias from fairness, transparency and explainability;
- identify proxy discrimination, feedback loops and fairness-metric conflicts;
- explain why standard classification metrics do not transfer cleanly to generative AI;
- separate substantive harm from procedural harm;
- trace how an apparently neutral variable can reproduce structural inequality;
- calculate and interpret accuracy, false-positive rate, false-negative rate, precision and recall; and
- connect technical findings to the Australian AI Ethics Principles of fairness, transparency and explainability, contestability and accountability.

## Key Concepts

| Concept | My working definition | Governance question |
|---|---|---|
| Bias | A systematic tendency in data, design, deployment or outcomes that favours some patterns or groups over others. | Where did the pattern enter, and how is it amplified? |
| Fairness | A normative judgement about whether benefits, burdens and errors are distributed acceptably. | Which definition of fairness is appropriate for this use and affected population? |
| Transparency | Disclosure about the system's purpose, data, operation, limitations and governance. | Can affected people and reviewers understand what system is being used and on what basis? |
| Explainability | Information that helps a person understand why a particular output occurred. | Can a decision-maker or affected person make sense of and challenge the result? |

These concepts overlap, but they are not interchangeable. A transparent system can disclose that it has unequal error rates and still be unfair. A statistically accurate system can still be procedurally harmful if a person receives no reason, review or meaningful way to challenge a decision.

## Task 1 – Exploring and Cleaning the COMPAS Data

### 1A – Who Is Represented?

The supplied workbook contained 7,214 defendant records.

| Racial group | Count (n) | Share of total |
|---|---:|---:|
| African-American | 3,696 | 51.23% |
| Caucasian | 2,454 | 34.02% |
| Hispanic | 637 | 8.83% |
| Other | 377 | 5.23% |
| Asian | 32 | 0.44% |
| Native American | 18 | 0.25% |
| **Total** | **7,214** | **100.00%** |

### Q1 – Which Groups Support Reliable Conclusions?

African-American and Caucasian defendants have enough records for stable descriptive comparisons in this dataset. Hispanic defendants have a moderate sample, while the Other category should be interpreted cautiously because it combines people who may not form a meaningful or homogeneous group.

My rough screening rule would be at least 100 observations and, more importantly, enough positive and negative outcomes to avoid very small confusion-matrix cells. Several hundred cases are preferable when comparing error rates. This is not a universal statistical threshold. Reliability depends on the event rate, the size of the effect being estimated and the uncertainty that is acceptable for the decision.

The Asian and Native American groups are too small for dependable subgroup conclusions here. A percentage based on 18 people can change sharply when only one or two records change.

### Q2 – What Does Inadequate Validation Mean for a Person?

For an Asian or Native American defendant, inadequate validation means the available evidence does not establish how well the model performs for people from that group. The score may still be correct in an individual case, but the organisation cannot responsibly claim that its error rates, calibration or limitations are known for that population.

This creates both substantive and procedural risks. The person may receive a poor prediction, and they may also be unable to discover or challenge a group-specific failure because the validation evidence is too weak. Lack of evidence is not proof that the model is biased, but it is a serious limit on claims that the model is fair or safe.

### 1B – Cleaning Decisions

The workbook was already clean for most of the tutorial's checks. Only the screening-window rule removed records.

| Rows considered | Decision | Rows affected | Justification |
|---|---|---:|---|
| `days_b_screening_arrest` outside −30 to +30 days | Exclude | 735 | Keep the screening event reasonably close to the arrest being analysed and make the cohort comparable with the tutorial's stated method. |
| `two_year_recid = -1` | Exclude if present | 0 | An unknown or incomplete outcome cannot be treated as either reoffending or not reoffending. |
| `c_charge_degree = O` | Exclude if present | 0 | The category is outside the standard felony/misdemeanour comparison and may not represent the same decision context. |
| Blank `score_text` | Exclude if present | 0 | A record without a COMPAS category cannot be evaluated as a model prediction. |
| Duplicate IDs | Retain one defensible record if present | 0 | I would retain the record closest to the relevant arrest after checking whether repeated rows represent duplicates or distinct events. |

The cleaned dataset contained 6,479 records.

### Q4 – Whose Cleaned Dataset Is Correct?

I did not have a classmate's completed workbook to compare, so I cannot claim that a particular classmate made a different choice. However, the tutorial makes clear that two analysts can produce different defensible datasets because cleaning depends on the question being answered.

A dataset is not "correct" simply because it has more or fewer rows. The analyst should define the target population and outcome first, apply consistent rules, test how sensitive the results are to those rules and document every exclusion. A different decision becomes a governance problem when it is hidden, inconsistently applied or chosen after seeing which result it produces.

### Q5 – Who Might the Screening-Window Rule Exclude?

The ±30-day rule may exclude people whose screening occurred substantially before or after the recorded arrest, including people who were not in custody at screening, people whose cases moved slowly, and records affected by administrative delay.

Those circumstances may be associated with bail access, legal support, court workload, geography or socioeconomic resources. I cannot determine the direction of that bias from the rule alone. Excluding the records could remove people with greater access to release, or it could remove people experiencing longer and more complex processing. The appropriate response is to compare included and excluded groups rather than assume the exclusion is neutral.

### Q6 – Representation After Cleaning

| Racial group | Cleaned count | Rows lost | Proportion lost |
|---|---:|---:|---:|
| African-American | 3,334 | 362 | 9.8% |
| Caucasian | 2,179 | 275 | 11.2% |
| Hispanic | 562 | 75 | 11.8% |
| Other | 360 | 17 | 4.5% |
| Asian | 31 | 1 | 3.1% |
| Native American | 13 | 5 | 27.8% |
| **Total** | **6,479** | **735** | **10.2%** |

Native American defendants lost the largest proportion of records, but the group began with only 18 cases. Five exclusions therefore produce a large percentage change. Hispanic and Caucasian defendants had the next highest proportional losses among the larger groups.

Cleaning did not solve the representation problem. It reduced the already very small Native American group to 13 records, which further lowers my confidence in any group-specific rate. This is why proportional change, absolute count and statistical uncertainty should be considered together.

## Task 2 – Confusion Matrix and Error Rates

I used the tutorial's stated threshold: **High** was treated as a positive prediction, while Low and Medium were treated as negative predictions. The results below use the 6,479 cleaned records.

| Actual outcome | Predicted High | Predicted Low/Medium | Row total |
|---|---:|---:|---:|
| Reoffended | TP = 861 | FN = 2,003 | 2,864 |
| Did not reoffend | FP = 349 | TN = 3,266 | 3,615 |
| **Column total** | **1,210** | **5,269** | **6,479** |

| Metric | Result | Interpretation |
|---|---:|---|
| Accuracy | 63.7% | The share of all predictions that matched the recorded two-year outcome. |
| False-positive rate | 9.7% | The share of non-reoffenders who were incorrectly classified as High risk. |
| False-negative rate | 69.9% | The share of reoffenders who were classified as Low or Medium risk. |
| Precision | 71.2% | The share of people classified as High risk who reoffended. |
| Recall | 30.1% | The share of reoffenders captured by the High-risk threshold. |

### Q7 – Which Error Is More Common, and What Does It Cost?

False negatives were much more common than false positives: 2,003 compared with 349.

A false positive can affect a person's liberty and opportunities if a risk score influences bail, sentencing, parole or supervision. It can impose a burden even though the person did not reoffend during the recorded period. A false negative may leave a genuine risk unmanaged and can create costs for victims, the community and later justice-system intervention.

The two errors are therefore not interchangeable. Their consequences fall on different people, and the ethical significance depends on how the score is used rather than on the count alone.

### Q8 – What Happens When the Threshold Changes?

I recalculated the results by treating both Medium and High as positive predictions.

| Threshold | Accuracy | FPR | FNR | Precision | Recall |
|---|---:|---:|---:|---:|---:|
| High only | 63.7% | 9.7% | 69.9% | 71.2% | 30.1% |
| Medium or High | 65.4% | 31.4% | 38.6% | 60.7% | 61.4% |

Lowering the threshold caught many more people who reoffended: recall increased from 30.1% to 61.4%, and the false-negative rate fell from 69.9% to 38.6%. The cost was a much higher false-positive rate, which rose from 9.7% to 31.4%, and lower precision.

A lower threshold may benefit public-safety objectives by detecting more recorded reoffending, but it harms more people who would not reoffend by placing them in the positive-risk category. A higher threshold reduces over-flagging but misses more people who later reoffend. Threshold choice is therefore a policy decision with distributive consequences, not just a technical tuning step.

### Q9 – Should Both Errors Count Equally?

Overall accuracy silently gives every correct result the same value and every error the same cost. That assumption is difficult to defend in criminal justice because a false positive may contribute to a loss of liberty, while a false negative may expose other people to preventable harm.

The weighting should not be chosen by the software vendor or data scientist alone. It should be set through a transparent and legally accountable process involving courts, policymakers, domain experts and communities affected by the decisions. The process should consider rights, empirical evidence about consequences, the presumption of innocence, proportionality and the purpose for which the score is being used.

### Q10 – What Does Historical Arrest Data Measure?

Arrests and charges are produced by both behaviour and institutional practices. If some communities have experienced more intensive policing, surveillance or enforcement, they will have more opportunities to be observed and recorded even when underlying conduct is similar.

A model trained on those records can learn the likelihood of future contact with police and courts as well as the likelihood of future offending. It may therefore reproduce enforcement patterns through variables such as prior charges, neighbourhood or criminal-history counts. Calling the output a neutral measure of individual risk would conceal that measurement problem.

### Subgroup Error Rates

The two largest groups illustrate the fairness conflict discussed in the Moodle COMPAS case study.

| Group | n | Recorded reoffending rate | FPR | FNR | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| African-American | 3,334 | 50.8% | 15.2% | 61.8% | 72.2% | 38.2% |
| Caucasian | 2,179 | 38.1% | 5.0% | 80.5% | 70.7% | 19.5% |

Precision was similar for the two groups, but the error distribution was not. African-American non-reoffenders were falsely classified High at about three times the Caucasian rate, while Caucasian reoffenders were more often missed.

This does not reduce fairness to a single winning metric. When groups have different recorded base rates, calibration or similar precision can coexist with unequal false-positive and false-negative rates. The governance task is to identify which properties matter for the decision, make the trade-off visible and determine whether the remaining burden is legally and ethically acceptable.

I did not interpret the Asian and Native American rates because their cleaned samples were only 31 and 13. Calculating a percentage is possible, but presenting it as a stable fairness finding would be misleading.

## Optional Task 3 – A Simple Logistic-Regression Model

I completed the optional modelling task using an L2-regularised logistic regression mathematically equivalent to the tutorial's model specification. It used all 7,214 complete rows, a 0.5 decision threshold and the five listed features. Because this comparison follows the optional tutorial code, the COMPAS column below uses the raw workbook rather than the Task 1 filtered cohort.

### Coefficients

| Variable | Coefficient | Direction | Interpretation |
|---|---:|---|---|
| Intercept | +0.8075 | Positive | Baseline log-odds when all listed features are zero; it is a mathematical reference point rather than a realistic person. |
| Age | −0.0454 | Negative | Each additional year lowers predicted log-odds when the other features are held constant. |
| Prior adult charges | +0.1543 | Positive | More prior charges increase predicted risk. |
| Juvenile felony charges | +0.1844 | Positive | More juvenile felony charges increase predicted risk. |
| Juvenile misdemeanour charges | +0.0199 | Positive | The estimated per-charge contribution is small relative to the other history variables. |
| Other juvenile charges | +0.2000 | Positive | This is the largest coefficient per unit, although practical influence also depends on how widely a feature varies. |

### Model Comparison

| Model | Accuracy | FPR | FNR | Precision | Recall |
|---|---:|---:|---:|---:|---:|
| COMPAS, High-only threshold | 63.2% | 10.1% | 69.2% | 71.3% | 30.8% |
| Simple logistic regression | 68.0% | 18.7% | 48.2% | 69.4% | 51.8% |

The simple model had higher accuracy than the High-only COMPAS classification and substantially higher recall. It reduced the false-negative rate from 69.2% to 48.2%, but its false-positive rate increased from 10.1% to 18.7%. The largest coefficient per unit was `juv_other_count`, while `priors_count` may still have greater practical influence because adult prior counts can span a wider range. These results show that a small, inspectable model can be competitive on aggregate metrics. They do not prove that the model is fair, causal or suitable for court use, and they do not show that COMPAS's proprietary complexity adds no value under every threshold or use case.

## Case Studies from the Moodle Book

### Comparative Analysis

| Case study | Main failure mode | Substantive harm | Procedural harm | Governance lesson |
|---|---|---|---|---|
| COMPAS | Proxy variables, conflicting fairness metrics and a proprietary model | Unequal distribution of false positives and false negatives in a high-impact justice setting | An affected person may not be able to inspect, understand or effectively challenge the basis of the score | Validate subgroup outcomes, state which fairness definition is being used, disclose limitations and preserve judicial responsibility and review |
| Dutch childcare benefits | Nationality-related proxies combined with a self-reinforcing investigation loop | Families were wrongly required to repay large sums, experienced severe hardship and, in some cases, family disruption | A flag led to scrutiny that generated further evidence of suspicion, while meaningful explanation and appeal were weak | Test proxy chains, separate suspicion from proof, prevent feedback loops and provide accessible independent review |
| SafeRent | Credit-related variables, including medical debt, operated as proxies for structural inequality | Applicants could lose access to housing despite the variable having a weak relationship to tenancy behaviour | Applicants had limited visibility into the score and little practical ability to correct or contest it | Require relevance testing, adverse-impact analysis, case-level reasons and a human reconsideration process |
| Gemini image generation | Diversity prompting overcorrected without enough historical and contextual evaluation | Historically implausible and offensive representations reduced accuracy and trust | Users became de facto testers after release and could not see how the intervention changed the result | Test representational quality across contexts before release and monitor scenarios that cannot be reduced to a confusion matrix |

### Tracing a Proxy Chain

The SafeRent case demonstrates how discrimination can occur without using race as an explicit input:

1. Unequal access to healthcare and financial security contributes to medical debt being concentrated in some communities.
2. Medical debt enters a credit file or tenant-screening input.
3. The screening model treats the debt as evidence of rental risk.
4. The score influences a landlord's acceptance threshold.
5. Applicants from already disadvantaged racial and income groups are more likely to be rejected.

Removing the race field does not break this chain. Governance must test whether a variable is relevant to the decision, whether it acts as a proxy and whether it creates a disproportionate burden.

### Why Classification Metrics Do Not Transfer Cleanly to Generative AI

The COMPAS audit has a defined binary outcome: the person was or was not recorded as reoffending within two years. That allows a confusion matrix to be constructed, even though the outcome itself has limitations.

The Gemini case is different. A generated historical image does not usually have one binary ground-truth label. Quality depends on the prompt, context, factual period, representational choices and the kind of harm being evaluated. Demographic parity, equalised odds and calibration cannot by themselves determine whether an image is historically accurate or culturally appropriate.

Generative AI therefore needs scenario-based evaluation. This should include historically specific prompts, open-ended prompts, diverse human review, adversarial testing, documentation of interventions and monitoring after deployment. A correction intended to improve representation can introduce a different bias if it is applied without enough context.

## Governance Response

The four case studies point to a lifecycle rather than a one-time fairness check.

### Before Deployment

- Define the intended use, affected population and decisions the system must not make.
- Conduct an impact assessment covering rights, groups, foreseeable misuse and severity of harm.
- Document the origin and limitations of training, validation and operational data.
- Test representation, proxy variables, subgroup performance and alternative thresholds.
- Explain why each input is relevant to the stated purpose.
- Set minimum evidence requirements for small or underrepresented groups.
- Require independent approval before a high-impact system is used.

### At the Point of Decision

- Tell the person when AI has materially influenced a decision.
- Provide a useful reason based on the main factors rather than only a general system description.
- Keep a responsible human decision-maker with enough time, competence and authority to disagree.
- Offer an accessible process to correct data, challenge the outcome and obtain reconsideration.
- Record overrides, disagreements and reasons so that oversight can detect recurring patterns.

### After Deployment

- Monitor error rates and outcomes by relevant group, not just overall accuracy.
- Test for changes in data, population, policy and system behaviour.
- Treat complaints and appeals as evidence for model review.
- Investigate feedback loops between predictions, interventions and future training data.
- Publish material limitations and corrective action.
- Suspend the system when the evidence no longer supports continued use.

These controls connect directly to Australia's AI Ethics Principles. Transparency and explainability require responsible disclosure and reasonable information about outcomes. Contestability requires a timely way to challenge a significant AI-assisted decision. Fairness, accountability and human oversight make those protections operational rather than symbolic.

## Week 8 Reflection

This week changed how I think about the phrase "remove the bias."

Bias is not a single error that can always be deleted from a dataset. It can enter through historical labels, unequal representation, proxy variables, threshold choices, institutional practice and the way a prediction changes future behaviour. The Dutch case showed this most clearly because a suspicion triggered investigation, the investigation produced more adverse records, and those records appeared to confirm the original suspicion.

The COMPAS exercise also showed why an accuracy figure is not enough.

With a High-only threshold, the model achieved 63.7% accuracy on the cleaned cohort, but it missed almost 70% of recorded reoffenders. Lowering the threshold increased recall and reduced false negatives, but it more than tripled the false-positive rate. The technical result does not tell society which burden is acceptable. It makes the trade-off visible so that an accountable decision can be made.

The subgroup comparison was equally important. Similar precision did not mean similar treatment because the African-American and Caucasian groups experienced very different false-positive and false-negative rates. Fairness therefore depends on the decision context, the selected metric and the people who carry each type of error.

My main takeaway is that transparency and contestability are part of fairness, not optional additions after a model is built.

A person affected by a criminal-risk score, fraud flag or tenant-screening result needs more than an assurance that the model is accurate on average. They need to know that AI influenced the decision, understand the main reasons, correct inaccurate information, obtain meaningful human review and access a remedy when the system causes harm.

The Gemini case added another lesson. Governance methods must match the type of system. Classification audits are valuable when predictions and outcomes can be clearly defined. Generative systems require broader contextual and representational evaluation because there is no single confusion matrix capable of measuring historical accuracy, cultural harm and usefulness at the same time.

## Evidence

- The workbook preserves the original `RAW DATA` and `Column Guide` sheets and adds formula-driven `Task 1`, `Task 2` and `Optional Model` sheets.
- The four case-study analyses are based on the videos in the Week 8 Moodle Book. The Moodle link may require Federation University authentication.

## References

Australian Government, Department of Industry, Science and Resources. (2026). *Australia's AI Ethics Principles*. https://www.industry.gov.au/publications/australias-ai-ethics-principles

Chouldechova, A. (2017). Fair prediction with disparate impact: A study of bias in recidivism prediction instruments. *Big Data, 5*(2), 153–163. https://doi.org/10.1089/big.2016.0047

Dressel, J., & Farid, H. (2018). The accuracy, fairness, and limits of predicting recidivism. *Science Advances, 4*(1), eaao5580. https://doi.org/10.1126/sciadv.aao5580

Federation University Australia. (2026). *ITECH2119 Week 8: Bias, fairness, transparency and explainability* [Moodle Book and case-study videos]. https://moodle.federation.edu.au/mod/book/view.php?id=8980859

Google. (2024, February 23). *What happened with Gemini image generation*. https://blog.google/products-and-platforms/products/gemini/gemini-image-generation-issue/

Louis v. SafeRent Solutions, LLC. (2024). *Class action settlement agreement and release*. https://www.matenantscreeningsettlement.com/Content/Documents/Settlement%20Agreement.pdf

ProPublica. (2016). *COMPAS analysis*. GitHub. https://github.com/propublica/compas-analysis
