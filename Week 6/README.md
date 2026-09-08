# Week 6 – EU AI Act Risk Classification and Watermarking

## Overview

This lab extends the Saltbush recruitment case from [Week 4](../Week%204/README.md) and [Week 5](../Week%205/README.md). It examines how hiring in Dublin changes the legal scope, why removing protected attributes does not remove bias, and how provider and deployer responsibilities differ. The practical activity compares Content Credentials with Google's SynthID using the supplied Byzantine icon image.

**Course:** ITECH2119 – AI Governance and Assurance  
**Analysis date:** 8 September 2026  
**Evidence:** Live compliance-checker runs, image transformations and recorded detector responses.  
**Completion boundary:** Written analysis, four checker runs and the watermark experiment are recorded below. SynthID survived the three completed transformed-image checks according to Gemini; the fourth returned a reported quota error. Defeating both detectors was not demonstrated. Tutor observation and the lab's in-session marks are not claimed.

The legal analysis uses the AI Act together with its 2026 amendment. The checker is an aid to classification; its displayed wording and dates are not a current compliance certificate.

---

# Task 1 – Classify Saltbush's shortlisting system

## Scope and role

Saltbush bought and uses an unmodified classifier, so it is the **deployer**. The vendor supplying the classifier is the **provider**. A recruiter being able to override its recommendations does not stop the classifier from influencing access to employment.

