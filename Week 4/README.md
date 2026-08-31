# 🔐 Week 3 – Australian Law, Privacy and AI Systems

## 📘 Overview

This week focused on the legal, social and cultural responsibilities that apply when AI systems are used in Australia. The activities examined the **Australian Privacy Principles (APPs)**, privacy controls in consumer AI products, and **Indigenous Data Sovereignty**.

For the practical audit, I examined **OpenAI ChatGPT** as a consumer AI product and compared its privacy policy and available product controls against **APPs 1, 3, 6, 10 and 11**. The scenario involved a Rivergum University admissions officer, Priya, pasting student enquiry emails into a commercial AI tool to help draft replies without approval from IT or compliance.

The main question was whether this creates privacy implications for the university and the students whose information is being entered into the system.

---

# ⚙️ Task 2 – Privacy Control Audit

## 🔎 Switch Hunting

I tested ChatGPT while **signed out**, without creating or logging into an account. This followed the lab suggestion to use a private browser session and avoid unnecessary sign-ups.

The main privacy controls available to me were located under:

**Settings → Data Controls**

| Looking for | How far did I get? | Setting | Access | Default |
|---|---|---|---|---|
| **Training opt-out** | Found and could change it | **Improve the model for everyone** | Settings → Data Controls | **On** |
| **History and retention** | Could only confirm through OpenAI documentation because chat history controls require an account | **Archived Chats** and Temporary Chat | Available after signing in | Standard chats are retained until deleted. Temporary Chats are automatically deleted after 30 days. |
| **Export or deletion** | Could only confirm through OpenAI documentation because export is unavailable while logged out | **Export data** and **Delete account** | Available after signing in | User initiated. OpenAI states deleted data is generally removed within 30 days. |

### Evidence

While signed out, the **Data Controls** panel showed **Improve the model for everyone**, **Marketing measurement**, and **Personalized marketing** enabled by default.

The other controls could not be tested directly without signing into an account, so I used OpenAI's Help Centre documentation to confirm how they operate.

One thing I noticed was that some OpenAI documentation still refers to a **"Chat history & training"** setting, while the current product calls the setting **"Improve the model for everyone."** This demonstrates how documentation can sometimes lag behind changes made to a live product.

---

# 🧾 Task 3 – Australian Privacy Principles Audit

## APP 1, 3, 6, 10 and 11

| APP | Requirement | What the policy says | What I observed | Judgement |
|---|---|---|---|---|
| **APP 1** | Open and transparent management of personal information | OpenAI publishes a dated privacy policy explaining the information it collects, how it is used, disclosure, retention, controls and user rights. Information about complaints and overseas processing is more general. | This was mainly assessed through the privacy policy rather than the product itself. | ⚠️ **Unclear / Partial** |
| **APP 3** | Collection of solicited personal information | The policy states that OpenAI may collect account information, prompts and other content, communications, device and location information, and information publicly available on the internet for model development. | ChatGPT allowed prompts to be submitted while signed out, with the Privacy Policy available through the interface. | ⚠️ **Unclear** |
| **APP 6** | Use or disclosure of personal information | The policy explains that content may be used to improve or train models and provides an option to opt out. | **Improve the model for everyone** was enabled by default in the signed-out session and had to be manually disabled. | ⚠️ **Unclear / Potential concern** |
| **APP 10** | Quality of personal information | The policy provides ways to request correction or removal of inaccurate personal information, including inaccurate information produced about a person. | This could not be meaningfully tested without an account. | ⚠️ **Unclear** |
| **APP 11** | Security of personal information | OpenAI states that it uses commercially reasonable technical, administrative and organisational measures to protect personal information. The public privacy policy does not provide detailed information about individual security controls. | No detailed security controls were visible through the signed-out interface. | ⚠️ **Unclear** |

---

## 💭 My Assessment

The most difficult part of this task was avoiding the assumption that a privacy policy automatically proves compliance.

For example, OpenAI states that it uses security measures to protect personal information, but that statement by itself does not allow me to verify whether those controls satisfy APP 11. The same problem appears when assessing how information is used. A policy can explain what a company intends to do, but the actual product settings are also important.

The training setting was particularly interesting because **Improve the model for everyone** was enabled by default. This means a user needs to know the setting exists, find it, and manually disable it if they do not want their conversations used for model improvement.

---

# 🔍 Task 4 – Second Opinion

## Row 1 – APP 11 and Microsoft Copilot

The original judgement treated Microsoft's security information and ISO 27001 certification as enough evidence to declare the product compliant, even though the product itself had not been checked.

I do not think that is enough evidence.

An organisation-wide security certification can provide evidence that security processes exist, but it does not automatically prove how a particular AI product handles personal information.

### Revised Judgement

⚠️ **Unclear**

Microsoft's ISO 27001 certification is a positive indicator, but I would still need product-specific information about how Copilot protects conversation data before determining that it complies with APP 11.

---

## Row 2 – APP 6 and Microsoft Copilot

The second row concluded that Copilot was compliant because the policy did not mention training and a training setting could not be found.

I think this is another example where there is not enough evidence to make a clear judgement.

A policy not mentioning something does not prove that the practice does not occur. It could also mean that the information is unclear or located somewhere else.

### Revised Judgement

⚠️ **Unclear**

I would need further evidence, such as Microsoft's product documentation, enterprise terms or information about administrator controls, before determining whether conversation content is used for model training or another secondary purpose.

### 💭 Reflection

