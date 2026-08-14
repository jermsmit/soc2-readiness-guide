# 9. Business Continuity and Disaster Recovery

Business continuity and disaster recovery sit under CC9 alongside vendor risk, both concerned with an organization's ability to withstand disruption. Where vendor risk is about disruption caused by someone else, this section is about disruption to your own systems and operations, and whether you can actually recover from it within a timeframe your business and your customers can tolerate.

This is a control domain where the gap between having a document and having a working capability is unusually wide. Almost every company can produce a business continuity plan. Far fewer can produce evidence that a backup has actually been restored successfully, or that a disaster recovery failover has actually been exercised end to end. Auditors know this, and it is exactly where they focus their testing.

## Business continuity plan versus disaster recovery plan

These get used interchangeably in casual conversation, but they answer different questions, and an auditor expects to see both addressed, even if they live in a single combined document.

**Business continuity** addresses how the business keeps operating, or resumes operating, when something disrupts normal operations, which could be a technical failure, a facility loss, a key vendor outage, or even a loss of critical personnel. It is broader than IT and covers how the organization as a whole continues to function.

**Disaster recovery** is the technical subset of that plan focused specifically on restoring IT systems and data after a disruptive event, such as infrastructure failure, data loss, or a significant security incident that takes systems offline. Recovery time objective and recovery point objective, covered below, live primarily in this part of the plan.

A company can have a reasonable disaster recovery capability, backups that restore, redundant infrastructure, and still have a weak business continuity plan if it has never thought through what happens if, for example, a key facility becomes inaccessible or a critical vendor goes dark for an extended period. Cover both explicitly rather than assuming DR readiness implies BC readiness.

## Setting recovery time objective and recovery point objective

**Recovery time objective, RTO**, is how long the business can tolerate a system being unavailable before the impact becomes unacceptable. **Recovery point objective, RPO**, is how much data loss, measured in time, the business can tolerate, which is really a question about how far back your most recent recoverable backup or replication point can be relative to the moment of failure.

Set these deliberately, not aspirationally. A common mistake is setting an RTO of a few hours because that sounds appropriately serious, without any operational basis for whether the current infrastructure and backup strategy can actually achieve it. If your actual restore process takes eighteen hours, documenting a four-hour RTO does not make the four-hour number true, it creates a target your DR test will fail against, and worse, an expectation your business and customers may be relying on without knowing it does not reflect reality.

Set RTO and RPO based on what the business genuinely needs, balanced against what your infrastructure can realistically deliver, and where there is a gap between the two, that gap becomes a specific infrastructure investment decision rather than a number quietly rounded down to look better on paper.

## Backup testing evidence: proving restores work, not just that backups run

This is the single most consequential distinction in this entire section, and it is worth stating directly: a backup job completing successfully every night is not evidence that your data is recoverable. It is evidence that a process wrote data somewhere. Whether that data can actually be restored, intact and usable, is a separate question that a completed backup job does not answer, and it is exactly the question an auditor is going to ask.

Backup failures are common, but the specific failure mode that causes real damage during an actual disaster is different: backups that report success but turn out to be corrupted, incomplete, or restorable only into a state that does not actually work, discovered for the first time during a real emergency rather than during a test. Building a program that catches this before it matters requires treating restore testing as its own control, distinct from and in addition to monitoring that backup jobs complete.

**What a credible restore testing program includes:**

- **A defined testing cadence.** Restore tests should happen on a regular schedule, not only when someone happens to think of it. Monthly or quarterly is a common cadence depending on system criticality, with more frequent testing for your most critical data stores.
- **An actual restore into a working environment**, not a checksum verification or a "backup file exists and is the expected size" check. A real restore test takes the backup, restores it into an isolated environment, and confirms the restored system or dataset is actually usable, meaning an application can connect to it, queries return expected results, and the data is internally consistent.
- **Documented results for every test**, including which backup was tested, when, who performed the test, what was verified, and the outcome. If the test fails, the documentation needs to show what failed, what the root cause was, and what was done to fix it, not just a note that the test did not go well.
- **Coverage across every critical data store**, not just your primary production database. Companies frequently test their main database restore process rigorously while leaving object storage backups, configuration backups, or secondary system backups completely unverified.

A concrete example of what this looks like in practice: on a monthly cadence, an engineer restores the most recent production database backup into an isolated staging environment, runs a defined set of validation queries against it to confirm row counts and referential integrity match expectations, confirms the application can connect to the restored database and perform basic read and write operations against it, and then logs the result, pass or fail, along with the backup timestamp tested and the total time the restore took, in a tracking system. That last detail, the time the restore actually took, is itself valuable evidence toward your RTO, since it tells you empirically whether your stated recovery time objective is achievable rather than assumed.

