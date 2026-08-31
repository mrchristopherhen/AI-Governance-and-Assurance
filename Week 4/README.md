# ⚖️ Week 4 – Probing AI Bias and Fairness

## 📘 Overview

This week focused on bias and fairness in AI systems and how an AI system can appear accurate overall while still producing different outcomes for different groups.

The activity involved a simulated AI hiring classifier used to decide which applicants were shortlisted for an interview. Management believed the system was accurate overall, but employees were concerned that some groups were being selected less often than others.

I used a sample of 20 applicants across **Group A** and **Group B** to calculate selection rates, interpret the results using Fairlearn, investigate possible failure modes, design additional tests and recommend how the organisation should respond.

---

# 🔮 Task 1 – Prediction Before Calculating

Before calculating the selection rates, I suspected that the classifier might not be applying the same standard to both groups.

Looking at one successful applicant is not enough to determine whether the overall system is fair. For example, the fact that B01 scored 83 and was shortlisted shows that someone from Group B can be selected, but it does not tell us whether Group B applicants are being selected at the same rate as Group A.

The same problem applies when looking only at whether higher scores generally lead to selection. The important question is whether applicants from both groups are being treated consistently.

I therefore expected the group-level results to provide a clearer picture than individual examples.

---

# 📊 Task 2 – Selection Rate Worksheet

| Group | Selected | Total | Selection rate |
|---|---:|---:|---:|
| **Group A** | 6 | 10 | **60%** |
| **Group B** | 3 | 10 | **30%** |

The difference between the two groups is **30 percentage points**.

Group A applicants were shortlisted at a rate of 60%, compared with 30% for Group B. This means Group A was shortlisted at twice the rate of Group B within this sample.

It is important to describe this as a **30 percentage-point difference**, rather than saying the classifier was "30% less accurate." Selection rate and accuracy measure different things.

Another important pattern in the supplied data is that the two groups appear to have different qualification-score cut-offs. Based on the values recorded in the activity, Group A applicants were shortlisted from a score of **66**, while Group B applicants needed a score of **75** or higher. A Group B applicant with a score of 72 was rejected while a Group A applicant with a lower score of 66 was shortlisted.

This does not prove why the difference occurred, but it gives me another reason to investigate whether the classifier is treating the two groups consistently.

---

# 💻 Part B – Fairlearn Output

I worked through the Fairlearn activity and compared its results with my manual calculation.

```text
Selection rate by group:
group
Group A    0.6
Group B    0.3
Name: selected, dtype: float64

Difference between groups (max - min): 0.3
```

The Fairlearn result matches the manual calculation:

- **Group A:** 60%
- **Group B:** 30%
- **Difference:** 30 percentage points

Fairlearn therefore identifies a measurable difference between the outcomes for the two groups.

However, this result does not prove that discrimination occurred. It identifies a **disparity that should be investigated further**. More information is needed before determining what caused the difference or whether it represents unfair treatment.

---

# 🔎 Task 3 – Interpreting the Fairlearn Result

## Which group had the higher selection rate?

**Group A** had the higher selection rate at 60%, compared with 30% for Group B.

## How large was the difference?

The difference was **30 percentage points**. Group A applicants were shortlisted at twice the rate of Group B applicants within this sample.

## Does this suggest the classifier should be investigated for possible bias?

Yes.

A 30 percentage-point difference is large enough to justify further investigation. The supplied data also suggests that Group B applicants may require a higher qualification score before being shortlisted.

This does not tell us why the difference exists, but it provides enough evidence to question whether the classifier is applying a consistent standard across both groups.

## Does the selection-rate difference prove discrimination occurred?

No.

A difference in selection rates shows that the groups received different outcomes, but it does not explain the cause.

The difference could potentially come from the training data, the way qualification scores were calculated, other features used by the model, differences within the applicant sample, or another part of the hiring process.

The result should therefore be treated as evidence for further investigation rather than proof of discrimination.

## What other information would I want before making a final judgement?

Before deciding whether the system is fair, I would want to know:

- What **Group A** and **Group B** actually represent.
- How the **qualification score** is calculated and whether the same process is used for everyone.
- What other information the classifier uses when making its decision.
- What historical hiring data was used to train the model.
- Whether the 20 applicants are representative of the organisation's normal applicant pool.
- Whether similar differences appear across larger samples and multiple recruitment rounds.
- Whether there is reliable ground truth showing which applicants should have been shortlisted.

This additional information would help determine whether the difference is caused by bias in the system or another factor.

---

# 🧩 Task 4 – Finding the Failure Mode

