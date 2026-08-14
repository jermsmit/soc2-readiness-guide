# 12. Choosing an Auditor and Preparing for Fieldwork

By the time you are ready to select an auditor, most of the hard work described in this guide is already underway or complete: your control matrix exists, your policies are written and approved, your evidence is being collected continuously. This section covers the part of the process that is easy to underestimate because it feels administrative, choosing the right firm and running fieldwork smoothly, but which has a real effect on both your timeline and how much disruption the audit causes your team.

## What to evaluate when selecting a CPA firm

SOC 2 reports must be issued by a licensed CPA firm, but licensure is table stakes, not a differentiator. Within the pool of firms qualified to issue the report, the differences that actually matter are experience, communication style, and how the engagement will actually run in practice.

**Life sciences and SaaS experience.** A firm with genuine experience auditing life sciences companies, not just SaaS companies broadly, understands why your system boundary might reference GxP validation, why certain evidence comes from a quality system rather than a typical IT ticketing tool, and will ask better, more relevant questions during fieldwork rather than treating every unfamiliar process as a red flag that needs extensive explanation. Ask directly during the selection process how many life sciences clients the firm has worked with, and ask for a reference from one if possible.

**Report turnaround history.** Ask prospective firms how long, in practice, from the end of fieldwork to a delivered final report, their engagements typically take. This varies more between firms than people expect, and a firm with a track record of fast, predictable turnaround is worth real weight in the decision, particularly if your report needs to land by a specific date tied to a customer deal or contract renewal.

**Responsiveness during the engagement.** A firm's responsiveness during the sales process is a reasonable, if imperfect, predictor of responsiveness once you are a signed client. Firms that are slow to schedule an initial call or vague about their process before you have signed anything are not likely to become dramatically more responsive afterward.

**Fee structure and scope clarity.** Understand what is included in the quoted fee, and what would trigger additional cost, an expanded system boundary discovered mid-engagement, additional criteria added after scoping, a longer observation window than originally planned. Get this in writing before signing, since scope creep on either side, yours or the auditor's, is a common source of friction and unexpected cost.

## Questions worth asking during auditor selection

A short, direct set of questions during the selection process reveals more about how an engagement will actually run than a firm's marketing materials will.

- How many life sciences clients have you audited for SOC 2, and can I speak with one as a reference?
- What does your fieldwork process actually look like, week by week, from kickoff to report delivery?
- How do you typically request evidence, through a shared portal, email, a GRC platform integration, and how much lead time do you give before an evidence request is due?
- What is your average time from the end of fieldwork to final report delivery, and has that estimate held in recent engagements?
- If we discover a control gap or exception during fieldwork, what does that process look like, and how does it affect the timeline?
- Who will actually be doing the fieldwork, and is that the same team involved in the sales process, or does the engagement get handed off to different staff once signed?

That last question matters more than it might seem. Some firms involve senior, experienced staff throughout the sales process and then hand fieldwork execution to more junior staff who were not part of the initial conversations. This is not automatically a problem, but it is worth knowing in advance so you know who to expect showing up for interviews and evidence review.

## Preparing teams for interviews

Auditor interviews are where the evidence you have collected meets the people who can explain it, and inconsistency between what an interviewee says and what the submitted evidence shows is one of the more common sources of unnecessary friction during fieldwork.

Before fieldwork begins, brief everyone who will be interviewed on what they are likely to be asked about, based on the control areas relevant to their role, and make sure they have reviewed the evidence already submitted for those controls so their answers align with what the auditor has already seen in writing. This is not about coaching people to give rehearsed answers, it is about making sure an engineer describing the change management process in an interview is describing the same process the submitted pull request evidence actually demonstrates, rather than describing an idealized version from memory that does not quite match what the evidence shows.

A useful practice: hold a brief internal readiness session before fieldwork starts, where whoever owns the SOC 2 program walks through the control matrix with each team that will be interviewed, confirming everyone understands what evidence exists, where it lives, and what the actual current practice is, not what the policy document says the practice should be. If there is a gap between the two, better to surface it internally before the interview than to have it surface for the first time when an auditor notices the inconsistency.

