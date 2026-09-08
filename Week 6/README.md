Week 6 – EU AI Act Risk Classification and Watermarking

Overview

This week focused on the EU AI Act and how the risk classification of an AI system depends on how and where the system is being used.

The activities continued with the Saltbush Group hiring classifier from Weeks 4 and 5. This time, Saltbush has expanded its recruitment into Dublin, which means the classifier now has a connection to the European Union.

I used the EU AI Act Compliance Checker to classify the system from both the deployer and provider perspectives. I then examined several features used by the classifier that could act as proxies for protected characteristics, assessed claims made by the vendor, changed the purpose of the system to see how its risk classification changed, and investigated a proposed video interview feature that would attempt to measure applicant enthusiasm and confidence.

The second part of the week focused on AI-generated image transparency. I tested an image containing both Content Credentials and Google’s SynthID watermark and then modified the image in several ways to see whether those signals survived.

The main thing I found this week is that AI risk classification depends heavily on context. The same underlying technology can move from minimal risk to high risk or even prohibited depending on what it is being used to do.

⸻

Task 1 – Classifying the Saltbush Shortlisting System

Does the EU AI Act Apply?

Saltbush is an Australian organisation and the classifier is hosted in Sydney. However, Saltbush is now using its output to help shortlist applicants for jobs in Dublin.

This means the EU AI Act can still apply.

Article 2(1)(c) covers providers and deployers located outside the European Union where the output produced by an AI system is used within the EU.

Saltbush therefore cannot avoid the Act simply because the organisation and its servers are located in Australia.

For the existing classifier:

* Saltbush is the deployer because it purchased and uses the classifier without modifying it.
* The vendor is the provider because it supplies the AI system.

The classifier is used to rank applicants and influence who receives an interview. Recruitment and applicant evaluation are listed as high-risk uses under Article 6 and Annex III of the AI Act.

Compliance Checker Results

I completed the Future of Life Institute EU AI Act Compliance Checker twice: once for Saltbush as the deployer and once for the vendor as the provider.

Run	Result	Main provision	Checker result
Saltbush as deployer	High-risk AI system	Article 6 and Article 26	10 main deployer obligations, plus AI literacy and conditional obligations
Vendor as provider	High-risk AI system	Article 6 and Article 16	12 main provider obligations, plus AI literacy

Evidence:

* Saltbush deployer checker screenshot
* Saltbush deployer checker result
* Vendor provider checker screenshot
* Vendor provider checker result

The risk classification did not change between the two runs. The difference was in the responsibilities attached to each role.

The provider has more responsibility for demonstrating that the AI system itself meets the requirements of the Act. The checker identified areas such as technical documentation, quality management, conformity assessment, registration and corrective action.

Saltbush’s responsibilities as the deployer are more focused on how the classifier is actually used. These include human oversight, monitoring, input data, logging and responding appropriately when problems are identified.

The obligation counts above are the number of items displayed by the checker. They should not be treated as a complete count of every possible legal obligation that could apply.

Information I Would Still Need

The checker gives Saltbush a useful starting point, but selecting answers in a compliance checker does not prove that the organisation is compliant.

Before making a stronger assessment, I would want to know:

* what bias testing the vendor has performed,
* what technical documentation exists,
* who controls and reviews the classifier’s logs,
* how recruiters actually provide human oversight,
* what data-protection arrangements exist,
* when the classifier was first placed into service, and
* whether Saltbush or the vendor has made significant changes to it.

This is similar to the issue I found with ISO/IEC 42001 in Week 5. A claim about governance or compliance is only as useful as the evidence supporting it.

⸻

Features That Could Act as Proxies

Saltbush and the vendor argue that the classifier does not use protected attributes such as gender directly.

However, removing a protected attribute does not necessarily remove the information associated with it.

Several of the remaining features could potentially act as proxies.

Feature	Possible connection	Potential problem	Evidence I would want
Continuous employment, with penalties for breaks over six months	Gender and potentially disability	Applicants who have taken parental, caring or extended health-related leave could be disadvantaged even when the employment break has little relationship to their ability to perform the job	Compare employment-gap patterns and selection outcomes between appropriate groups and test whether the penalty is actually job-relevant
Year of earliest qualification	Age	Qualification dates can provide information about someone’s approximate age	Examine how the model treats qualification dates and compare otherwise similar applicants
Postcode converted into near/far distance bands	Race, ethnicity or socioeconomic position	Residential patterns could cause particular communities to receive different scores	Examine local demographic information, model behaviour and whether distance is genuinely required for the role

These features do not prove that discrimination is occurring. However, they provide reasons to investigate whether apparently neutral inputs are producing unequal outcomes.

