# Week 2 – Ethical Frameworks for AI

## Overview

This week focused on applying ethical frameworks to real-world AI incidents. I examined the **OECD AI Principles**, **Australia's AI Ethics Principles**, and the **ACS Code of Professional Ethics** and compared how each framework approaches issues such as safety, transparency, accountability, fairness and professional responsibility.

My assigned incident was **AIID 545, involving Tessa**, a chatbot used by the National Eating Disorders Association (NEDA). The incident provided an example of how changes to an AI system after its original development can introduce new risks, particularly when the system is being used with vulnerable people.

---

# Task 1 – First Impressions

## AIID 545 – Tessa and the National Eating Disorders Association

### Initial Reaction

My first impression was that using a chatbot to support people with eating disorders was not necessarily a bad idea, but replacing human support with it was a high-risk decision that required much stronger governance and oversight. AI could potentially assist trained staff, but it should not replace human support for vulnerable people without appropriate safeguards, particularly when incorrect advice could cause serious harm.

The two things that concerned me most were:

- Tessa recommended behaviours such as calorie counting, weight loss and body measurements to people seeking help for eating disorders.
- NEDA reportedly did not know that the vendor had introduced generative AI functionality into the platform.

### AI Type

I classified the incident as **Generative AI**. Tessa was originally designed as a rule-based chatbot providing scripted responses, but the incident scenario states that generative AI functionality was later introduced into the platform.

### Revisiting My First Impression

After applying the ethical frameworks, my original impression still mostly holds, but I now think the problem was much broader than simply replacing human support with a chatbot.

The frameworks highlighted problems throughout the governance of the system, including safety, transparency, accountability, human-centred design and professional responsibility. The reported introduction of generative AI functionality without NEDA's knowledge was particularly significant because it changed the behaviour and risk profile of the system.

I still believe AI could potentially support trained professionals in this area, but the Tessa incident demonstrates why a high-risk system needs continuous testing, monitoring, clear responsibility and meaningful human oversight throughout its lifecycle.

---

# Task 2 – Ethical Framework Mapping

| Framework | Principle | Judgement | Justification |
|---|---|---|---|
| **OECD** | Inclusive growth, sustainable development and well-being | Violated | Tessa was intended to support people at risk of eating disorders but instead gave advice that could worsen the very harm it was designed to prevent. |
| **OECD** | Human rights and democratic values, including fairness and privacy | Violated | The system was used with a vulnerable population and produced advice capable of undermining their wellbeing and autonomy. |
| **OECD** | Transparency and explainability | Violated | NEDA stated that it did not know generative AI functionality had been introduced, while users were given harmful advice without a clear explanation of how or why the system generated it. |
| **OECD** | Robustness, security and safety | Violated | Tessa failed to operate safely within its intended purpose and generated potentially harmful eating and weight-loss advice. |
| **OECD** | Accountability | Unclear | Tessa was developed by Cass and deployed by NEDA, while NEDA claimed the vendor introduced generative functionality without its knowledge. Responsibility therefore appears divided between multiple organisations. |
| **Australia** | Human, societal and environmental wellbeing | Violated | A system intended to support people with eating disorders instead produced advice that could contribute to further harm. |
| **Australia** | Human-centred values | Violated | Replacing human support with a chatbot in a sensitive context, followed by harmful advice, failed to adequately protect the needs and autonomy of vulnerable users. |
| **Australia** | Fairness | Unclear | The incident demonstrates harm to a vulnerable population, but the available evidence does not clearly show discriminatory or unequal treatment between different groups. |
| **Australia** | Privacy protection and security | Unclear | The incident information does not establish that personal information was improperly accessed, disclosed, or inadequately secured. |
| **Australia** | Reliability and safety | Violated | Tessa produced advice directly inconsistent with its intended role of supporting people affected by eating disorders. |
| **Australia** | Transparency and explainability | Violated | NEDA reportedly did not know generative functionality had been introduced, demonstrating a significant lack of transparency between the developer and deploying organisation. |
| **Australia** | Contestability | Unclear | Users publicly challenged Tessa's advice and the system was eventually removed, but it is unclear whether an accessible formal process existed for challenging its outputs. |
| **Australia** | Accountability | Violated | Appropriate responsibility and oversight were not maintained across Tessa's lifecycle, particularly when its functionality changed without NEDA reportedly knowing. |
| **ACS** | Honesty | Violated | NEDA initially disputed publicly reported evidence of harmful responses before the screenshots were verified, raising concerns about openness and truthful communication. |
| **ACS** | Trustworthiness | Violated | Deploying a system to vulnerable users without maintaining adequate knowledge, testing, oversight and control of its capabilities conflicts with trustworthy ICT practice. |
| **ACS** | Respect for Others | Violated | The system exposed vulnerable users to potentially harmful advice instead of minimising risks to those affected by the technology. |
| **ACS** | Respect for the Profession | Violated | The failure to adequately govern and monitor a high-risk support system undermined responsible use of ICT and public confidence in technology. |

