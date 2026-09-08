Week 6 – EU AI Act Risk Classification and Watermarking

Overview

This week continued with the Saltbush Group hiring classifier from Weeks 4 and 5, but introduced the EU AI Act and looked at what happens when the system is used outside Australia.

The scenario now involved Saltbush using the classifier to shortlist applicants for jobs in Dublin. This created an important change because the system’s outputs are now being used within the European Union, even though Saltbush is an Australian organisation and the system is hosted in Sydney.

The activities focused on classifying the hiring system under the EU AI Act, comparing the responsibilities of Saltbush and the vendor, examining possible proxy variables for protected characteristics, assessing claims made by the vendor, and seeing how changing the purpose of an AI system can change its legal classification.

The final activity moved away from recruitment and looked at AI-generated image provenance. I tested Content Credentials and Google’s SynthID using a supplied image of a supposed Byzantine icon and then modified the image in several ways to see how well the different detection methods survived.

⸻

Task 1 – Classifying Saltbush’s Shortlisting System

Scope and Roles

Saltbush purchased the classifier from an external vendor and uses it without modifying it.

For this scenario:

* Saltbush is the deployer
* The vendor is the provider

The fact that a recruiter can override the classifier does not remove the influence the system has over applicants. The classifier still ranks applicants and recommends who should be shortlisted for an interview.

The system is also within the scope of the EU AI Act because its outputs are being used for recruitment in Dublin.

Article 2(1)(c) covers situations where a provider or deployer is located outside the EU but the output produced by the AI system is used within the EU.

Because the classifier is being used to evaluate applicants for employment, the relevant high-risk classification comes from Article 6 and Annex III.

Compliance Checker Results

I completed the Future of Life Institute EU AI Act Compliance Checker twice so I could compare Saltbush’s responsibilities with those of the vendor.

Run	Result	Main provision	Obligations shown
Saltbush as deployer	High-risk AI system	Article 6 and Article 26	10 main deployer obligations, plus AI literacy and conditional requirements
Vendor as provider	High-risk AI system	Article 6 and Article 16	12 main provider obligations, plus AI literacy

Evidence

* Saltbush deployer checker screenshot
* Saltbush deployer result text
* Vendor provider checker screenshot
* Vendor provider result text

The risk classification did not change between the two runs because the purpose of the system remained the same.

What changed was the type of responsibility.

The vendor has responsibilities associated with developing and demonstrating compliance of the system, including areas such as technical documentation, conformity assessment, quality management and corrective action.

Saltbush’s responsibilities are more focused on how the system is actually used, including human oversight, monitoring, input data, logging and responding to problems.

The checker was useful for identifying these differences, but completing the checker does not prove that Saltbush or the vendor is compliant.

There is still information I would want before making that judgement, including:

* technical and bias-testing documentation,
* information about who controls the system logs,
* evidence of actual human oversight,
* information about data-protection responsibilities,
* when the system was first placed into service, and
* whether significant changes have been made to the system.

⸻

Features That Could Act as Proxies

Removing protected characteristics from a dataset does not automatically remove the possibility of discrimination.

Several features used by the Saltbush classifier could potentially act as proxies for other characteristics.

Feature	Possible proxy	Potential problem	Evidence I would need
Continuous employment, with penalties for breaks longer than six months	Gender or disability	Parental leave, caring responsibilities or extended illness could create employment gaps unrelated to someone’s current ability to perform the job	Compare employment-gap patterns and selection outcomes between appropriate groups
Year of earliest qualification	Age	Qualification dates can provide an approximate indication of someone’s age	Examine how the model uses qualification dates and compare similar applicants
Postcode-derived distance band	Race, ethnicity or socioeconomic position	Residential patterns could cause particular communities to receive systematically different scores	Compare local demographic information with model outcomes and determine whether distance is genuinely required for the job

Other features such as experience, qualifications and keyword matching could also require investigation.

