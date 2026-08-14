# 6. Vendor and Third-Party Risk Management

Nearly every company running a SOC 2 program depends on other companies to deliver its product: cloud infrastructure, identity providers, customer support platforms, analytics tools, and dozens of smaller services woven into daily operations. Each one is a point where your data, or your customers' data, leaves your direct control. CC9 exists because an auditor cannot evaluate your risk posture without also evaluating the risk you have inherited from everyone you depend on.

This is also, alongside access control, one of the two areas that consistently takes longer to remediate than companies expect, mostly because it depends on getting responses from third parties who have no particular urgency to help you pass your audit. Start this earlier than your instinct suggests.

## Building a vendor inventory

You cannot manage vendor risk you have not inventoried. The starting point is a complete, centralized list of every vendor with any data access or operational criticality, not just the obvious infrastructure providers.

This inventory is usually more incomplete than people expect on the first pass. Pull from multiple sources to build it out: your accounts payable or expense system will surface vendors nobody remembered to mention, your SSO or identity provider will show every third-party application employees have connected, and interviews with engineering, sales, and customer success will surface tools adopted informally outside any procurement process. This last category, tools adopted without going through procurement, is often where the largest gaps hide, since nobody owns the relationship and nobody has ever asked the vendor for a security questionnaire.

For each vendor, the inventory should capture: what data or system access the vendor has, who the internal owner is, what tier the vendor is classified as, when the last security review happened, and when the next one is due. This inventory is what you hand your auditor, and it is also the operational tool that keeps the program running after the audit is over.

## Risk tiering

Not every vendor deserves the same scrutiny, and treating them all the same is how vendor risk programs collapse under their own weight. A payroll processor handling sensitive employee data and a scheduling tool with no data access at all should not go through the same review process.

The tiering model in the [Vendor Risk Management Policy template](../templates/policies/vendor-risk-management-policy.md) uses four tiers: Critical, High, Moderate, and Low, based on the combination of data sensitivity and operational criticality. A vendor earns a higher tier if either factor is high, even if the other is low. A vendor with only moderate data access but whose failure would take down a core product function still deserves Critical-tier scrutiny, and the reverse is equally true: a vendor with minimal operational role but broad access to sensitive data does not get a pass just because you could survive losing them.

Assign tiers at the point of onboarding, not retroactively during audit prep. Reassess tier whenever a vendor relationship expands in scope, since a tool that started as a small pilot with limited access frequently grows into something with much broader access over time without anyone revisiting the original risk classification.

## What to actually request from vendors

For Critical and High tier vendors, request:

- **The vendor's own SOC 2 report**, Type II where available, since it demonstrates their controls have operated over time rather than just being designed correctly at a point in time.
- **A completed security questionnaire**, covering data handling practices, encryption standards, access control, and incident history. Keep this proportionate: a lengthy generic questionnaire that asks the same fifty questions of every vendor regardless of tier produces low response rates and low-quality answers. Scale the depth of the questionnaire to the tier.
- **A summary of any recent penetration test**, where the vendor's risk profile warrants it. Full reports are often withheld for the vendor's own security reasons, but a summary of scope, findings severity, and remediation status is a reasonable ask.
- **A signed data processing agreement or equivalent contractual data protection terms**, particularly where personal data is involved.

Moderate tier vendors can typically be satisfied with an abbreviated questionnaire and confirmation that a data processing agreement exists where relevant. Low tier vendors are recorded in the inventory without a formal review requirement, reassessed only if their scope changes.

## Reading a vendor's SOC 2 report properly

Receiving a vendor's SOC 2 report and filing it away is not the same as reviewing it, and this is one of the more common gaps auditors find during vendor risk testing. A report needs to actually be read, and specifically, someone needs to review the section on complementary user entity controls.

This section describes controls the vendor assumes their customer, meaning you, has implemented independently. A cloud infrastructure vendor's report might state that they assume the customer manages access to their own accounts within the platform, encrypts data at the application layer, or maintains their own incident response process for events originating on the customer side of the shared responsibility boundary. If you have not actually implemented the controls the vendor is assuming you have, you have a gap, and it is a gap your own auditor will expect you to have identified and closed, not one you can point to the vendor's report as having covered for you.

Build this review into your vendor onboarding and renewal process as a specific step, not an afterthought. Document which complementary controls apply to each Critical and High tier vendor, and track them the same way you track any other control gap.

## Setting a review cadence and assigning ownership

The single most common way vendor risk programs fail after a successful first audit is that the review cadence quietly lapses once the pressure of the audit is gone. A review that happened once during audit prep, with no owner responsible for the next cycle, is not a program, it is a one-time event that happened to coincide with an audit.

Assign a specific individual, not a team, as the owner of each vendor relationship, responsible for triggering the next review when it comes due. Build the review cadence into a calendar or ticketing system that generates a task automatically rather than depending on someone remembering. Critical tier vendors reviewed annually at minimum, with more frequent check-ins if the relationship or the vendor's own risk profile changes materially, is a reasonable default, adjusted for your actual risk tolerance.

Track review completion in the same central vendor inventory referenced above. When your auditor asks to see evidence that vendor reviews are happening on schedule, the inventory itself, showing last review date and next due date for every in-scope vendor, is exactly what they are looking for.

## Life sciences note: CROs, CDMOs, and clinical data platforms

Life sciences companies carry a category of vendor relationship that most generic SOC 2 guidance does not address at all: vendors who are simultaneously subject to GxP vendor qualification requirements and SOC 2 vendor risk review. Contract research organizations, contract development and manufacturing organizations, and platforms handling clinical trial data all fall into this category.

Running these as two entirely separate assessments, one owned by Quality for GxP qualification and one owned by IT Security for SOC 2, duplicates effort and often produces inconsistent records, since the two teams are asking related but not identical questions and rarely compare notes. The stronger approach is a single vendor record that captures both sets of requirements, with Quality and IT Security jointly reviewing any vendor that triggers both frameworks.

Before initiating SOC 2 vendor due diligence for a vendor that might already be GxP qualified, check with Quality first. In many cases, existing GxP qualification documentation, audits, quality agreements, already covers a substantial portion of what a SOC 2 vendor review would otherwise need to gather independently, and the actual incremental work is narrower than it first appears. This coordination is worth building into your Vendor Risk Management Policy explicitly, as the template in Section 4 does, rather than leaving it to be discovered the first time a vendor relationship happens to span both requirements.

## Common mistakes this section addresses

**Collecting vendor SOC 2 reports without reading them, and missing complementary controls the vendor expects you to implement.** A filed-away report satisfies nothing. The complementary user entity controls section is often the most consequential part of the report for your own compliance posture, and skipping it is one of the most common gaps auditors identify during vendor risk testing.

**No tiering model, so a payroll vendor and a critical infrastructure vendor get the same shallow review.** Applying uniform, minimal scrutiny across every vendor regardless of risk either under-protects your highest-risk relationships or over-burdens your lowest-risk ones, usually both at once. A tiering model that actually drives differentiated review depth is what makes the program sustainable rather than something that gets abandoned under its own workload.

---

*Next: [Section 7, Change Management](07-change-management.md)*
