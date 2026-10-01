# Week 7 – Human Factors in AI Systems

## Overview

This week focused on the human factors that affect AI governance, including trust, over-reliance, expertise, transparency, human oversight and accountability.

The opening checkpoint described a healthcare setting where staff gradually stop checking an AI decision-support tool and begin agreeing with its recommendations. This demonstrated automation bias, where people become more likely to accept an automated recommendation without independently assessing whether it is correct. It is not simply a technical failure. It occurs when the way people use a system reduces their willingness or ability to independently assess its output.

I then completed *Survival of the Best Fit*, a browser game about training and deploying an automated hiring system. The game demonstrated how apparently reasonable individual decisions can become training labels, how historical data can reproduce unequal opportunities, and how automation can amplify those patterns faster than a human can review them.



## Task 1 – Survival of the Best Fit

### What Happened in My Game

The game began with manual hiring. I could inspect each candidate's skill, school prestige, work experience and ambition before accepting or rejecting them.

In the first round, I selected Ellen Copeland, Todd Howe and Corey Chang. The game reported that the people I hired had 7% more school prestige than the average applicant. During the final debrief, I identified education as the attribute I had valued most.

The process then changed quickly.

| Stage | What happened | Human-factors problem |
|---|---|---|
| Manual selection | I reviewed individual profiles and chose three candidates. | My preferences became labels describing what a "good" candidate looked like. |
| Time pressure | The investor required five hires and then eight hires within 45-second rounds. | Speed reduced the time available for careful comparison and encouraged shortcuts. |
| Model training | The engineer used my earlier decisions and asked me to add a large external dataset. I selected Google's historical applicant data. | Neither dataset was reviewed for representativeness, historical exclusion or proxy variables before training. |
| Automated hiring | The system began accepting and rejecting applicants at a speed that I could not manually reproduce. | The hiring manager remained present but was no longer making, checking or explaining each decision. |
| Complaint investigation | A rejected applicant, Elvan Yang, had very strong qualifications. The data inspector also showed that accepted candidates were mostly orange while rejected candidates were mostly blue. | The problem became visible only after an affected person complained. |
| Group-level review | The orange and blue groups had similar average performance, but the model rejected many more blue candidates. | Overall activity and speed concealed a discriminatory outcome between groups. |
| Final outcome | The bias became public, the company was sued for hiring discrimination and investors withdrew. | Governance was reactive. Investigation occurred after harm and reputational damage rather than before deployment. |

### Decision Points That Felt Uncomfortable

The first uncomfortable point was the pressure to hire faster.

The candidate profiles contained several attributes, but the timed rounds made it difficult to examine them consistently. The investor treated speed and lower cost as evidence of success. This created an incentive to finish the task rather than question whether the decisions were reliable or fair.

The second uncomfortable point was supplying historical CVs and selecting a large technology company's dataset without checking it.

More data was treated as automatically better data. However, a large dataset can give a model more examples of historical inequality. In the game, orange applicants had historically received more opportunities in technology. The dataset therefore did not represent a neutral standard of merit.

The third uncomfortable point was the shift from decision support to automatic decision-making.

The engineer said that my job had been automated and that I could "enjoy the ride." At that point, the system continued to process candidates while I watched accepted and rejected totals increase. I was still nominally involved, but I was no longer exercising meaningful oversight.

The fourth uncomfortable point was the rejection of Elvan Yang.

Elvan's profile showed high skill, school prestige, work experience and ambition. There was no convincing performance-based explanation for the rejection. The group pattern suggested that being blue, or a proxy correlated with being blue, influenced the result.

### How Bias Entered the System

The game showed several connected sources of bias rather than one deliberately discriminatory rule.

1. My manual decisions created the initial labels.
2. Time pressure made those decisions less careful and more dependent on simple cues.
3. The external dataset reflected a history in which orange people had greater access to technology employment.
4. The model could infer group membership through proxies such as the university a person attended, even when colour was not an explicit field.
5. Automation repeated the learned pattern across a much larger number of applicants.
6. The organisation monitored speed and cost before it examined group outcomes.

I did not notice the full pattern while making the first decisions. In the moment, school prestige looked like a job-related characteristic rather than a possible proxy for unequal opportunity. The bias became much clearer in hindsight when the data inspector placed accepted and rejected candidates side by side.

This was an important distinction. A person does not need to intend discrimination for their decisions to contribute to a discriminatory system.

### Where Human Oversight Broke Down