However, a feature being correlated with a protected characteristic does not automatically prove discrimination. Evidence would still be required to determine how the classifier actually uses that information.

The scenario also contains a likely_gender field, but it is stated to be used for correspondence rather than as an input to the classifier.

For that reason, I would not use the existence of this field as evidence that the classifier directly considers gender.

It would also be unreliable to use gender inferred from someone’s first name as the main basis for a fairness audit.

Connection to Week 4

In Week 4, I found the following selection rates:

* Group A: 60%
* Group B: 30%

This created a 30 percentage-point difference and a selection-rate ratio of 0.50.

Those results provide a reason to investigate the classifier, but they do not tell us what caused the difference or prove that one particular feature was responsible.

Do the Proxy Features Change the Risk Classification?

No.

The classifier is high risk because it is being used to evaluate people for employment.

Changing or removing individual features does not change that purpose.

The proxy features instead affect the fairness risks that Saltbush and the vendor need to investigate.

⸻

Provider Obligations and Bias

One of the biggest concerns for the vendor is data governance and the requirement to examine and address possible bias.

Article 10 includes requirements relating to the quality and governance of data used by high-risk AI systems.

Simply saying that protected characteristics are not included as inputs does not demonstrate that the system is fair.

For example, postcode, employment history or qualification dates may still produce unequal outcomes even if gender or age are not directly supplied to the classifier.

The vendor would therefore need evidence showing that the relevant datasets and model behaviour have been examined for bias.

A two-page feature description and a statement that protected attributes have been removed would not be enough evidence for me to accept that the issue had been properly addressed.

⸻

Using Protected Attributes for Fairness Testing

Using protected or demographic information during a controlled fairness audit can sometimes improve the organisation’s ability to identify unequal outcomes.

The important distinction is that this information should be used for auditing rather than becoming another input used by the classifier to rank applicants.

Any fairness audit should also use accurate information rather than guessing characteristics from names.

Access should be restricted, the information should only be kept for as long as necessary, and Saltbush would still need to meet its privacy and data-protection obligations.

The EU AI Act provides a controlled pathway for processing certain sensitive information for bias detection and correction, but this does not create unlimited permission to collect demographic information.

The organisation would still need to justify why the information is necessary and how it will be protected.

⸻

Task 2 – Responding to the Vendor’s Claims

The vendor made several claims about why Saltbush should not be concerned about the EU AI Act.

I assessed each claim separately.

Vendor claim	My assessment	Reason
Australia and Sydney hosting mean the EU AI Act does not apply	Disagree	The classifier’s outputs are being used for recruitment in Dublin, creating the required connection with the EU
Shortlisting is only a narrow procedural task	Disagree	Ranking applicants directly influences who receives an interview
Removing protected inputs removes the fairness problem	Disagree	Proxy variables and unequal outcomes can still exist
High-risk requirements are delayed, so nothing needs to be done now	Partly agree with the timing, but disagree with the conclusion	Some high-risk obligations are deferred, but other requirements and existing privacy and discrimination responsibilities still matter
The proposed enthusiasm-scoring feature is high risk and can be used if documented properly	Disagree	Workplace emotion inference using biometric information can fall within prohibited AI practices

The final claim was particularly important.

If the proposed feature analyses someone’s face or voice to determine whether they appear enthusiastic or confident during an interview, documentation would not automatically make that use acceptable.

A prohibited AI practice cannot simply be converted into a compliant one by creating more paperwork.

⸻

Who Checks the Checker?

I also looked at the information provided by the compliance checker itself.

Item	Recorded information
Latest changelog entry	3 July 2025
Official text the checker says it reflects	13 June 2024

The checker is provided by the Future of Life Institute rather than an EU institution.

This means I would treat it as a useful classification tool rather than official proof of legal compliance.

This became especially important because the legislation has continued to change since the dates shown by the checker.

What Obligations Apply Now?

