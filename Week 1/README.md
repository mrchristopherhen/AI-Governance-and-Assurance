# Week 1 – Introduction to AI Governance and Assurance

## Overview

This week’s activities introduced the foundations of AI governance and assurance by examining real-world AI incidents, exploring established AI risk frameworks, and identifying AI systems used in everyday life. The exercises highlighted that AI governance extends beyond technical implementation and requires consideration of ethics, accountability, transparency, and the impacts that AI systems can have on individuals and society.

---

# Task 1 – AI Incident Database

## Overview

The [AI Incident Database (AIID)](https://incidentdatabase.ai/) is a publicly accessible record of real-world incidents involving artificial intelligence and automated systems. It is maintained by the Responsible AI Collaborative and used by researchers, policymakers, and governance practitioners. For this task, I examined two incidents discussed in the Week 1 lectures, identified the type of AI involved, who was harmed, and how the AIID uses evidence to document incidents.

---

## Incident 1 – Miami Police Facial Recognition

| Item | Details |
|---|---|
| **Incident ID** | [557](https://incidentdatabase.ai/cite/557/) |
| **Title** | Miami Police Deployed Facial Recognition to Arrest George Floyd Protestor Allegedly without Cause |
| **AI Type from the lecture** | Computer Vision (Facial Recognition / Biometrics) |
| **Really AI?** | Yes. Facial recognition uses machine learning to compare facial features against images stored in a database. The result is only a possible match and should always be verified by a human before action is taken. |
| **Who was harmed?** | Oriana Albornoz, who was identified and arrested, along with protesters whose privacy and freedom of expression may have been affected by the use of facial recognition technology. |
| **Approximate number affected** | One person was directly identified and arrested. The total number of protesters whose images were analysed is not stated. |
| **Summary** | Miami Police used Clearview AI facial recognition software to identify Oriana Albornoz from footage of a George Floyd protest before arresting her. The arrest report did not disclose that facial recognition had been used, and her lawyer questioned both the source of the images and whether there was sufficient independent evidence to support the arrest. |

---

## Incident 2 – Robodebt

| Item | Details |
|---|---|
| **Incident ID** | [57](https://incidentdatabase.ai/cite/57/) |
| **Title** | Australian Automated Debt Assessment System Issued False Notices to Thousands |
| **AI Type from the lecture** | Automated Decision-Making |
| **Really AI?** | I agree with the lecture that Robodebt is better described as an automated decision-making system than artificial intelligence. It relied on rules and income averaging rather than learning from data or adapting its behaviour. AIID's CSET classification also notes that the system likely does not meet its definition of AI. |
| **Who was harmed?** | Australian welfare recipients who received incorrect debt notices. |
| **Approximate number affected** | Approximately 443,000 people were affected, with around 470,000 debts raised. |
| **Summary** | The Robodebt scheme compared Australian Taxation Office income data with Centrelink records using income averaging to identify alleged welfare debts. The flawed process generated hundreds of thousands of incorrect debts, reduced meaningful human oversight, shifted the burden of proof onto recipients, and caused significant financial and psychological harm before the scheme was ruled unlawful. |

---

## Reports and Alleged Causes – Incident 57

When I reviewed the Robodebt entry, AIID listed 39 supporting reports. These included articles from organisations such as the ABC, SBS, *The Guardian*, and *The Sydney Morning Herald*, as well as court decisions, parliamentary inquiries, official government reports, and the Royal Commission.

The alleged causes focused less on software faults and more on poor governance. They included the use of income averaging to calculate debts, flawed assumptions about government data, limited human oversight, a lack of transparency, and shifting the burden onto welfare recipients to prove a debt was incorrect. The scheme also continued despite legal and operational concerns.

The AIID separates the incident itself from the evidence supporting it. Multiple reports are grouped together to document a single incident, creating a clear evidence trail rather than treating every article as a separate event. I think this demonstrates that AIID records incidents when there is credible, publicly available evidence linking an AI or automated system to real-world harm.

---

## Reflection

This activity changed the way I think about AI governance. Before this week I mostly associated AI risks with advanced machine learning models, but Robodebt showed that poorly governed automated systems can be just as harmful. As someone studying cybersecurity, I can already see strong links between AI governance and security governance, particularly around accountability, risk management, and protecting people from technology that is not properly controlled.

---

## References

- [AI Incident Database: Incident 557](https://incidentdatabase.ai/cite/557/)
- [AI Incident Database: Incident 57](https://incidentdatabase.ai/cite/57/)
- [Royal Commission into the Robodebt Scheme](https://robodebt.royalcommission.gov.au/)

---

# Task 2 – MIT AI Risk Repository

## Overview

The [MIT AI Risk Repository](https://airisk.mit.edu/risks) is a taxonomy of AI risks drawn from more than 70 existing frameworks. It classifies risks using two perspectives: the **Domain Taxonomy**, which identifies the type of harm, and the **Causal Taxonomy**, which explains how that harm occurred. Together, these provide a structured way to analyse AI incidents beyond simply describing what happened.

---

## Domain Taxonomy Classification

### Incident 557 – Miami Police Facial Recognition

| Domain | Subdomain | Why it applies |
|---|---|---|
| **2. Privacy & Security** | **2.1 Compromise of privacy** | Clearview AI analysed facial images collected from public and social media sources, raising concerns about identifying individuals without meaningful consent or transparency. |
| **5. Human-Computer Interaction** | **5.1 Overreliance and unsafe use** | A facial recognition match should only be treated as an investigative lead. Relying on it without sufficient independent verification increases the risk of incorrect decisions. |
| **6. Socioeconomic & Environmental** | **6.5 Governance failure** | The undisclosed use of facial recognition during a public protest highlights shortcomings in oversight, accountability, and governance. |

I did not select **Discrimination & Toxicity** because this incident does not demonstrate that the arrest resulted from demographic bias. While facial recognition systems can perform unevenly across different groups, that broader risk is not established by the evidence presented for this case.

---

### Incident 57 – Robodebt

| Domain | Subdomain | Why it applies |
|---|---|---|
| **5. Human-Computer Interaction** | **5.2 Loss of human agency and autonomy** | Automated debt notices and limited human review made it difficult for recipients to understand or challenge decisions. |
| **6. Socioeconomic & Environmental** | **6.5 Governance failure** | The scheme continued despite concerns about its legality, data quality, and harmful impacts, reflecting failures in oversight and accountability. |
| **7. AI System Safety, Failures & Limitations** | **7.3 Lack of capability or robustness** | Income averaging could not accurately determine fortnightly earnings, leading to incorrect debt calculations. |

These classifications show that both incidents involved more than technical failures. The greatest risks arose from the interaction between technology, governance, organisational decisions, and the people affected.

---

## Causal Taxonomy Classification – Robodebt

| Causal factor | Classification | Reasoning |
|---|---|---|
| **Entity** | **Human** | Human policy and design decisions were the primary cause. The system simply executed those decisions. |
| **Intent** | **Unintentional** | The objective was debt recovery and administrative efficiency, not widespread harm, even though the consequences became severe. |
| **Timing** | **Post-deployment** | The documented harm occurred after the system was deployed and debt notices were issued. |

The classification is not entirely clear-cut. The automated system directly contributed to individual debt decisions, while flaws in the system were introduced before deployment. I classified the incident as **Human** and **Post-deployment** because they best represent the primary cause and when the harm occurred. The fact that other frameworks classify the entity differently demonstrates that risk taxonomies support informed judgement rather than providing a single definitive answer.

---

## Reflection

This activity showed me that AI incidents rarely fit into a single category. Technical limitations, organisational decisions, governance failures, and human oversight all contribute to the final outcome. Using the MIT AI Risk Repository helped me move beyond describing an incident and instead analyse why it occurred and which risks were most significant.

---

## References

- [MIT AI Risk Repository](https://airisk.mit.edu/risks)
- [The AI Risk Repository: A Meta-Review, Database and Taxonomy of Risks from Artificial Intelligence](https://futuretech.mit.edu/publication/the-ai-risk-repository-a-meta-review-database-and-taxonomy-of-risks-from-artificial-intelligence)

---

# Task 3 – AI in My Daily Life

## AI Systems I Use

| AI system | Lecture type | How I used it |
|---|---|---|
| **ChatGPT** | **Generative AI / LLMs** | I used ChatGPT to research concepts, organise information, review my work, and improve my understanding of course content. |
| **YouTube** | **Recommender System** | YouTube recommended videos based on my viewing history and interactions, influencing the content shown on my homepage. |
| **Apple Face ID** | **Computer Vision / Biometrics** | Face ID analysed my facial features to verify my identity and unlock my phone securely. |
| **Gmail Spam Filtering** | **Automated Decision-Making** | Gmail automatically classified incoming emails and filtered suspected spam before they reached my inbox. |

---

## Reflection

This exercise made me realise how often I interact with AI without consciously thinking about it. While tools such as ChatGPT are obvious examples, systems like recommender algorithms, facial recognition, and spam filtering have become routine parts of everyday technology. Each performs a different role, but they all raise important questions about accuracy, transparency, privacy, and human oversight.

---

# Week 1 Reflection

As someone studying cybersecurity, I found strong parallels between AI governance and information security governance. Both disciplines emphasise risk management, accountability, transparency, and protecting people from unintended consequences arising from technology.

This week also showed me that AI governance is not only concerned with advanced models. Rules-based automation, biometric systems, and recommendation algorithms can all create serious risks when they are poorly designed, weakly governed, or used without meaningful oversight.