| Possible failure mode | Evidence to look for | How I would test it | Possible mitigation |
|---|---|---|---|
| **Historical bias** | Previous hiring data may show that Group A applicants were selected more often than similarly qualified Group B applicants. | Compare historical shortlisting decisions between applicants from both groups with similar qualification scores. If the same pattern appears in the historical data, this would provide evidence that the model may have learned an existing disparity. | Review and clean the training data before retraining the model. Historical decisions that reflect unfair patterns should not simply be treated as correct examples for the model to learn from. |
| **Proxy variables** | The model may be using information that is strongly connected to group membership, even if the group itself is not directly used. Examples could include postcode, name or referring institution. | Review the features used by the model and test whether changing a suspected proxy while keeping the rest of an applicant's information the same changes the decision. | Remove inappropriate features where possible and test the model again. Feature removal alone may not solve the problem, so fairness testing should continue after retraining. |
| **Weak fairness monitoring** | Management focused on overall accuracy while the difference between groups was only identified after employees raised concerns. | Review the organisation's testing and deployment process to determine whether group-level fairness metrics were checked before and after deployment. | Make fairness testing part of the approval process for new models and continue monitoring group-level outcomes after deployment. |

### 💭 My Assessment

I think all three failure modes are possible based on the scenario, but the current evidence does not tell us which one caused the difference.

The important next step would be to test each explanation rather than assuming that the selection-rate difference automatically identifies the cause.

---

# 🔴 Task 5 – Red-Team the Hiring System

I would perform three additional tests before allowing the organisation to rely on the classifier.

| Test | What would I compare? | What result would concern me? |
|---|---|---|
| **Similarly qualified applicant test** | Compare the decisions for Group A and Group B applicants within similar qualification-score ranges. | I would be concerned if Group B applicants were rejected more often than Group A applicants despite having similar qualification scores. |
| **Additional demographic testing** | Compare outcomes across other relevant demographic groups and, where appropriate, combinations of characteristics. | I would be concerned if another group experienced a much lower selection rate that was hidden by only comparing Group A and Group B overall. |
| **Testing over time** | Compare selection rates across multiple recruitment rounds rather than relying on one sample of 20 applicants. | I would be concerned if the difference remained consistent or became larger over time. This could indicate that the problem is systematic rather than a one-off result from a small sample. |

These tests would provide a broader picture of the classifier's behaviour.

If reliable ground-truth labels were available showing which applicants genuinely met the shortlisting criteria, I would also compare error rates such as **false negatives between groups**. Without ground truth, however, I would not describe rejected applicants as false negatives simply because they had a particular qualification score.

---

# 🛡️ Task 6 – Mitigation and Governance

Before the organisation continues using the classifier, I would recommend actions across four areas.

## 📂 Data

The data or machine learning team should review the historical training data to determine whether both groups are properly represented and whether previous shortlisting decisions contain patterns that could introduce bias.

If historically unfair decisions are being used as training labels, retraining the model on the same data could reproduce the same problem.

## 🧪 Testing

Fairness testing should become a required part of model testing before deployment and after retraining.

This should include selection rates across relevant groups and, where reliable ground truth exists, error-rate measures such as false negatives.

The organisation should define and document what level of disparity requires investigation or prevents deployment rather than choosing an arbitrary threshold after seeing the results.

## 👥 Human Oversight

The classifier should support hiring decisions rather than operate as the final decision-maker.

Human recruiters should be able to review automated decisions, particularly when monitoring identifies a possible disparity. Applicants should also have a clear way to request human review or challenge an automated shortlisting decision.

## 📈 Monitoring and Governance

Fairness should continue to be monitored after deployment rather than being treated as a one-time test.

The organisation should assign responsibility for monitoring the system, regularly review group-level outcomes and establish a clear process for escalating concerns. If a significant unexplained disparity appears, the organisation should be prepared to pause the system while the cause is investigated.

---

# 🧠 Week 4 Reflection

This week showed me why overall accuracy is not enough when evaluating an AI system. A model can appear to perform well when looking at one overall number while still producing very different outcomes for different groups.

The hiring example made this particularly clear. Group A had a 60% selection rate while Group B had a 30% selection rate. That difference does not automatically prove discrimination, but it is a strong enough signal that the system should be investigated further.

I also found the failure-mode activity useful because it moved the analysis beyond simply identifying a disparity. Historical data, model features, proxy variables, testing practices and weak governance could all contribute to unfair outcomes. This means fairness needs to be considered throughout the AI lifecycle rather than checked once after deployment.

From a governance perspective, the biggest lesson for me was that **fairness metrics should be treated as evidence for investigation rather than automatic proof of why a disparity occurred**. Human oversight, ongoing monitoring and clear accountability are still needed before an organisation can make responsible decisions about whether an AI system should continue to be used.

---