## What fieldwork actually looks like

Fieldwork for a Type II audit typically runs over several weeks, though the exact length depends on your system boundary and the firm's process. A general shape most engagements follow:

**Kickoff.** The auditor reviews your system description and control matrix, confirms the scope and criteria being tested, and provides an initial evidence request list covering the full observation window.

**Evidence review.** The bulk of fieldwork happens here, with the auditor working through submitted evidence for each control, sampling specific instances, a subset of terminated employees to check deprovisioning timing, a subset of changes to check review and approval, a subset of vendor reviews to check completeness, and following up with clarifying questions or requests for additional evidence where something is unclear or incomplete.

**Interviews.** Scheduled conversations with relevant team members to confirm understanding of processes and controls that evidence alone does not fully explain. These are typically shorter and less adversarial than people expect going in, particularly when the interviewee has been briefed and the evidence is solid.

**Findings and exceptions discussion.** If the auditor identifies a gap or an instance where a control did not operate as designed, this gets discussed before the report is finalized, giving you the opportunity to understand exactly what was found and, in some cases, provide additional context or evidence that clarifies the situation.

**Report drafting and review.** The auditor drafts the report, and you typically get an opportunity to review it for factual accuracy, the system description accurately reflects your actual environment, before it is finalized, though you cannot influence the auditor's actual opinion or findings.

Keeping fieldwork from disrupting engineering delivery mostly comes down to preparation done before fieldwork starts. If evidence is already organized per Section 10's guidance, most fieldwork becomes the auditor working through an evidence repository with occasional clarifying questions, rather than your team scrambling to produce evidence on demand throughout the engagement. Interviews, scheduled in advance with reasonable notice, are a much smaller time commitment than most engineers expect, particularly once the first one or two have happened and the format becomes familiar.

## Handling findings and exceptions without panic

Finding a gap during fieldwork is common and does not automatically mean your report will carry a qualified opinion. What happens next depends on the nature and severity of what was found.

For a Type I report, a design gap identified before the report is finalized can often simply be fixed, with the control redesigned and evidenced properly before the report is issued, since Type I evaluates design at a point in time and you have some latitude to correct course before that point is locked in.

For a Type II report, an exception identified during the observation window generally gets disclosed in the final report as an exception, since the report is testifying to what actually happened over the period, not what could be fixed before delivery. This is not necessarily catastrophic. A single documented exception, with clear evidence that it was identified, understood, and remediated promptly, is viewed very differently by a sophisticated customer's security team than a pattern of unaddressed or recurring exceptions across multiple controls. Most experienced enterprise security reviewers understand that a spotless first Type II report with zero exceptions across a full observation period is somewhat unusual, and a single well-handled exception with clear remediation is not a disqualifying signal.

What matters most when a finding surfaces is how it is handled from that point forward: understand exactly what happened and why, fix the underlying process so it does not recur, and be prepared to explain the finding clearly and honestly to any customer or prospect who asks about it, rather than treating it as something to obscure. A defensive or evasive response to a reasonable question about a disclosed exception damages trust far more than the exception itself typically does.

## Common mistakes this section addresses

**Choosing an auditor primarily on price without evaluating life sciences experience or fieldwork process.** The cheapest quote is not a bargain if it comes from a firm unfamiliar with life sciences environments, since unfamiliarity translates into more clarifying questions, more back and forth, and a longer, more disruptive fieldwork process than working with a firm that already understands the context.

**Sending team members into interviews unprepared and unaware of what evidence has already been submitted.** Inconsistency between interview answers and submitted evidence creates unnecessary friction and follow-up work, even when the underlying control is actually operating correctly. A brief internal readiness session before fieldwork begins closes this gap at very low cost.

---

*Next: [Section 13, Staying Compliant After the Report](13-continuous-compliance.md)*