The relevant connection is that the classifier's output is used for recruitment in Dublin. Australian ownership and Sydney hosting do not remove it from scope: **Article 2(1)(c)** covers providers and deployers outside the EU where their system's output is used in the Union. The system ranks and evaluates applicants, making **Article 6(2), Annex III point 4(a)** the relevant high-risk route. [EU AI Act, Articles 2 and 6 and Annex III](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

## Checker inputs and results

The [Future of Life Institute checker](https://artificialintelligenceact.eu/assessment/eu-ai-act-compliance-checker/) was completed for both roles. The live version displayed the AI-system definition rather than a separate yes/no question. A classifier that infers rankings from applicant features fits that definition on the supplied facts.

| Input | Answer and basis |
|---|---|
| Role | Deployer for Saltbush; provider for the vendor comparison |
| Modification or rebranding | None for Saltbush; the scenario explicitly says it did not build or modify the system |
| Annex I, sections A and B | None of the listed product categories |
| Annex III use | Employment, worker management and access to self-employment |
| Significant influence/risk | Yes: ranking affects interview opportunities and evaluates individuals |
| Territorial connection | Output used in the EU |
| Exclusions | None established by the scenario |
| Prohibited practices | None for the original shortlisting classifier; the proposed video add-on is assessed separately |
| Article 50 features | None specified for the original non-conversational classifier |
| Public authority/public-service deployer | No, assuming Saltbush is the private distribution business described |

| Run | Actual result | Provision named in result | Displayed obligation count | Evidence |
|---|---|---|---|---|
| Saltbush as deployer | High-risk AI system | Article 6; deployer duties under Article 26 | 10 main deployer bullets, plus 1 AI-literacy topic; 3 additional conditional bullets | [Screenshot](evidence/checker-deployer.jpg), [result text](evidence/checker-deployer.txt) |
| Vendor as provider | High-risk AI system | Article 6; provider duties under Article 16 | 12 main provider bullets, plus 1 AI-literacy topic | [Screenshot](evidence/checker-provider.jpg), [result text](evidence/checker-provider.txt) |

These are counts of the **tool's displayed bullets**, not a count of every statutory obligation. The deployer result also lists conditions for public authorities, law enforcement and data-protection impact assessments. The first two do not match this scenario. The DPIA point needs a separate assessment and should not be silently counted as an unconditional additional duty.

The risk tier stayed the same. The provider result added responsibilities for designing and demonstrating compliance, including quality management, technical documentation, conformity assessment, registration and corrective action. The deployer result focused on using the system properly, human oversight, monitoring, input quality, logs and affected people.

**Information still needed:** the complete technical and bias-testing records; who controls the logs; actual oversight arrangements; data-protection roles and lawful bases; when the system was first put into service for the relevant deployment; and whether future changes would significantly alter its design. Selecting answers in a checker does not establish these facts.

## Features that can act as proxies

| Feature | Possible protected attribute | Who could be disadvantaged and why | Evidence needed |
|---|---|---|---|
| Continuous employment, penalising breaks over six months | Gender; potentially disability | People taking parental/carer leave or extended illness-related leave can receive a penalty unrelated to their present ability to do the job. Women may be disproportionately affected by parental-care patterns. | Compare gap patterns and selection outcomes using appropriate group labels; test whether the penalty is job-relevant |
| Year of earliest qualification | Age | Earlier qualification years can reveal approximate age. If the model favours recent qualifications, older applicants may lose out; the actual direction cannot be established without its learned behaviour. | Inspect feature effects and compare otherwise similar applicants with different qualification dates |
| Postcode-derived near/far distance band | Race/ethnicity through residential patterns; also socioeconomic position | Applicants in particular neighbourhoods may receive systematically different scores. A far-distance penalty can disadvantage groups concentrated outside the preferred area. | Local demographic evidence, the model's actual distance effect, and a justified connection to job requirements |

Experience, qualifications and keyword matching also deserve testing, but correlation alone does not establish unlawful discrimination. A proxy is a feature that carries information correlated with another characteristic; the model need not explicitly reconstruct a person's gender or age for unequal effects to occur.

The `likely_gender` field is stated to be used for correspondence, **not as a model input**. It must not be presented as proof that the classifier directly uses gender. Inferring gender from first names is also an unreliable basis for either respectful correspondence or a fairness audit.

Week 4 recorded selection rates of **60% for Group A and 30% for Group B**: a **30 percentage-point gap** and a **0.50 selection-rate ratio**. Those small samples flag a problem to investigate; they do not identify the cause or establish that Group B represents women. [Week 4 portfolio](../Week%204/README.md)

### Do the features change the tier?

No. Recruitment and applicant evaluation determine the Annex III classification. The features change the bias risks and the evidence needed to manage them, not the employment purpose. The profiling safeguard in Article 6(3) also prevents a provider from treating an Annex III profiling system as exempt merely because a human makes the final decision. [AI Act, Article 6](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

### Which provider obligation is the problem?

The strongest concern is **data governance and bias examination/mitigation under Article 10(2)(f)–(g)**, reached through the provider's Article 16(a) responsibility to meet Section 2 requirements. Representativeness and suitability under Article 10(3)–(4), technical documentation under Article 11 and information for deployers under Article 13 are also relevant.

A two-page feature sheet and a claim that protected inputs are excluded do not demonstrate that training/testing data were examined for bias or that unequal effects were addressed. The evidence establishes a **governance and assurance gap**, not proof of an already-enforceable Article 10 breach: applicability dates and the legacy-system rule must also be considered. [AI Act, Articles 10–16](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

### Is using protected attributes for a bias audit better or worse?

It can put Saltbush in a better assurance position because meaningful subgroup testing needs dependable group information. The audit should use justified, accurate labels, keep them separate from operational scoring, minimise access and retention, and test intersectional effects where sample sizes permit. Guessing gender from names can hide or introduce measurement error.

The amended **Article 4a** provides a tightly conditioned route for providers and deployers to process special-category data for bias detection/correction; it is not unrestricted permission. Necessity and safeguards still matter, including whether less intrusive data would suffice. Gender and age are not automatically GDPR special-category data, although they remain personal data. The former Article 10(5) has been replaced by this broader framework. [2026 amendment, Article 1(6) and amendments to Article 10](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32026R1744)

---

# Task 2 – Respond to the vendor's email

| Vendor claim | Assessment | Reason and relevant provision |
|---|---|---|
| 1. Australia and Sydney hosting mean the EU Act does not apply. | **Disagree.** | The output is used to recruit in Dublin. Article 2(1)(c) establishes the relevant EU connection. |
| 2. Shortlisting is a narrow procedural task exempt under Article 6(3). | **Disagree on these facts.** | Ranking applicants materially influences selection. It is not just administrative formatting. Annex III point 4(a) applies, and Annex III systems that profile natural persons remain high risk. A provider invoking the exception must document its assessment under Article 6(4) and meet the associated Article 49(2) registration requirement. An unsupported assertion is insufficient. |
| 3. No protected inputs means no fairness problem. | **Disagree.** | Proxies and unequal outputs still matter. Article 10(2)(f)–(g) concerns examining and addressing bias, rather than merely omitting particular columns. The Week 4 disparity requires investigation. |
| 4. High-risk obligations wait until 2027, so nothing needs doing now. | **Partly correct about deferred high-risk duties; disagree with “no action”.** | The current Annex III date is 2 December 2027. AI literacy already applies, existing Article 5 prohibitions already apply, and the legacy-system rule needs checking. Existing data-protection and equality responsibilities are not switched off by the AI Act timetable. |
| 5. The enthusiasm add-on is high risk and acceptable with documentation. | **Disagree, assuming it infers emotions from biometric face/voice information.** | Workplace emotion inference is prohibited by Article 5(1)(f), subject to the medical/safety exception. Recruitment enthusiasm/confidence scoring does not fit that exception. Documentation cannot make a prohibited use lawful. If the system only assesses answer content against a skills rubric, rather than inferring emotion from biometrics, its actual function needs reassessment. |

Sources: [AI Act, Articles 2, 5, 6, 10 and 49](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng); [2026 amendment](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32026R1744).

## Who checks the checker?

| Date shown by the checker | Recorded value |
|---|---|
| Latest changelog entry | **3 July 2025** |
| Date of official text the tool says it reflects | **13 June 2024** |

The tool is supplied by the Future of Life Institute, an independent organisation, rather than an EU institution. Calling it “official compliance tooling” overstates its authority. Its dates also precede the 2026 amendment. [Checker and its explanatory material](https://artificialintelligenceact.eu/assessment/eu-ai-act-compliance-checker/)

### 1. How many listed obligations apply today?

On **8 September 2026**, **0 of the 10 main high-risk deployer bullets** have begun applying through the Annex III timetable. **1 separately listed topic—AI literacy under Article 4—already applies.** The checker uses the older literacy wording; the amendment requires measures supporting the development of literacy.

The current timetable is:

| Date | Relevant stage |
|---|---|
| 2 February 2025 | Chapters I and II, including literacy and the original prohibitions |
| 2 August 2025 | General-purpose AI model obligations begin, subject to transition provisions |
| 2 August 2026 | Article 50 transparency duties generally begin |
| 2 December 2026 | Article 50(2) transition ends for qualifying existing systems; new prohibited practices begin |
| 2 December 2027 | Annex III high-risk requirements and obligations |
| 2 August 2028 | High-risk AI in the relevant regulated-product route |

The classifier has run for eighteen months. **Article 111(2)** is therefore material: the high-risk duties for qualifying pre-existing systems hinge on significant design changes after the relevant application date. It would be wrong to say every unchanged legacy classifier automatically becomes subject to every high-risk duty on 2 December 2027. Its deployment history needs checking. [Commission timetable](https://ai-act-service-desk.ec.europa.eu/en/ai-act/faq/when-does-enforcement-start); [amended Articles 111 and 113](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32026R1744)

### 2. Which system is the more urgent legal problem?

The enthusiasm add-on requires the immediate **do-not-deploy decision**, because its prohibited use would be unlawful now. It is only proposed, so there is no evidence that Saltbush is already committing that use violation. The running classifier creates the current operational fairness issue and should be investigated now, while the specific Annex III duties are deferred. These are different kinds of urgency.

### 3. What prohibition arrives in December 2026?

The amendment adds prohibitions concerning **AI-generated/manipulated non-consensual intimate material and child sexual abuse material**, including relevant provider and deployer practices. The intimate-material provisions concern specified realistic depictions of identifiable people without the required consent; this is not a blanket ban on generated images. See amended Article 5(1)(ba)–(bb), with its accompanying conditions and exceptions. [2026 amendment](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32026R1744)

### 4. What is the checker good for?

It is useful for initial classification and an obligation inventory, but I would never use its output alone to certify current legal compliance or decide that no action is required.

---

# Task 3 – Change the use, reassess the tier

| Scenario | Actual checker result / analysis | Why it changes, or does not change | Evidence |
|---|---|---|---|
| Sort ordinary supplier invoices by urgency | **Minimal risk** in this scenario; the result retained **AI Literacy obligations** | The employment use in Annex III point 4(a) is removed. No other high-risk, prohibited or Article 50 use was established. Minimal risk does not mean absolutely no AI Act duties. | [Invoice run](evidence/checker-invoices.jpg) |
| Score interview enthusiasm/confidence from biometric video cues | **Prohibited** | Article 5(1)(f) takes priority over an otherwise high-risk hiring classification. The checker gave its Article 5 prohibited-system warning. | [Enthusiasm run](evidence/checker-enthusiasm.jpg) |
| Add a conversational explanation front-end for rejected candidates | **Hiring remains high risk, with additional transparency duties** | Article 50(1) concerns systems intended to interact directly with people; Article 50(5) concerns clear, accessible disclosure by the first interaction. | Reasoned application of Article 50; no third checker run is claimed |

For the conversational front-end, candidates should be told that they are interacting with AI unless this is already obvious in the statutory sense. Disclosure should appear at the start, alongside a practical route to human review. Answers should reflect actual selection reasons rather than plausible reasons invented by a language model.

**Role matters:** Article 50(1) directly addresses the provider. If Saltbush builds and releases the front-end under its own name, provider duties may attach to it. If the vendor supplies it, Saltbush should ensure the supplied disclosure is correctly implemented and maintained in use. Any generated-text marking duty under Article 50(2) is a separate provider consideration. A private candidate explanation is not automatically public-interest publication under Article 50(4). [AI Act, Articles 3 and 50](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

---

# Task 4 – Test the Byzantine icon's provenance

## Initial inspection and baseline

The image shows a haloed figure in traditional icon styling holding an **electric guitar**. That visible anachronism undermines the listing's eleventh-century claim. The unrecorded provenance, single photograph and recently created seller account are reasons to request evidence; they do not independently prove how the image was produced.

The lab supplied [`byzantine_icon.jpg`](https://moodle.federation.edu.au/pluginfile.php/10610290/mod_lesson/page_contents/553491/byzantine_icon.jpg), a **992 × 1075** JPEG. Its SHA-256 is:

```text
d28322208d7dde75728b9ef868a389c2bf2534dbf9cc9c7efe0c8e50db3a5ad5
```

The [Content Credentials verifier](https://verify.contentauthenticity.org/) identified AI generation and displayed **Google LLC**, with **Google Media Processing Services** as the issuer. It showed creation/editing provenance and an issuance time of **24 August 2026, 10:57 PM GMT+10**. [Original verifier screenshot](evidence/credentials-original.jpg)

Gemini's original response reported a valid watermark and Google creation record, but its explanation mixed SynthID with Content Credentials. Follow-up prompts explicitly requested a detector result separate from metadata and visual judgement. Results below are **Gemini-reported**: the experiment did not have independent access to its detector logs or confidence scores. The [baseline response](evidence/gemini-original.txt) and [complete lab-only transcript](evidence/gemini-lab-transcript.txt) preserve the evidence.

Content Credentials carry signed provenance assertions associated with a file. SynthID encodes a signal in the media itself. Their evidential value differs: a provenance record can identify an asserted creation history, while a provider-specific watermark can support a narrower origin claim. Neither authenticates the physical object in a seller's possession. [Google's verification guidance](https://support.google.com/gemini/answer/16722517?hl=en); [Google DeepMind SynthID](https://deepmind.google/models/synthid/)

## Predictions and controlled transformations

Predictions were written before creating the test copies. Each transformation starts from the original rather than accumulating earlier edits. The screenshot trial captured the image displayed at 260 pixels wide on Moodle; the image-only area was cropped and saved as JPEG. The other trials used deterministic macOS image conversion, without generating a replacement image. [Prediction log](evidence/watermark-predictions.md)

| Attempt | Prediction recorded before testing | Content Credentials observation | SynthID observation | Could the image still serve as an auction photograph? |
|---|---|---|---|---|
| Original, 992 × 1075 | Baseline should retain provenance and watermark | Verifier displayed Google-issued AI-generation credentials | Gemini reported a valid watermark, but mixed metadata and watermark reasoning | Visually detailed; the guitar still contradicts the claimed age |
| [Screenshot, crop and JPEG re-save, 260 × 282](evidence/icon-screenshot-260.jpg) | Credentials should not transfer; pixel watermark might survive resizing | Verifier reset without an explicit result; original embedded provenance segments absent in local header inspection; Gemini reported no valid C2PA manifest | **Positive**, according to Gemini's stated automated verification result | Recognisable as a small thumbnail; insufficient detail for evaluating an expensive antique |
| [JPEG re-save at quality 20, 992 × 1075](evidence/icon-jpeg-q20.jpg) | Export may discard credentials; watermark may survive compression | Same verifier reset; local provenance segments absent; Gemini reported no valid C2PA manifest | **Positive**, according to Gemini's stated automated verification result | Retains detail and composition sufficiently for a listing image, although text and borders show compression; authenticity remains unproven |
| [Resize to 124 × 134, then enlarge to 992 × 1075, JPEG quality 80](evidence/icon-down-up.jpg) | Severe resampling may prevent detection, with visible blur | Upload succeeded after a file-picker retry; verifier reset; local provenance segments absent; Gemini reported no valid C2PA manifest | **Positive**, according to Gemini; the prediction that severe resampling might stop detection was not supported | Recognisable composition, but obvious pixelation and lost fine detail make it unsuitable for a credible inspection photograph |
| [Rotate original 7 degrees and export at JPEG quality 35](evidence/icon-rotate-7.jpg) | Geometric misalignment might disrupt detection while preserving most detail; export may discard credentials | Verifier reset; local provenance segments absent; Gemini reported no valid C2PA manifest | **Unavailable:** Gemini reported **Quota Exceeded** and explicitly said no watermark assessment was performed | Most detail remains; tilted framing and black corner padding reduce presentation quality |

The prediction log also contains proposed screenshot sizes that were not run. They are **plans, not additional experimental results**. File-picker retries are technical failures, not negative detections. The original plus four transformed-image prompts were submitted; the last reported a quota limit, which ended further SynthID testing.

**Credential evidence limitation:** the verifier's return to its start screen was not an explicit negative result. Local JPEG-header inspection found **3 APP11 segments in the original and 0 in each derivative**, supporting loss of its embedded provenance. This header check does not validate signatures, search for remote credentials, or detect SynthID. Gemini separately reported absent C2PA manifests. The [file manifest](evidence/file-manifest.json) identifies the exact images and records the header findings. The verifier states are saved for the [screenshot](evidence/credentials-screenshot-260.jpg), [JPEG](evidence/credentials-jpeg-q20.jpg), [resize](evidence/credentials-down-up.jpg) and [rotation](evidence/credentials-rotate-7.jpg) attempts.

### Reproducing the deterministic edits

Download the supplied original into the current directory. These macOS `sips` commands reproduce the export, resize and rotation methods; software versions can affect exact encoded bytes, so the supplied file hashes identify the actual tested copies.

```sh
sips -s format jpeg -s formatOptions 20 byzantine_icon.jpg --out icon-jpeg-q20.jpg
sips --resampleHeightWidth 134 124 byzantine_icon.jpg --out icon-small.jpg
sips --resampleHeightWidth 1075 992 -s format jpeg -s formatOptions 80 icon-small.jpg --out icon-down-up.jpg
sips --rotate 7 -s format jpeg -s formatOptions 35 byzantine_icon.jpg --out icon-rotate-7.jpg
```

For the screenshot trial, display the original at 260 pixels wide, take a browser screenshot and crop to its 260 × 282 image area. This trial combines display resampling, screenshot capture and JPEG re-saving; it does not isolate those effects individually.

## Findings and reflection

### 1. Which detector was easier to defeat?

**The original embedded credentials were easier to remove.** Even the screenshot/export lost their JPEG provenance segments, while Gemini reported SynthID present in all three completed transformed-image checks. The comparison is limited by the verifier's inconclusive UI behaviour and the lack of independently accessible SynthID detector logs; it is not a general benchmark of either technology.

### 2. How much degradation stopped the watermark, and is it valuable?

A stopping threshold was **not reached**. Gemini still reported a watermark after reduction to 124 × 134 and enlargement to 992 × 1075—approximately **1.56% of the original pixel count** at the intermediate stage. This visibly damaged the image without achieving a reported negative. The rotation trial cannot establish anything about survival because its detector check was unavailable.

The low-quality JPEG remains visually usable as a listing photograph, but the heavily enlarged version is inadequate for examining a claimed AU$4,200 antique. Both retained a reported watermark result. Thus the experiment did **not** achieve the lab's challenge of removing both signals while maintaining a convincing photograph.

A positive provenance/watermark result remains valuable evidence against this particular listing. A negative result would not establish that the photograph is authentic: an image may come from another generator, lose its metadata, or be altered beyond a detector's reliable range. An auction buyer still needs provenance records, additional photographs and an appropriate examination of the physical object.

### 3. What can be done with an image from an unknown generator?

Start with embedded Content Credentials and identify any named issuer. Use an originating provider's supported detector where available, compare earlier versions through source/reverse-image research, and request the original file and creation history. Generic AI-image classifiers can supply uncertain clues, but there is no single universal watermark detector that proves every unmarked image is genuine. Google's own verification guidance explains the limits of its supported checks. [Gemini verification guidance](https://support.google.com/gemini/answer/16722517?hl=en)

### 4. Does Article 50 apply when the seller removes the mark?

Article 50(2) places the machine-readable marking responsibility on the **provider of the generating system**. Destroying a mark later does not automatically make the seller that provider or establish a breach of that exact paragraph.

A commercial seller who uses an AI system to generate or manipulate a deceptive image may be a **deployer**, making the Article 50(4) deepfake disclosure rule relevant where its definition and scope are met. Whether this synthetic depiction of an object meets every element needs analysis; merely exporting a JPEG with a conventional editor does not itself make someone an AI deployer. The Cyprus seller has a clear EU connection, and the commercial sale is not simply personal non-professional use.

My assessment is that the actor, the AI use and the applicable duty must be identified separately. The provider's marking duty and a seller's disclosure duty address different conduct. The deceptive listing can also raise consumer-law issues, which this experiment does not determine. [AI Act, Articles 2, 3(60) and 50](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

## Optional smaller challenge – Transparency Code of Practice

Google, identified in the original file's provenance, announced signing the **Code of Practice on transparency of AI-generated content on 24 July 2026**. The Commission's subsequent list includes Google among Section 1 signatories. This is the transparency code associated with Article 50, distinct from the earlier general-purpose AI code. Signing supports a commitment to marking; it does not demonstrate that every watermark is indestructible or independently certify this individual file. [Google announcement](https://blog.google/company-news/outreach-and-initiatives/public-policy/eu-ai-act-transparency-code-of-practice/); [Commission signatory announcement](https://digital-strategy.ec.europa.eu/en/news/strong-backing-code-practice-transparency-ai-generated-content)

The optional Colab text-watermarking challenge was not performed.

---

# Connecting the lab to the governance portfolio

| Week 5 governance area | Practical application from Week 6 |
|---|---|
| Clause 4 – Context | Update the system scope for Dublin recruitment and the EU legal connection |
| Clause 5 – Leadership | Name the accountable owner and reject the prohibited emotion-scoring proposal |
| Clause 6 – Planning | Record proxy risks, affected groups and the legal applicability assessment |
| Clause 7 – Support | Develop staff AI literacy and provide effective oversight training |
| Clause 8 – Operation | Obtain vendor information, establish oversight, and prepare appropriate logging and escalation |
| Clause 9 – Performance evaluation | Reassess subgroup outcomes and monitor changes after deployment |
| Clause 10 – Improvement | Investigate the Week 4 disparity, document corrective action and verify whether it works |

This is a conceptual connection to the [Week 5 portfolio](../Week%205/README.md), not a claim of ISO certification or an exact reproduction of every ISO requirement.

The main learning is that **classification, legal timing and evidence are separate questions**. A high-risk label does not reveal which duties apply today. A fairness assurance needs output and data evidence, not just an input-column list. A detector's confident prose is not a substitute for an identifiable test result.

## Sources and evidence notes

- [Federation University Topic 6 lab](https://moodle.federation.edu.au/mod/lesson/view.php?id=9098743) supplies the fictional Saltbush and auction scenarios; institutional login is required.
- [Regulation (EU) 2024/1689](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng) is read together with [Regulation (EU) 2026/1744](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32026R1744).
- The linked screenshots preserve live tool results. Counts and legal conclusions are explained in the text so the portfolio remains readable without opening very tall captures.
- Image transformations are supplied as clearly identified lab derivatives. They are not presented as photographs of a genuine antique.
- **AI assistance:** Codex assisted with browsing, checker interaction, deterministic image transformations, source checking and drafting. Gemini was used for the recorded verification prompts. Personal attendance, tutor approval and unobserved detector outcomes have not been invented.