As of 8 September 2026, the main Annex III high-risk deployer obligations shown by the checker have not all begun applying through the current timetable.

AI literacy requirements already apply.

The current timetable recorded during the activity was:

Date	Stage
2 February 2025	Chapters I and II, including AI literacy and original prohibited practices
2 August 2025	General-purpose AI model obligations begin, subject to transition arrangements
2 August 2026	Article 50 transparency requirements generally begin
2 December 2026	Additional transparency transition requirements and new prohibited practices
2 December 2027	Annex III high-risk requirements and obligations
2 August 2028	Relevant high-risk regulated-product requirements

The classifier has already been operating for approximately eighteen months.

This means its deployment history and any significant changes made to the system would also need to be considered rather than assuming that every future requirement automatically applies to an unchanged existing system.

⸻

Which System Is the More Urgent Problem?

The proposed enthusiasm-scoring system creates the most immediate legal concern because Saltbush should not deploy a system that performs prohibited workplace emotion inference.

However, the existing hiring classifier creates a different problem.

It is already operating and Week 4 identified a substantial difference between Group A and Group B selection rates.

I would therefore treat them as two different types of urgency:

* Do not deploy the proposed emotion-scoring feature
* Investigate the fairness of the existing classifier

⸻

What Is the Compliance Checker Good For?

I think the checker is useful for:

* identifying an initial AI Act risk classification,
* identifying possible obligations,
* comparing provider and deployer responsibilities, and
* identifying legislation that needs further investigation.

I would not use the checker by itself to declare that an organisation is legally compliant.

The output still needs to be checked against the legislation and the actual facts surrounding the AI system.

⸻

Task 3 – Changing the Use and Reassessing the Risk

This activity demonstrated how much the purpose of an AI system matters when determining its risk classification.

I tested or assessed several different uses.

Scenario	Result	Reason	Evidence
Sort ordinary supplier invoices by urgency	Minimal risk	The system is no longer being used for employment decisions or another identified high-risk purpose	Invoice checker run
Score interview enthusiasm or confidence from biometric video cues	Prohibited	Workplace emotion inference can fall under Article 5 prohibited practices	Enthusiasm checker run
Add a conversational explanation system for rejected applicants	Hiring remains high risk with additional transparency considerations	The underlying employment system remains high risk and the conversational system introduces direct AI interaction with applicants	Analysis based on Article 50

The first scenario was particularly useful because the underlying technology could potentially remain similar while its legal classification changes because its purpose has changed.

Sorting ordinary invoices does not affect someone’s access to employment, so the high-risk employment classification no longer applies.

The enthusiasm-scoring scenario moved in the opposite direction.

Instead of simply becoming another high-risk recruitment tool, emotion inference in the workplace can fall into the prohibited category.

⸻

Conversational Explanations for Rejected Applicants

Adding an AI chatbot that explains rejection decisions would not remove the original high-risk classification.

The hiring system would still be influencing employment decisions.

The conversational system would introduce additional transparency considerations because applicants would be interacting directly with AI.

Applicants should be clearly told that they are interacting with an AI system unless this is already obvious.

I would also provide a clear way for applicants to request human review.

Another important control would be ensuring that the chatbot only explains genuine reasons associated with the recruitment decision.

A language model generating a convincing but incorrect explanation would create another governance problem rather than solving the first one.

⸻

Task 4 – Testing the Byzantine Icon

The final activity involved a supplied image of a supposed Byzantine icon.

The image shows a haloed figure in traditional religious iconography holding an electric guitar.

That immediately creates a fairly obvious problem with the claim that the object is an authentic eleventh-century Byzantine icon.

The scenario also included other warning signs such as limited provenance, a single photograph and a recently created seller account.

These details would make me want additional evidence before accepting the seller’s claims.

⸻

Original Image

The supplied image was:

* 992 × 1075 pixels
* JPEG format