When a restore test fails, treat it the same way you would treat a failed control anywhere else in this program: root cause it, fix it, and re-test until it passes, with the entire sequence documented. A failed restore test that gets fixed and re-verified is actually a stronger piece of evidence for an auditor than a suspiciously perfect record with no failures ever recorded, since real infrastructure occasionally fails restore tests, and a record with zero failures across a long observation window sometimes signals the testing was not rigorous enough to catch anything.

## Annual DR test planning and documentation

Beyond routine backup restore testing, which validates data recoverability, a full disaster recovery test validates the broader capability: can the organization actually execute its documented recovery process end to end, under conditions that resemble a real disaster, within the RTO it has committed to.

**Planning the test.** Define the scenario in advance and make it specific rather than generic. "Test disaster recovery" is not a plan. "Simulate the loss of the primary production region and execute failover to the secondary region, measuring total time to restore full service" is a plan. Choose a scenario that reflects a genuine risk to your actual architecture, not a generic scenario copied from a template that may not map to how your systems are actually built.

Decide the scope of the test in advance: is this a full failover exercise where traffic actually moves to the recovery environment, or a tabletop walkthrough where the team talks through the steps without executing them technically. Both have value, and a mature program typically alternates or combines them, but be explicit about which one you are running and do not let a tabletop discussion get documented in a way that implies a full technical test occurred if it did not.

Assign specific roles for the exercise: who initiates the failover, who verifies each stage of recovery, who is responsible for monitoring the recovery environment once traffic has moved, and who makes the call to fail back to primary once the exercise concludes. Identify these roles before the test, not improvised during it.

**Executing the test.** Run the exercise against the actual documented DR procedure, not an ad hoc version assembled by whoever is running the test that day. If the documented procedure turns out to be wrong, outdated, or missing steps, that is itself a valuable finding, but it needs to be captured as a gap in the documentation, with the documentation corrected afterward, rather than silently worked around in the moment and left unfixed for the next person who has to follow it during an actual disaster.

Measure actual time to recovery against your stated RTO throughout the exercise. This is where the DR test either validates your RTO commitment or reveals that it needs to be revised, either by investing further in infrastructure to actually meet the stated target, or by adjusting the target to reflect what is realistically achievable.

**Documenting the test.** The completed test record should include the date, the scenario tested, who participated and in what roles, the actual time to recovery measured against the target RTO, any data loss observed measured against the target RPO, what worked as expected, what did not, and specific action items with owners and target dates for anything that needs to be fixed before the next test cycle.

Run this at minimum annually. For companies whose infrastructure changes significantly, a major architecture migration, a new critical system entering production, an additional test may be warranted sooner than the annual cycle, since a DR test executed against outdated infrastructure demonstrates very little about your actual current recovery capability.

## Life sciences note: recovery expectations for validated systems

For systems within your SOC 2 boundary that are also GxP-validated, backup and recovery carries an additional dimension beyond SOC 2's own expectations: data integrity requirements tied to the validated state of the system itself. A restored system needs to not only contain the correct data, it generally needs to be restorable into a state that preserves the validated configuration, meaning the restore process itself may need to be part of what was validated during the system's original qualification, rather than treated purely as an IT operations concern outside the scope of the quality system.

Coordinate backup and recovery testing for GxP-relevant systems with whoever owns computer system validation. In many cases, restore testing that satisfies SOC 2 evidence expectations can be structured to also satisfy validation requirements for periodic verification of backup and recovery procedures, but only if the test is planned with both sets of requirements in mind from the start, rather than IT Security running a SOC 2 focused test independently and Quality later discovering it does not fully address validation expectations.

## Common mistakes this section addresses

**Treating a successfully completed backup job as evidence that data is recoverable.** These are not the same thing, and an auditor testing this control will specifically ask for restore test evidence, not backup job completion logs. A monitoring dashboard showing green backup jobs every night proves nothing about whether any of those backups can actually be restored into a working state.

**Running DR tests as informal tabletop discussions while documenting them as if a full technical test occurred.** Both tabletop exercises and full failover tests have real value, but they answer different questions and provide different strength of evidence. Be explicit about which one was run, and build toward periodically executing the full technical version, since that is what actually validates whether your documented RTO is achievable rather than aspirational.

---

*Next: [Section 10, Evidence Collection and Audit Readiness](10-evidence-collection.md)*