The scenario also contains a likely_gender field inferred from applicant names. This field is stated to be used for correspondence rather than as an input to the classifier, so I would not claim that Saltbush is directly using gender to calculate the score.

I would also be cautious about using inferred gender as evidence in a fairness audit because guessing gender from someone’s first name can itself be inaccurate.

Connection to Week 4

In Week 4, I calculated the following selection rates:

* Group A: 60%
* Group B: 30%

This is a 30 percentage-point difference, with Group B being selected at half the rate of Group A.

The sample was relatively small, so this result does not prove what caused the difference. It does, however, provide enough evidence to justify further investigation.

Do the Proxy Features Change the Risk Classification?

No.

The classifier is high risk because it is being used for recruitment and applicant evaluation.

Changing or removing individual features does not change that purpose. Instead, the features affect the kinds of bias risks Saltbush needs to investigate and manage.

A recruiter being able to make the final decision also does not automatically remove the high-risk classification when the AI system is still ranking and evaluating applicants.

⸻

Which Provider Obligation Concerns Me Most?

The area I would investigate first is the provider’s responsibility for data governance and identifying and addressing possible bias under Article 10.

The vendor has provided Saltbush with a two-page feature sheet and says protected characteristics are not used.

I do not think this is enough evidence.

Removing columns labelled gender, race or age does not demonstrate that the remaining data has been properly tested for bias or that proxy variables are not producing substantially different outcomes.

Other relevant areas include technical documentation and the information that providers are expected to give deployers.

At this stage, I would describe this as a governance and assurance gap rather than automatically claiming that the vendor has breached the Act. The actual application dates and transition arrangements also need to be considered.

⸻

Should Protected Attributes Be Used for a Fairness Audit?

I think carefully controlled use of accurate demographic information could actually put Saltbush in a better assurance position.

It is difficult to determine whether an AI system produces different outcomes between groups if the organisation has no reliable way to identify those groups.

However, this information should be kept separate from the classifier’s operational scoring and only used where necessary for the audit. Access, retention and privacy would also need to be controlled.

Where enough data exists, Saltbush could also examine intersectional effects rather than looking at each characteristic completely separately.

The amended EU AI Act provides a controlled route for providers and deployers to process certain sensitive information when it is genuinely necessary for detecting and correcting bias. This does not mean organisations have unrestricted permission to collect protected information.

⸻

Task 2 – Responding to the Vendor’s Claims

The next activity involved assessing several claims made by the classifier vendor.

Vendor claim	My assessment	Why
Australia and Sydney hosting mean the EU AI Act does not apply	Disagree	The classifier’s output is being used for recruitment in Dublin, creating the required EU connection
Shortlisting is only a narrow procedural task and is exempt	Disagree	Ranking applicants can materially influence whether someone receives an interview and is more than an administrative task
Removing protected inputs means there cannot be a fairness problem	Disagree	Proxy variables and unequal outcomes can still exist even when protected characteristics are removed
High-risk obligations do not apply until 2027, so nothing needs to be done now	Partly agree with the timing, but disagree with the conclusion	Some high-risk requirements are deferred, but other AI Act requirements already apply and existing privacy and discrimination responsibilities do not disappear
The proposed enthusiasm feature is high risk and can be used if properly documented	Disagree	If the feature infers emotions from biometric video or voice information in recruitment, it falls within the workplace emotion-recognition prohibition

The final claim is particularly important.

Saltbush is considering adding a system that would analyse video interviews and score candidates based on characteristics such as enthusiasm or confidence.

If the system attempts to infer a person’s emotional state using biometric information from their face or voice, Article 5’s prohibition on emotion recognition in workplaces becomes relevant.

Documentation does not turn a prohibited use into an acceptable high-risk use.

If the system instead assessed the actual content of an applicant’s answers against a skills rubric without attempting to infer emotions, it would need to be assessed differently.

⸻

Who Checks the Checker?

I also looked at the information provided by the Future of Life Institute compliance checker itself.

Item	Date shown
Latest changelog entry	3 July 2025
Official AI Act text the checker says it reflects	13 June 2024

The checker is produced by the Future of Life Institute rather than an EU institution.

This does not make it useless. I found it helpful for working through the classification process and identifying possible obligations.

However, I would not describe it as an official EU compliance tool.

The dates are also important because the checker predates the 2026 amendments to the AI Act. This means its output should be checked against the current legislation before relying on it.

⸻

Which Obligations Apply Now?

This was one of the more confusing parts of the activity because classification and application dates are separate questions.

Saltbush’s classifier can be classified as a high-risk system even though the main Annex III high-risk obligations have not all started applying yet.