Its SHA-256 hash was:

d28322208d7dde75728b9ef868a389c2bf2534dbf9cc9c7efe0c8e50db3a5ad5

I first tested the original image using the Content Credentials verifier.

The verifier identified AI-generation provenance associated with Google LLC, with Google Media Processing Services shown as the issuer.

The credentials showed an issuance time of 24 August 2026 at 10:57 PM GMT+10.

Evidence

* Original Content Credentials result
* Gemini baseline response
* Complete Gemini lab transcript

Gemini also reported that the original contained a valid watermark.

However, its initial explanation mixed information from Content Credentials with its SynthID result.

For the later tests, I specifically asked Gemini to separate the watermark result from metadata and visual analysis.

⸻

Content Credentials and SynthID

The two systems work differently.

Content Credentials provide provenance information associated with the file.

SynthID places a signal within the media itself.

This means modifying or exporting a file may remove its original provenance information while a watermark embedded into the visual content may still survive.

I wanted to test how this difference behaved in practice.

⸻

Predictions and Transformations

Before testing the modified images, I recorded what I expected to happen.

Each transformation was created from the original image rather than applying modifications on top of previous modifications.

Attempt	My prediction	Content Credentials result	SynthID result	Image usefulness
Original	Provenance and watermark should both remain	Google-issued AI-generation credentials detected	Gemini reported watermark present	Detailed enough for a listing, although the electric guitar remains an obvious problem
Screenshot, crop and JPEG save at 260 × 282	Credentials would probably disappear but the watermark might survive	Original embedded provenance was no longer present in local header inspection	Positive according to Gemini	Recognisable but too small for detailed inspection
JPEG quality 20 at 992 × 1075	Export may remove credentials but SynthID may survive compression	Embedded provenance was no longer present	Positive according to Gemini	Still usable as a listing image despite visible compression
Resize to 124 × 134 and enlarge back to 992 × 1075	Severe resizing might interfere with watermark detection	Embedded provenance was no longer present	Positive according to Gemini	Clearly degraded and unsuitable for properly inspecting an expensive antique
Rotate seven degrees and export at JPEG quality 35	Geometric changes might interfere with detection	Embedded provenance was no longer present	Unavailable because Gemini reported a quota error	Still recognisable but the rotation and black corners reduce presentation quality

Evidence

* Prediction log
* Screenshot transformation
* JPEG quality 20 transformation
* Downscale and upscale transformation
* Rotated transformation
* File manifest

I also kept screenshots of the Content Credentials verifier during the transformed-image tests:

* Screenshot test
* JPEG compression test
* Resize test
* Rotation test

One limitation is that the Content Credentials verifier returned to its starting screen rather than displaying an explicit negative result for the transformed images.

Local inspection provided additional evidence.

The original JPEG contained three APP11 segments, while the transformed versions contained zero.

This supports the conclusion that the embedded provenance information was removed from the transformed files, but it does not test SynthID or prove that no other provenance information could exist elsewhere.

⸻

Reproducing the Image Transformations

The following macOS commands reproduce the JPEG compression, resizing and rotation tests:

sips -s format jpeg -s formatOptions 20 byzantine_icon.jpg --out icon-jpeg-q20.jpg
sips --resampleHeightWidth 134 124 byzantine_icon.jpg --out icon-small.jpg
sips --resampleHeightWidth 1075 992 -s format jpeg -s formatOptions 80 icon-small.jpg --out icon-down-up.jpg
sips --rotate 7 -s format jpeg -s formatOptions 35 byzantine_icon.jpg --out icon-rotate-7.jpg

The screenshot test was created by displaying the image at 260 pixels wide, taking a screenshot and cropping the image area before saving it as JPEG.

Because that test combines resizing, screenshot capture, cropping and JPEG conversion, it does not show which individual operation caused the change.

⸻

Which Detector Was Easier to Defeat?

The embedded Content Credentials were