This exercise reinforced that **a lack of evidence should normally result in an unclear judgement rather than automatically assuming compliance**.

I applied the same approach to my ChatGPT audit. For APP 11, I could find general statements about security measures but could not independently verify the controls through the consumer product. I therefore classified it as unclear rather than compliant.

---

# 📌 Key Findings

The audit identified three main privacy concerns.

1. **Model improvement is enabled by default.** ChatGPT's **Improve the model for everyone** setting was enabled when I tested the product while signed out. A user needs to find and disable this setting if they do not want their conversations used for model improvement.
2. **Important controls require an account.** A signed-out user can access some privacy controls, but features such as chat history management, data export and account deletion require signing in.
3. **Public privacy information cannot prove every security control.** OpenAI states that it uses technical, administrative and organisational security measures, but the public privacy policy does not provide enough detail to independently assess all of those controls.

---

# 🏫 Response to Rivergum University

## What is Rivergum's exposure if Priya keeps pasting student emails into ChatGPT?

I think Rivergum University would have a genuine privacy and governance risk if Priya continued pasting student emails into a public consumer AI service without approval.

Student enquiry emails can contain personal information and may sometimes include sensitive information relating to health, disability, cultural circumstances or other personal matters. By copying an email into ChatGPT, that information is being provided to a third-party service for a purpose the student may not expect.

The risk becomes more significant because the tool has not been approved by Rivergum's IT or compliance teams. This means the university may not have completed a privacy assessment, established an appropriate agreement with the provider, or determined how student information is stored, processed, retained and secured.

The default model improvement setting also creates an additional concern because users need to actively disable it.

I would recommend that Rivergum **stop entering identifiable student information into an unapproved consumer AI service** until the tool has been formally assessed. If the university wants staff to use generative AI, it should establish an approved service, clear rules about what information can be entered, appropriate privacy controls and staff training.

This is not simply a productivity issue. It is an AI governance and privacy issue because the university remains responsible for how student information is handled.

---

# 🌏 Indigenous Data Sovereignty

## How Could Indigenous Data Sovereignty Affect an AI System?

Indigenous Data Sovereignty highlights an important limitation of looking at AI governance only through individual privacy law.

The Privacy Act mainly focuses on information about identifiable individuals. Indigenous Data Sovereignty also considers the rights and interests of **communities** in relation to data about their people, culture, knowledge and communities.

For example, a recommender system could potentially use aggregated or de-identified data relating to an Aboriginal or Torres Strait Islander community. The data may no longer identify individual people, but decisions made using that information could still affect the community.

This means developers should consider more than whether data has technically been de-identified. They should also consider who collected the data, what the original purpose was, whether the relevant community agreed to the new use, who controls how the data is used, whether the AI system could misrepresent or disadvantage the community, and how the community can challenge the use of the data.

The **Maiam nayri Wingara Indigenous Data Sovereignty principles** encourage greater Indigenous control over how Indigenous data is collected, accessed, interpreted and used.

Federation University's **FUA Copyright Deed** provides another useful example through its treatment of **Indigenous Cultural and Intellectual Property (ICIP)**. Where ICIP is involved, permission from a copyright owner may not be enough by itself. Relevant ICIP Rights Holders and cultural protocols also need to be considered.

I think the same idea is important when developing AI systems. Meeting the minimum requirements of privacy law does not automatically mean that the use of data is culturally appropriate or ethically responsible.

---

# 💭 Discussion Reflection

The hardest principle for me to assess was **APP 11**, because security claims are difficult to verify from a privacy policy alone. Statements such as "commercially reasonable" security measures provide some information, but they do not explain enough about the actual technical controls to independently determine compliance.

To make stronger judgements on the unclear areas, I would want access to additional evidence such as product-specific security documentation, enterprise agreements, data processing terms, independent security audits and the privacy controls available to signed-in users.

One thing that surprised me was that ChatGPT still exposed the **Improve the model for everyone** setting while signed out. However, other controls such as history management and data export were only available after signing in.

---

# 🧠 Week 3 Reflection

This week showed me that using AI responsibly involves more than checking whether the technology works correctly. Organisations also need to understand what information is being entered into an AI system, where that information goes, why it is being collected and who remains responsible for protecting it.

The Rivergum scenario demonstrated how easily **shadow AI** can create governance problems. Priya may only be trying to save time when responding to students, but copying student emails into an unapproved AI service can create privacy risks that the organisation may not even know exist.

I also found the Indigenous Data Sovereignty section important because it demonstrates that legal compliance is not always the same as responsible governance. An organisation might technically satisfy privacy requirements while still using community data in a way that ignores cultural ownership, expectations or appropriate consultation.

From a cybersecurity perspective, this week reinforced the connection between **privacy, security and AI governance**. Protecting information is not only about preventing unauthorised access. It also means controlling where data is sent, understanding how third parties use it and making sure technology is being used within appropriate organisational policies.

---

# 📚 References

- [OpenAI Privacy Policy](https://openai.com/policies/privacy-policy/)
- [OpenAI Data Controls FAQ](https://help.openai.com/en/articles/7730893-data-controls-faq)
- [OpenAI: How to Delete and Archive Chats](https://help.openai.com/en/articles/8809935-how-to-delete-and-archive-chats-in-chatgpt)
- [Office of the Australian Information Commissioner – Australian Privacy Principles](https://www.oaic.gov.au/privacy/australian-privacy-principles)
- [Maiam nayri Wingara – Indigenous Data Sovereignty](https://www.maiamnayriwingara.org/)