As at 8 September 2026, the checker displayed 10 main high-risk deployer obligations, but those obligations have not yet begun applying through the Annex III timetable.

AI literacy is different because that requirement has already begun applying.

The current timetable I recorded was:

Date	Relevant stage
2 February 2025	Chapters I and II begin applying, including AI literacy and the original prohibited practices
2 August 2025	General-purpose AI model obligations begin, subject to transition arrangements
2 August 2026	Article 50 transparency requirements generally begin
2 December 2026	Additional transparency transition requirements and new prohibited practices
2 December 2027	Annex III high-risk requirements and obligations
2 August 2028	Relevant high-risk requirements for regulated-product systems

There is another complication because Saltbush’s classifier has already been operating for approximately 18 months.

The AI Act contains transition arrangements for some systems that were already in use. This means I would need to establish when this particular deployment began and whether significant changes have been made before claiming that every high-risk obligation automatically applies to it from December 2027.

This reinforced an important point for me: being classified as high risk does not automatically tell me which obligations apply today.

⸻

Which System Is the More Urgent Problem?

The proposed enthusiasm-scoring system creates the most urgent legal decision because Saltbush should not deploy it if it performs prohibited workplace emotion recognition.

However, the existing classifier creates the more immediate operational fairness problem because it is already being used.

I therefore see the two problems differently.

The enthusiasm system requires a do not deploy decision.

The existing classifier requires Saltbush to investigate the fairness gap, improve monitoring and determine whether the system is producing unjustified differences between groups.

⸻

What Changes in December 2026?

The 2026 amendment also adds new prohibited practices involving certain AI-generated or manipulated non-consensual intimate material and child sexual abuse material.

These provisions are more specific than simply banning AI-generated images.

The distinction matters because it shows why reading the actual scope of a legal requirement is important instead of reducing it to a broad statement such as “AI-generated images become illegal.”

⸻

What Is the Compliance Checker Good For?

I would use the checker as:

* a starting point for classification,
* a way of identifying relevant sections of the Act, and
* a checklist of issues that need further investigation.

I would not use it as proof that an organisation is legally compliant.

The final decision should be based on the current legislation and evidence about how the AI system actually works and is being used.

⸻

Task 3 – Changing the Use and Reassessing the Risk

The next activity demonstrated how much the purpose of an AI system affects its classification.

I changed what the system was being used to do and compared the results.

Scenario	Result	Why
Sort ordinary supplier invoices by urgency	Minimal risk	The system is no longer being used for recruitment or another high-risk purpose
Score interview enthusiasm or confidence from biometric video cues	Prohibited	Workplace emotion inference using biometric information is prohibited
Add a conversational explanation system for rejected candidates	Hiring system remains high risk, with additional transparency considerations	The underlying recruitment use remains high risk and candidates are now directly interacting with AI

Evidence:

* Invoice checker result
* Enthusiasm checker result

The invoice example was particularly useful because the underlying technology could still be some form of AI classifier, but its legal risk classification changed because its purpose changed.

Sorting invoices does not have the same effect on a person’s employment opportunities as ranking job applicants.

The enthusiasm example went in the opposite direction. Instead of simply becoming more heavily regulated, the proposed use crossed into a prohibited category.

⸻

Conversational Explanations for Rejected Applicants

Saltbush could also add a conversational AI system that explains decisions to rejected applicants.

This would not remove the high-risk classification of the recruitment system.

It would instead create additional transparency issues because candidates would now be interacting directly with AI.

I think candidates should be clearly told that they are interacting with an AI system unless this is already obvious. This information should appear at the beginning of the interaction rather than being hidden somewhere in a privacy policy.

There should also be a practical way to request human review.

Another important issue would be making sure the explanation reflects the real reason for the classifier’s recommendation. A language model generating a believable explanation is not useful if that explanation does not match what actually influenced the decision.

The organisation would also need to determine who is acting as the provider of the conversational system. If Saltbush develops and releases the front-end itself, its responsibilities could be different from simply deploying a system supplied by the existing vendor.

⸻

Task 4 – Testing the Byzantine Icon’s Provenance

The final activity moved away from the Saltbush classifier and focused on AI-generated image transparency.

The supplied image supposedly showed an eleventh-century Byzantine religious icon being sold at auction.

There was one fairly spectacular problem with that claim.

The figure in the image is holding an electric guitar.

That does not by itself tell me exactly how the image was created, but it gives me a very good reason to question the claimed provenance of the object.

The listing also had limited provenance information, only one photograph and a recently created seller account.

I therefore tested the supplied image using Content Credentials and Google’s SynthID verification.

⸻

Original Image

The supplied byzantine_icon.jpg was a 992 × 1075 JPEG.

Its SHA-256 hash was:

d28322208d
