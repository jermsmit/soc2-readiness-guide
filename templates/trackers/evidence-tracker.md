# Evidence Collection Tracker

**[Company Name]**
**Observation Window:** [Start Date] to [End Date]
**Owner:** [Name / Title, e.g. SOC 2 Program Owner]

This is a template. Replace bracketed content with your actual controls, owners, and cadence. This tracker is designed to work as a spreadsheet: import the table below into a spreadsheet tool for actual use, since a spreadsheet allows filtering, sorting, and status tracking that a static markdown table does not. The structure here shows the columns and a set of example rows covering common controls referenced throughout this guide.

## How to use this tracker

Each row represents one control. As you build out your control matrix during the gap assessment (see [Section 3](../../docs/03-gap-assessment.md)), add a row here for each control that requires ongoing evidence, not just controls you are remediating once. Update the "Last Collected" and "Status" columns as evidence is actually gathered, on the cadence defined for that control, not just when preparing for an audit.

Review this tracker against its own due dates on a regular internal cadence, monthly or quarterly, independent of any active audit engagement, as described in [Section 10](../../docs/10-evidence-collection.md) and [Section 13](../../docs/13-continuous-compliance.md). A tracker that is only updated right before fieldwork defeats its own purpose.

## Column definitions

- **Control ID.** A short reference code, consistent with your control matrix from the gap assessment.
- **Control Description.** Plain-language description of what the control requires.
- **TSC / CC Reference.** Which Trust Services Criteria or Common Criteria category this maps to (see [Section 1](../../docs/01-trust-services-criteria.md)).
- **Evidence Type.** What form the evidence takes, for example an access review log, a signed policy acknowledgement, a restore test record.
- **Evidence Source.** Where the evidence is actually generated or stored, for example a specific tool, ticketing system, or repository.
- **Owner.** The specific individual responsible for ensuring this evidence is generated and collected, not a team or department.
- **Collection Frequency.** How often this evidence needs to be generated, for example quarterly, monthly, per-event, annually.
- **Last Collected.** The date evidence was most recently gathered for this control.
- **Next Due.** The date the next instance of this evidence is due, calculated from the frequency.
- **Status.** On Track, At Risk, or Overdue.
- **Auditor Notes.** Any notes from a prior audit cycle relevant to this control, including prior findings or auditor feedback on evidence sufficiency.

## Example tracker

| Control ID | Control Description | TSC / CC Reference | Evidence Type | Evidence Source | Owner | Collection Frequency | Last Collected | Next Due | Status | Auditor Notes |
|---|---|---|---|---|---|---|---|---|---|---|
| AC-01 | Quarterly access review for production systems | CC6 | Access review log with reviewer, date, and outcome per system | Identity provider export + review ticket | [Name] | Quarterly | [Date] | [Date] | [Status] | |
| AC-02 | Timely deprovisioning upon termination | CC6 | Deprovisioning log showing termination date and access removal timestamp | HRIS + identity provider log | [Name] | Per-event | [Date] | Ongoing | [Status] | |
| AC-03 | Employee policy acknowledgement | CC1, CC2 | Signed acknowledgement record | Policy management tool | [Name] | At onboarding + annually | [Date] | [Date] | [Status] | |
| CM-01 | Code changes reviewed and approved before merge | CC8 | Pull request approval record | Version control system (e.g. GitHub) | [Name] | Continuous | [Date] | Ongoing | [Status] | |
| CM-02 | Infrastructure changes reviewed before apply | CC8 | Terraform plan review and approval record | CI/CD pipeline logs | [Name] | Continuous | [Date] | Ongoing | [Status] | |
| CM-03 | Emergency change retrospective review | CC8 | Documented retrospective review linked to incident | Ticketing system | [Name] | Per-event | [Date] | Ongoing | [Status] | |
| IR-01 | Incident response tabletop exercise | CC7 | Exercise documentation with findings and action items | Internal documentation repository | [Name] | Annually | [Date] | [Date] | [Status] | |
| IR-02 | Post-incident review for Medium+ severity incidents | CC7 | Completed post-incident review with tracked action items | Ticketing system | [Name] | Per-event | [Date] | Ongoing | [Status] | |
| VR-01 | Critical/High tier vendor SOC 2 report review | CC9 | Reviewed SOC 2 report with complementary controls assessment documented | Vendor inventory | [Name] | Annually | [Date] | [Date] | [Status] | |
| VR-02 | Vendor risk tiering current and accurate | CC9 | Vendor inventory with tier assignments | Vendor inventory | [Name] | Ongoing, reassessed at scope change | [Date] | Ongoing | [Status] | |
| BC-01 | Backup restore test | CC9, Availability | Restore test log with validation results | Internal test tracking | [Name] | Monthly or quarterly | [Date] | [Date] | [Status] | |
| BC-02 | Annual disaster recovery test | CC9, Availability | DR test report with RTO/RPO measured against target | Internal documentation repository | [Name] | Annually | [Date] | [Date] | [Status] | |
| RA-01 | Organizational risk assessment | CC3 | Documented risk assessment with identified risks and mitigations | Internal documentation repository | [Name] | Annually | [Date] | [Date] | [Status] | |
| PP-01 | Policy review and re-approval | CC5 | Version history with approval record | Policy management tool | [Name] | Annually | [Date] | [Date] | [Status] | |

Add rows as needed for every control in your matrix, including any additional Trust Services Criteria in scope, such as Availability, Confidentiality, or Processing Integrity, and any life sciences specific controls, for example evidence that also serves 21 CFR Part 11 or HIPAA obligations, as described in [Section 11](../../docs/11-life-sciences-considerations.md).

## A note on automation

Several rows above can be populated automatically rather than tracked manually, particularly evidence sourced from version control, identity providers, and CI/CD pipelines. See [Section 10](../../docs/10-evidence-collection.md) for suggestions on where automation tends to add the most value in an evidence collection workflow, and where manual documentation, for controls requiring genuine human judgment, remains the stronger approach.
