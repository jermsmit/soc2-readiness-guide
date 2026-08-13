# 1. Trust Services Criteria, Explained

If you take one thing from this section, take this: SOC 2 is not a checklist of technical controls. It is an attestation that your organization's controls meet a set of criteria published by the AICPA, called the Trust Services Criteria (TSC). Everything else in this guide, every policy, every access review, every piece of evidence, exists to support a claim your auditor is willing to put their name behind: that your controls actually achieve these outcomes, consistently, over time.

Understanding the criteria before you touch a single policy template will save you months. Most companies that struggle with SOC 2 did not struggle because they lacked controls. They struggled because they built controls without understanding what the controls were supposed to prove.

## The five Trust Services Criteria

The AICPA defines five categories:

**Security.** Also called the Common Criteria. This is mandatory for every SOC 2 report regardless of scope. It covers protection against unauthorized access, both physical and logical, and forms the foundation that the other four categories build on.

**Availability.** Whether the system is available for operation and use as committed or agreed. This matters most for companies where uptime is a contractual commitment, such as SLA-backed SaaS platforms.

**Processing Integrity.** Whether system processing is complete, valid, accurate, timely, and authorized. This is the criterion most relevant to any platform that transforms, calculates, or transmits data where errors have real consequences, which in life sciences often means clinical data pipelines, lab result systems, or dosing calculation tools.

**Confidentiality.** Whether information designated as confidential is protected as committed or agreed. This applies to intellectual property, business plans, and any data your customers or partners have asked you to protect beyond what Security alone requires.

**Privacy.** Whether personal information is collected, used, retained, disclosed, and disposed of in conformity with your privacy notice and with criteria set by the AICPA. This is the most detailed and most frequently over-scoped category. Many companies mistakenly believe they need Privacy because they handle personal data, when in most cases Confidentiality already covers the relevant risk.

Security is always in scope. Everything else is a choice, and that choice should come from your product, your contracts, and your customers, not from what a competitor's marketing page claims.

## How most companies actually scope this

In practice, the overwhelming majority of SOC 2 reports include Security plus Availability, and sometimes Confidentiality. Full five-category reports are uncommon, and Privacy in particular should be a deliberate decision made with legal counsel, not a default.

Ask three questions when deciding scope:

1. Does your customer contract or a specific enterprise deal require a criterion by name? Read the actual contract language, not a summary someone gave you secondhand.
2. Does your product make a commitment that a criterion directly maps to? An uptime SLA points to Availability. A promise to keep research data confidential points to Confidentiality.
3. Would adding a criterion require controls you do not currently have and cannot build within your audit timeline? If yes, either extend the timeline or leave it out of this cycle and add it in year two.

Scoping too broadly in year one is one of the most common and most expensive mistakes in a first SOC 2 program. Every criterion you add multiplies the evidence you have to produce and the interview time your team has to give up. Add scope when you have a real reason to, not because it looks more thorough on paper.

## The Common Criteria: CC1 through CC9

Security is broken into nine categories, referred to as CC1 through CC9. These form the backbone of every SOC 2 report, and you will see them referenced constantly by your auditor, so it is worth knowing what each one actually means rather than treating them as arbitrary labels.

- **CC1: Control Environment.** Tone at the top, organizational structure, and commitment to integrity and ethical values. This is where your code of conduct, org chart, and board or leadership oversight of security get evaluated.
- **CC2: Communication and Information.** How the organization communicates information, both internally and externally, needed to support the functioning of internal controls. Your security awareness training and incident communication plans live here.
- **CC3: Risk Assessment.** How the organization identifies and analyzes risks to achieving its objectives. This is where a documented risk assessment process becomes evidence, not a formality.
- **CC4: Monitoring Activities.** Ongoing evaluations to ascertain whether components of internal control are present and functioning. Your access reviews and control monitoring cadence live here.
- **CC5: Control Activities.** The policies and procedures that help ensure management directives are carried out. This is broad and touches nearly every other section of this guide.
- **CC6: Logical and Physical Access Controls.** This is the largest and most heavily tested category in almost every audit. It covers authentication, authorization, network security, and physical access to facilities and infrastructure.
- **CC7: System Operations.** Detection and management of processing deviations, including incident response and vulnerability management.
- **CC8: Change Management.** How changes to infrastructure, data, and software are authorized, tested, and approved before deployment.
- **CC9: Risk Mitigation.** How the organization identifies, selects, and develops risk mitigation activities for risks arising from potential business disruptions and the use of vendors and business partners.

Notice that CC6 through CC9 map almost directly to sections 5 through 8 of this guide: access control, vendor and third-party risk touches CC9, change management is CC8, and incident response is CC7. That is not a coincidence. The structure of this guide follows the structure of what your auditor will actually test.

## What a finished SOC 2 report looks like

Before you build toward something, it helps to know what you are building toward. A SOC 2 report has four sections, regardless of firm:

1. **Management's assertion.** A letter from your company stating that the description of your system and controls is accurate and that the controls were suitably designed, and for Type II, operated effectively.
2. **Independent auditor's report.** The auditor's opinion, which is the section most people mean when they ask if you "passed." An unqualified opinion means no exceptions were found. A qualified opinion means the auditor identified specific control failures.
3. **Description of the system.** A detailed narrative of your infrastructure, software, people, procedures, and data, written to give a reader unfamiliar with your company enough context to understand what was tested.
4. **Description of tests of controls and results.** For Type II reports, this section lists every control tested, how it was tested, and what the auditor found. This is the section most customers' security teams actually read line by line.

Ask your auditor for a sample report, or an anonymized excerpt, during the selection process. Seeing the actual output before you start building controls toward it makes every later decision easier, because you can picture exactly what evidence needs to support each line.

## Life sciences note: why Confidentiality shows up more often than you'd expect

Most generic SOC 2 guidance treats Confidentiality as optional and secondary to Availability. In life sciences, particularly for companies handling clinical trial data, proprietary research, or partner intellectual property under NDA, Confidentiality is frequently just as important as Security itself, and sometimes more heavily scrutinized by customers than Availability is.

If your platform touches unpublished research data, clinical trial results before disclosure, or competitive intellectual property from pharma and biotech partners, expect your customers' security and legal teams to ask specifically whether Confidentiality is in scope. Building it in from the start, even if it adds a few weeks to your gap assessment, is usually less costly than adding it in a second cycle after a customer contract already assumed it was covered.

Confidentiality is not the same as Privacy, and it is not a replacement for HIPAA compliance if you handle protected health information. Section 11 covers where these regulatory frameworks overlap with SOC 2 and where they remain entirely separate obligations.

## Common mistakes this section addresses

**Choosing criteria based on what competitors have rather than what your product and contracts actually require.** A competitor's SOC 2 badge tells you nothing about their contractual obligations or their product architecture. Scope your report against your own commitments.

**Treating the criteria as a checklist instead of a description of outcomes an auditor will test.** The Trust Services Criteria describe what a system should achieve, not a specific list of tools or controls you must implement. Two companies can satisfy CC6 with completely different technical implementations, as long as both can demonstrate the outcome: unauthorized access is prevented and detected. Chasing a checklist someone else published, instead of understanding the outcome you need to prove, is how companies end up with controls that look right on paper but fall apart the moment an auditor asks a follow-up question.

---

*Next: [Section 2, Scoping and Choosing Type I vs Type II](02-scoping-and-audit-type.md)*