Meaningful oversight broke down when the algorithm moved from learning from my decisions to making decisions at scale.

Before automation, I could inspect a candidate and give a reason for my choice. After automation, I could see that a decision had occurred, but I could not explain why that candidate had been accepted or rejected.

The hiring manager therefore became a passive observer. The presence of a human did not provide an effective safeguard because the human lacked:

- time to review every decision;
- a clear explanation of the model's reasoning;
- subgroup monitoring;
- an escalation threshold;
- authority to pause the system; and
- a defined responsibility to challenge its output.

The manager's inability to explain Elvan's rejection also reduced the ability to detect mistakes. The problem was found through a complaint and a later group-level analysis, not through routine oversight.

## Task 2 – Bias Review

### Where the Same Dynamic Appears in Real Systems

The same pattern can appear whenever an organisation uses historical decisions to automate future decisions.

| Context | Historical label or proxy | How the problem can scale |
|---|---|---|
| Hiring | Past interview or hiring decisions; school, postcode, employment gaps or previous job titles | A model can reproduce previous workforce patterns across thousands of applicants before anyone reviews subgroup outcomes. |
| Lending | Past approvals, defaults and human risk assessments; postcode or employment history | Communities that previously had less access to credit can continue to receive fewer opportunities, making the historical pattern self-reinforcing. |
| Admissions | Past admission decisions, school attended, subject availability or extracurricular activities | The system can treat unequal access to educational opportunities as if it were a neutral measure of potential. |

In each case, scale changes the governance problem.

A human decision can be biased and harmful, but an automated system can apply the same pattern consistently, quickly and invisibly. The organisation may also trust the process more because the result came from a computer.

### When I Could No Longer Explain the Decisions

I stopped being able to explain individual outcomes once the automated hiring process began.

The system showed candidate profiles moving through accepted and rejected channels, but it did not provide a case-level reason that I could evaluate. This meant I could not determine whether the model had relied on skill, education, a proxy for colour, or some combination of factors.

That loss of explanation damaged oversight in two ways.

First, it made it difficult to challenge an individual error. Elvan appeared highly qualified, but I could not reconstruct the reason for the rejection.

Second, it delayed recognition of the broader pattern. I needed a complaint and a separate group-level breakdown before I could see that blue applicants were being rejected more often even though the average performance of the two groups was similar.

The game therefore showed that transparency is not only about publishing a general description of a model. The people responsible for decisions need information that helps them question a particular result and monitor the pattern created by many results.

## Task 3 – Governance Brainstorm

### Governance Mechanism Borrowed from Healthcare

I would introduce an **independent multidisciplinary peer-review board with authority to pause the hiring system**.

The board would include recruitment expertise, data or model expertise, legal and governance knowledge, and a representative able to consider the experience of applicants. It would review the system before deployment and at defined intervals after deployment.

Before deployment, the board would require evidence covering:

- the source and limitations of the training data;
- subgroup performance and selection outcomes;
- proxy variables that may reveal protected characteristics;
- the purpose and limits of the system;
- the role of the human decision-maker; and
- the conditions that require suspension or revalidation.

After deployment, the board would review a sample of accepted and rejected cases together with group-level outcomes and complaints. It would have authority to pause the system when a fairness threshold is exceeded, when a qualified applicant cannot be given a defensible reason, or when the available evidence is insufficient.

This mechanism would have caught the game's main failure before it reached scale. A pre-deployment review should have identified that the historical dataset contained unequal orange and blue representation. Post-deployment peer review should then have detected that accepted candidates were mostly orange and rejected candidates were mostly blue despite similar average performance.

The healthcare connection is useful because high-impact tools should support professional judgement rather than replace it. The World Health Organization's guidance also emphasises autonomy, transparency, responsibility, accountability, inclusiveness and continuous assessment when AI is used in health.

### Accountability Structure

Accountability should be shared but not vague. Each person should be responsible for the decisions they are able to control.

