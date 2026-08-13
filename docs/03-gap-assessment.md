# 3. Running the Gap Assessment

The gap assessment is where most SOC 2 programs either get a realistic foundation or start accumulating debt they will pay for later. Its purpose is simple to state and hard to execute well: figure out, honestly, where your current practices already meet the Trust Services Criteria, and where they do not, before you commit to a timeline or start writing policies nobody has validated against reality.

Done well, a gap assessment takes two to four weeks and produces a prioritized, owned remediation plan. Done poorly, it becomes a paperwork exercise that produces a stack of policy documents describing practices that do not actually exist yet, which is worse than having no documentation at all, because it creates evidence that will contradict what your team says in an audit interview.

## Structuring the assessment against the Common Criteria

Use the CC1 through CC9 structure from Section 1 as your assessment framework, plus any additional criteria you scoped in (Availability, Confidentiality, and so on). For each control area, you are answering three questions:

1. Does a control currently exist, even if undocumented?
2. If it exists, is it operating consistently, or does it depend on someone remembering to do it?
3. If it does not exist, what needs to be built, and how long will that realistically take?

Resist the urge to jump straight to writing policies. A policy describing a control that is not actually happening is not progress, it is a liability. The assessment phase is about finding the truth first.

## Building a control matrix

The single most useful artifact from this phase is a control matrix: a working document, most companies use a spreadsheet, with one row per control and the following columns.

- **Control ID and description.** A short reference (for example, AC-01) and a plain description of what the control is supposed to achieve.
- **Related Trust Services Criteria.** Which CC or additional criterion this maps to.
- **Owner.** The specific person responsible, not a team or department. If no individual owns it today, that is itself a gap.
- **Current state.** What actually happens today, described honestly. If the honest answer is "nothing," write that.
- **Target state.** What needs to be true for this control to satisfy the criterion.
- **Evidence source.** Where the proof will come from once the control is operating: a ticketing system export, an access review log, a signed policy document, a system configuration screenshot.
- **Gap severity.** How far the current state is from the target state, and how much audit risk the gap represents if unaddressed.
- **Remediation effort.** A rough estimate: days, weeks, or a quarter of work.

This matrix becomes the backbone of your entire program. It is what you hand your auditor when they ask what you have already assessed, it is what drives your remediation timeline, and later it evolves directly into your evidence tracker (see [templates/trackers/evidence-tracker.md](../templates/trackers/evidence-tracker.md)).

## Interviewing the people who actually do the work

The most common failure mode in a gap assessment is running it entirely from the top: a compliance lead or consultant fills out the control matrix based on what policies theoretically say, without talking to the engineers, IT staff, and HR team who actually execute the day-to-day work.

This fails in both directions. Sometimes a control that looks absent on paper is actually already happening informally, an engineering team might already require peer review on every pull request even though no policy says so, which means the gap is a documentation gap, not a practice gap, and is much faster to close. Other times a control that looks fine on paper is not actually happening the way the policy describes, because the policy was copied from a template two years ago and nobody updated it when the process changed.

Plan structured interviews with:

- Engineering leadership, on change management, access to production, and code review practices
- IT or infrastructure leads, on identity management, endpoint security, and network controls
- HR, on onboarding, offboarding, and background check practices
- Whoever owns vendor relationships, on how vendor risk is currently evaluated, if at all
- Quality or Regulatory Affairs, in a life sciences company, on what validation and change control already exists for GxP-relevant systems

Ask what actually happens, not what is supposed to happen. "Walk me through the last time someone left the company, what happened to their access" produces a far more useful answer than "do you have an offboarding process."

## Prioritizing remediation

Once the control matrix is populated, prioritize remediation using two factors together: audit risk and implementation effort. Do not simply work through the list in the order it was written, and do not default to fixing the easiest items first just because they are easiest.

A useful way to think about it:

- **High risk, low effort.** Fix these immediately. These are usually process gaps rather than technical gaps, for example documenting an access review process that already happens informally.
- **High risk, high effort.** These need to start early, since they are the most likely to determine your overall timeline. Access control system overhauls and vendor risk program buildouts often fall here.
- **Low risk, low effort.** Fix these opportunistically, in parallel with the higher-priority work, but do not let them displace attention from higher-risk items.
- **Low risk, high effort.** Deprioritize. If a control gap represents low audit risk and requires significant effort, it is often a candidate for scoping out of year one entirely, addressed in a later cycle instead.

Access control and vendor management deserve specific mention here because they consistently take longer to remediate than companies expect. Access control often requires cross-team coordination across HR, IT, and every system owner to get provisioning and deprovisioning genuinely consistent. Vendor management often requires chasing down SOC 2 reports and security questionnaires from third parties who are in no hurry to respond. Budget more time for both than your initial instinct suggests.

## Setting a remediation timeline that accounts for the observation window

Once you have prioritized your gaps, work backward from your target Type II observation window start date, established in Section 2. Every control needs to be fully remediated and have completed at least one full cycle at its natural cadence, an access review, a vendor review, a change management cycle, before the observation window begins. Starting the window with a control that has never actually run is how companies end up with an exception in month one of their first Type II report.

Build the remediation plan with explicit checkpoints, not just a single end date. A useful cadence is a biweekly review of the control matrix with whoever is driving the program, checking actual progress against the plan and re-prioritizing as gaps turn out to be bigger or smaller than initially estimated.

## Life sciences note: cross-referencing against existing GxP controls

If your company already operates under GxP requirements, computer system validation, or has an established quality management system, do not run your SOC 2 gap assessment in isolation from that work. There is real overlap, and finding it early saves significant duplicated effort.

Before starting interviews, pull your existing SOPs related to system access, change control, incident and deviation management, and vendor qualification. In many cases, a control that looks like a SOC 2 gap on paper is already substantially satisfied by an existing GxP process, and the actual gap is narrower than it first appears: it might just be that the existing process needs to be extended to cover systems outside the validated GxP boundary, or that evidence needs to be captured in a way that also satisfies SOC 2 documentation expectations.

The reverse is also true and worth watching for: a SOC 2 control that appears satisfied by an existing GxP process on paper needs to be checked for whether it actually covers the full SOC 2 system boundary. A change control SOP that only governs validated systems will not, by itself, satisfy CC8 for the parts of your infrastructure that sit outside GxP scope.

Involve Quality and Regulatory Affairs in the gap assessment directly, not as a downstream stakeholder informed after the fact. The goal is one control, one piece of evidence, satisfying both frameworks wherever that is genuinely possible, rather than two teams independently building parallel processes that cover the same ground.

## Common mistakes this section addresses

**Running the gap assessment as a paperwork exercise instead of interviewing the people who actually do the work.** A control matrix built entirely from existing policy documents, without validating against what actually happens day to day, produces a plan that looks complete and is not. The interviews are not optional overhead, they are the part of the process that catches the gap between what is written and what is real.

**Underestimating how long access control and vendor management remediation takes relative to other domains.** These two areas depend on cross-team coordination and third-party responsiveness that is largely outside your direct control, which makes them harder to estimate and easier to underbudget. Assume they will take longer than your first instinct, and start them earlier in the remediation sequence than their apparent complexity suggests.

---

*Next: [Section 4, Policies and Procedures](04-policies-and-procedures/)*
