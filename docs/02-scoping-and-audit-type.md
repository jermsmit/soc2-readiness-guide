# 2. Scoping and Choosing Type I vs Type II

Before you write a single control, you need to answer two questions: what exactly is being audited, and which type of report are you going after. Get these wrong and you either spend months building evidence for systems nobody asked about, or you commit to a Type II observation window before your controls are stable enough to survive it. Both mistakes are expensive, and both are avoidable with a few weeks of deliberate scoping work up front.

## Type I versus Type II, the real difference

**Type I** evaluates whether your controls are suitably designed as of a specific point in time. The auditor looks at your policies, your architecture, and your processes and asks: if these controls operated as described, would they achieve the criteria. It does not test whether the controls actually operated that way over any meaningful period.

**Type II** evaluates the same design question, plus whether the controls operated effectively over an observation period, typically three to twelve months. This is the report almost every serious enterprise customer, and virtually every life sciences partner conducting vendor due diligence, will eventually require. A Type I report tells a customer your house has locks. A Type II report tells them the locks were actually used, every day, for months, and someone checked.

Type I is meaningfully easier and faster to produce. There is no observation window to wait out, and design gaps are easier to remediate than operating gaps, since you only have to fix the control once rather than prove months of consistent execution.

## Why most companies still start with Type I

Given that Type II is what customers actually want, it might seem like you should skip straight to it. In practice, starting with Type I first is usually the better sequencing, for three reasons.

First, a Type I report gives you and your auditor a checkpoint to confirm your control design is sound before you commit to an observation window. If your access control process has a structural gap, you want to find that in a Type I review, not three months into a Type II window where you now have to restart the clock.

Second, Type I gives you something to show customers immediately, which matters if a deal is waiting on SOC 2 status. A completed Type I report, with a Type II already in progress, is a credible answer to almost any procurement question. Telling a prospect "we're targeting Type II in eight months" without anything in hand is a much harder conversation.

Third, moving straight to Type II means every control gap you discover during the observation window either gets remediated mid-window, which can restart or extend your timeline, or gets carried into your final report as an exception. Type I lets you find and fix those gaps on a shorter cycle first.

The exception: if you already have mature, well-documented operational practices and strong internal confidence in your controls, going straight to Type II can save real time. This is uncommon for a first SOC 2 program, but not unheard of for companies that have already been running informal security practices at a high level of rigor.

## Defining your system boundary

Scoping is not just about which Trust Services Criteria apply, covered in Section 1. It is also about defining exactly which systems, environments, products, and data flows are inside the audit boundary, and which are explicitly excluded.

Your system description, the document your auditor will use to define this boundary, needs to answer:

- Which products or platforms are in scope. If you have multiple products, decide whether all of them need to be covered in year one or whether you can scope to your primary revenue-generating or customer-facing product first.
- Which environments are in scope. Production is almost always in scope. Staging and development environments are sometimes excluded if they do not process real customer data, but be explicit about this rather than leaving it ambiguous.
- Which data flows and third-party integrations are in scope. If a critical function of your product is fulfilled by a subprocessor, you need to decide whether that subprocessor's controls are relied upon (with their SOC 2 report reviewed as part of your evidence) or whether the boundary needs to extend further.
- Which corporate functions are in scope. HR systems, corporate IT, and general business operations are typically included at some level under the Control Environment criteria (CC1 and CC2), even if your product infrastructure is the primary focus.

Write this boundary down explicitly before your gap assessment starts. A vague boundary is how companies end up mid-audit discovering that a system nobody planned to include is now expected to have twelve months of access review evidence.

## Setting your observation window

For a Type II report, you choose the length of the observation period, most commonly three, six, nine, or twelve months for a first report, then typically twelve months for every report after that.

A shorter window, such as three months, gets you a completed report faster, which matters if a deal is time-sensitive. The tradeoff is that a shorter first Type II report is sometimes viewed with more scrutiny by sophisticated customers, since it demonstrates a shorter track record. A longer window, such as six or twelve months for a first report, gives more evidence of consistency but delays your report delivery accordingly.

A practical approach for a first Type II report: choose the shortest window that still gives your team enough time to demonstrate the control operated correctly at its natural cadence. If your access review cadence is quarterly, a three-month window only captures a single review cycle, which is thin evidence. A six-month window captures two review cycles and shows the process repeating, which is a materially stronger demonstration of the control working as designed.

Once your window starts, do not change your controls in ways that break continuity. If you switch identity providers, change your ticketing system, or restructure your engineering org mid-window, you need to be able to demonstrate the control still operated consistently across that change, which is more work than starting the window after the change is already settled.

## Building a realistic timeline

A first SOC 2 program, from kickoff to a Type II report in hand, commonly takes nine to fifteen months when you account for the full sequence: gap assessment, remediation, Type I audit and report, the Type II observation window itself, and Type II fieldwork and report delivery.

Compress this timeline with caution. The most common cause of a blown timeline is not the audit itself, it is remediation taking longer than expected because a control was more broken, or more absent, than the initial gap assessment suggested. Build in buffer time between your gap assessment and the start of your observation window rather than starting the clock on optimistic assumptions.

Talk to your auditor about their own lead time as well. Reputable firms with life sciences and SaaS experience often have a booking lead time of six to ten weeks or more, particularly during peak season in the fall when many companies are trying to close out annual compliance ahead of renewal cycles. Reserve your auditor slot as soon as you have a realistic target date, not after your controls are already ready.

## Life sciences note: multi-tenant platforms spanning commercial and clinical data

A scoping question that comes up often in life sciences and rarely appears in generic SOC 2 guidance: what happens when a single platform serves both commercial customers and clinical trial data under different regulatory regimes.

If your system handles both, for example a data platform used by commercial biotech customers and also by sponsors running active clinical trials, you need to decide early whether the SOC 2 boundary treats these as one system or requires differentiated controls and evidence for the clinical-data segment. In practice, most companies keep a single SOC 2 boundary but document in the system description where clinical trial data carries additional handling requirements, referencing your separate GxP or 21 CFR Part 11 controls rather than duplicating them inside the SOC 2 narrative.

The mistake to avoid is treating clinical data as simply "more sensitive data" within the same undifferentiated boundary, without documenting that it carries distinct regulatory obligations. Auditors experienced with life sciences clients will often ask directly whether any in-scope data is subject to GxP validation requirements, and a system description that already addresses this cleanly, rather than getting explained for the first time in an interview, moves fieldwork along much faster. Section 11 goes into this overlap in full.

## Common mistakes this section addresses

**Scoping too broadly in year one and creating audit fatigue across teams that did not need to be involved.** Every product, environment, and criterion you add to scope multiplies the number of people who need to be interviewed, the volume of evidence that needs to be collected, and the number of places a gap can hide. A tightly scoped first report that gets renewed and expanded in year two is almost always a better outcome than an ambitious first report that drags on for a year and exhausts the goodwill of every team involved.

**Starting the Type II observation window before controls are actually operating consistently.** It is tempting to start the clock as soon as policies are written, since every month of delay pushes your report date back. But if a control has not actually been exercised through a full cycle, for example if your first quarterly access review has not happened yet, starting the window before that first real cycle just means the early part of your observation period is going to generate an exception. Wait until the control has run at least once in its natural cadence before the window formally begins.

---

*Next: [Section 3, Running the Gap Assessment](03-gap-assessment.md)*