---

# Task 3 – Areas of Disagreement

There were several principles where I did not think the available evidence justified a clear violation.

I classified **Privacy Protection and Security** and **Fairness** under Australia's AI Ethics Principles as unclear. Although Tessa produced harmful advice, the incident does not provide enough evidence to demonstrate that personal information was compromised or that the system discriminated unfairly between different groups.

I also classified **Contestability** as unclear. Users were able to publicly challenge Tessa's responses and the chatbot was eventually removed, but this does not demonstrate that NEDA had a formal process allowing users to challenge AI outputs or request human review.

This showed me that a serious AI incident does not automatically mean that every ethical principle has been violated. Each judgement still needs to be supported by evidence from the incident.

---

# Task 4 – Where the Frameworks Disagree

## Point of Divergence

Although the frameworks share many similar principles, one important difference in the Tessa incident is how they approach **contestability and professional responsibility**.

Australia's AI Ethics Principles include **Contestability as a separate principle**, requiring people affected by an AI system to have a way to challenge its use or outcomes. The OECD framework does not identify contestability as a standalone principle, instead addressing similar concerns more broadly through **Accountability**.

The ACS Code approaches the issue differently again because it focuses on the responsibilities of individual ICT professionals through principles such as **Trustworthiness** and **Respect for Others**.

### What Would an Adviser Do Differently?

If advising NEDA using **Australia's AI Ethics Principles**, I would focus strongly on whether users had a clear way to question Tessa's advice, report harmful responses and have those concerns reviewed by a person. In this incident, users eventually challenged Tessa publicly, but this is different from having a formal contestability process built into the service.

Using the **OECD AI Principles**, I would focus more broadly on who was accountable for ensuring Tessa remained safe after deployment. This would include determining responsibility between NEDA and Cass when generative AI functionality was reportedly added without NEDA's knowledge.

Using the **ACS Code of Professional Ethics** would shift my attention towards the ICT professionals involved. A developer who became aware that Tessa was providing potentially harmful advice would have professional responsibilities relating to trustworthiness, communicating risks, minimising harm and acting responsibly rather than simply assuming that responsibility belonged to the organisation.

## Which Framework Would Help Me Most as a Graduate Developer?

As a graduate developer working on Tessa, I think the **ACS Code of Professional Ethics would help me most** because it directly relates to my responsibilities as an ICT professional. If I discovered that the chatbot was giving harmful advice, the ACS principles would help guide what I should personally do, including raising concerns, communicating limitations and attempting to minimise harm.

The **OECD framework would probably leave me the most stuck**. Its principles are useful for assessing whether the overall AI system is trustworthy, but they provide less direct guidance about what I should personally do as a junior developer when I discover a problem.

Australia's framework sits somewhere between the two. It provides more specific expectations around issues such as **contestability**, but it is still primarily useful for evaluating how the AI system and organisation should operate rather than defining my individual professional obligations.

### Reflection

This comparison showed me that frameworks can agree on the same ethical concerns while still being useful in different ways. Australia's framework would make me ask whether users could challenge Tessa's outputs, the OECD framework would make me examine accountability across the system, and the ACS Code would make me consider my own responsibility as an ICT professional.

For someone working directly on an AI system, I think that difference is important because identifying an ethical problem is only useful if you also know what responsibility you have to act on it.

---

# Week 2 Reflection

This week showed me that ethical frameworks are not simply different versions of the same checklist. Although they share principles such as fairness, transparency, safety and accountability, they can make you look at the same incident from different perspectives.

The Tessa incident particularly demonstrated the importance of governance throughout the entire lifecycle of an AI system. A system may have originally been designed and tested for one purpose, but changes made after deployment can introduce completely different risks. Organisations therefore need to understand what their AI systems are actually doing, monitor changes made by third-party vendors and establish clear responsibility when something goes wrong.

From the perspective of someone entering the ICT industry, I found the ACS Code particularly relevant because it moves the question from **"Was this system responsibly governed?"** to **"What responsibility would I personally have if I discovered the problem?"**

---

# References

Australian Computer Society. (2023). *ACS code of professional ethics*.  
https://www.acs.org.au/content/dam/acs/ACSimages/ethicsdiscipline/CodeOfProfessionalEthics_Mar_2023.pdf

Australian Government Department of Industry, Science and Resources. (n.d.). *Australia's artificial intelligence ethics principles*.  
https://www.industry.gov.au/publications/australias-artificial-intelligence-ethics-principles

AI Incident Database. (n.d.). *Incident 545: Tessa and the National Eating Disorders Association*.  
https://incidentdatabase.ai/cite/545/

Organisation for Economic Co-operation and Development. (n.d.). *OECD AI principles*.  
https://oecd.ai/en/ai-principles

UNESCO. (2021). *Recommendation on the ethics of artificial intelligence*.  
https://www.unesco.org/en/artificial-intelligence/recommendation-ethics