| Stage | Accountable role | Required sign-off | What the sign-off means |
|---|---|---|---|
| Purpose and deployment decision | Founder or organisational system owner | Approves the defined use, affected groups, risk tolerance and resources for oversight. | The organisation accepts responsibility for using the system and cannot transfer that responsibility to the algorithm. |
| Design and validation | Engineer or model lead | Signs the data record, test results, subgroup analysis, known limitations and monitoring requirements. | The engineer confirms what was tested and clearly identifies what remains uncertain. |
| Operational decision | Hiring manager | Records an independent assessment, reviews the recommendation and gives a reason for following or overriding it. | The manager remains responsible for exercising judgement rather than rubber-stamping the output. |
| Independent assurance | Peer-review board or AI governance lead | Authorises initial use, reviews monitoring and can suspend operation. | A role outside the immediate delivery pressure decides whether the evidence is sufficient for continued use. |
| Incident and complaint response | System owner with governance lead | Records the investigation, corrective action and communication to the affected applicant. | Complaints become governance evidence rather than isolated customer-service issues. |

The founder should hold ultimate accountability for deployment because the founder chose to use the system and set the pressure for speed and cost reduction.

The engineer should be accountable for technical validation, documentation and disclosure of limitations. However, the engineer should not be expected to make employment-policy decisions alone.

The hiring manager should be accountable for meaningful review of individual decisions, but only if the workflow gives that person enough time, information, competence and authority to challenge the system.

This structure would have changed the outcome because no single person could treat the next step as somebody else's problem.

### Workflow Change for Appropriate Trust

I would change the interface to require an **independent-first decision before the AI recommendation is revealed**.

The workflow would be:

1. The hiring manager reviews the job-related evidence and records an initial shortlist decision with a brief reason.
2. The interface then reveals the AI recommendation and the main factors supporting it.
3. If the two decisions disagree, the case is automatically sent to a second reviewer before a final outcome is recorded.
4. The system logs agreements, disagreements, overrides and reasons so they can be reviewed for repeated patterns.

This does not change the underlying algorithm. It changes the way the human and the algorithm interact.

The design reduces the risk that the AI recommendation anchors the manager's first judgement. It also avoids the opposite problem of ignoring the system completely, because the recommendation is still considered after an independent view has been recorded.

The second-review trigger creates useful friction at the point where human and machine disagree. It also produces evidence about whether the model is helping, whether managers are automatically agreeing with it, or whether particular groups experience more disputed decisions.

Research on automation bias supports this direction. A systematic review found that workload, task complexity and time pressure can increase the risk of over-reliance, while user accountability and the way advice is presented can help mitigate it.

---

## Week 7 Reflection

This week showed me why putting a human in the loop is not enough by itself.

The hiring manager remained visible throughout the game, but the quality of the oversight changed. At first, the manager made decisions. Later, the manager watched the model make decisions. When the system began operating at scale, the manager could not explain individual outcomes and did not have a defined trigger for intervention.

The game also demonstrated why bias is a socio-technical problem.

The engineer did not deliberately write a rule saying that blue candidates should be rejected. Instead, the outcome emerged from human labels, time pressure, historical inequality, an unexamined external dataset, proxy variables and a business objective that rewarded speed and lower cost.

This connects directly with the governance work from Week 5.

ISO/IEC 42001 provides a structure for roles, impact assessment, operational controls, monitoring and corrective action. Week 7 showed why those controls matter in practice. Without meaningful human oversight and group-level monitoring, an organisation can have a person supervising an AI system while still failing to notice that the system is harming a group.

My main takeaway is that appropriate trust must be designed.

People should not be expected to rely on an AI system simply because it is fast, and they should not reject it simply because it can make mistakes. They need evidence about when it works, information that helps them question individual outputs, time to exercise judgement, and a clear escalation path when the evidence does not support continued use.

The strongest safeguard is therefore not a single fairness metric or a human approval box. It is a governance process that connects individual review, group-level monitoring, independent assurance, complaints, accountability and the authority to stop the system.

---

## References

Federation University Australia. (2026). *ITECH 2119 Week 7: Human factors in AI systems – Learning activity*. Moodle. https://moodle.federation.edu.au/mod/lesson/view.php?id=9104017

Goddard, K., Roudsari, A., & Wyatt, J. C. (2012). Automation bias: A systematic review of frequency, effect mediators, and mitigators. *Journal of the American Medical Informatics Association, 19*(1), 121–127. https://doi.org/10.1136/amiajnl-2011-000089

Survival of the Best Fit. (2019). *Survival of the Best Fit* [Interactive game]. https://www.survivalofthebestfit.com/game/

Survival of the Best Fit. (2019). *Understanding algorithmic bias*. https://www.survivalofthebestfit.com/resources

World Health Organization. (2021). *Ethics and governance of artificial intelligence for health: WHO guidance*. https://www.who.int/publications/i/item/9789240029200
