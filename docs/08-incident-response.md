# 8. Incident Response

Incident response is the control domain where auditors most want to see something happen, not just be described on paper. CC7 covers detection and management of processing deviations, and while access control and change management can often be evidenced through system logs and ticket histories alone, incident response requires proof that your process has actually been exercised, either through a real incident or a deliberate simulation. A plan that has never been tested is, in an important sense, not yet a plan.

If you have not already reviewed it, the [Incident Response Policy template](../templates/policies/incident-response-policy.md) from Section 4 lays out the structural commitments, severity classification, roles, escalation timing, this section walks through how to actually operationalize them and what auditors look for as evidence that the process works.

## Building a plan people will actually follow under pressure

The most common failure mode with incident response plans is that they are written once, during audit prep, by someone who is not the person who will actually be running point during a real incident. The result is a document that reads well but does not match how the team that would respond actually thinks or communicates under pressure.

Build the plan with input from whoever would realistically be the incident commander during an actual event, not just from IT Security or compliance in isolation. Keep the plan itself short enough that someone can actually reference it during a live incident rather than needing to read ten pages to figure out what to do next. A severity classification table, a clear escalation path, and a communication template are more useful in the moment than an exhaustive narrative description of your security philosophy.

## Detection and reporting

An incident response process is only as good as its ability to detect that something is happening in the first place. Detection comes from two sources: automated tooling and human reporting, and both need clear paths into your response process.

For automated detection, this means your monitoring, endpoint detection, and cloud security tooling need alerts routed somewhere a person will actually see them promptly, not into a channel that gets checked once a week. For human reporting, this means every employee needs to know, concretely, where to report something they think might be a problem, and needs to feel safe reporting a false alarm without being made to feel foolish for raising it. A culture where employees hesitate to report because they are not sure it is a real incident is a detection gap as serious as a missing monitoring tool.

A concrete example worth building into training: an employee receives a suspicious email that looks like a password reset request for a system they use, and clicks the link before realizing something is off. The right outcome is that employee reports it immediately, even though they are embarrassed, because early reporting is what allows a contained credential compromise to stay a Low or Medium severity event instead of escalating into something much larger. Training that makes this scenario explicit, rather than a vague reminder to "watch out for phishing," produces better real-world reporting behavior.

## Severity classification in practice

The severity table in the policy template gives you four tiers, but classification only works if the person triaging an incoming report can actually apply it quickly and consistently. Walk through a couple of examples to make the boundaries concrete.

A single employee's laptop is lost at an airport. If the laptop is encrypted, requires authentication to unlock, and does not have locally cached access to production systems, this is likely a Low or Medium severity event, since the risk of actual data exposure is limited by existing controls. If the same laptop was unencrypted, or had a password manager left unlocked with saved production credentials, the same physical event becomes High or Critical, because the actual exposure risk is materially different. The lesson is that severity classification depends on the controls surrounding the event, not just the event category itself, which is why a rigid keyword-based classification system tends to misfire in practice.

A vulnerability scan flags a critical CVE on a production system. Before that finding is treated as an active incident, triage needs to establish whether the vulnerability is actually exploitable in your environment, whether it is internet-facing, and whether there is any evidence of active exploitation. An unexploited but critical vulnerability on an internal, non-internet-facing system is a High priority remediation item, but it is a different classification than a confirmed active compromise, and treating every critical CVE alert as a Critical severity incident quickly exhausts a team's ability to respond meaningfully to the incidents that actually need that level of urgency.

## Running a tabletop exercise

If your company has not yet had a real incident that exercised the full response process, and most companies pursuing a first SOC 2 report have not, a tabletop exercise is how you generate the evidence an auditor is looking for that the plan actually works when people try to follow it.

A useful tabletop exercise does not need to be elaborate. Pick a realistic scenario, for example a report of unusual database query activity that might indicate unauthorized access, and walk the response team through it step by step in a facilitated session: who gets notified first, what does the incident commander do in the first fifteen minutes, at what point does the scenario escalate to involve legal or executive leadership, what would the customer-facing communication look like if this turned out to be confirmed.

Run the exercise with the actual people who would respond to a real incident, not a substitute group assembled for convenience. Document what worked, what did not, and specifically where the plan or the participants' understanding of the plan broke down. A tabletop that surfaces a real gap, for example discovering that nobody was quite sure who had the authority to approve external customer communication, and that gap gets fixed afterward, is far more valuable audit evidence than an exercise that goes smoothly because the scenario was too simple to test anything meaningful.

## Post-incident review as an evidence generator

Every incident of Medium severity or above should produce a documented post-incident review, and this document is one of the more valuable pieces of evidence in your entire SOC 2 program, because it demonstrates the full loop: detection, response, and improvement.

A strong post-incident review includes a factual timeline built from the logged response actions, an honest assessment of what worked and what did not, and specific, tracked action items rather than vague commitments to "do better." If a review identifies that detection was delayed because an alert routed to a channel nobody monitored closely, the action item is a specific change to alert routing, tracked to completion in your ticketing system, not just a note that the team will be more vigilant going forward.

Auditors testing CC7 will often ask to see a completed post-incident review as part of their sample. A review that shows genuine self-assessment and concrete follow-through is a stronger piece of evidence than a report showing no incidents occurred at all during the observation window, since it demonstrates the process functions, rather than simply having gone untested.

## Life sciences note: coordinating with deviation and CAPA processes

If your company operates under a quality management system, you likely already have a deviation and Corrective and Preventive Action, CAPA, process governing how quality events are investigated and resolved. Security incidents affecting GxP-relevant systems sit at the intersection of your Incident Response Policy and your quality deviation process, and running these as two entirely separate, disconnected investigations is both inefficient and a source of inconsistency an inspector or auditor could flag.

Where a security incident affects a GxP-relevant system, the post-incident review should feed directly into the applicable deviation and CAPA record rather than existing as a parallel document that Quality never sees. In practice, this often means the incident commander loops in Quality at the point an incident is confirmed to touch a GxP-relevant system, and the resulting corrective actions are tracked through whichever system, the CAPA system or the security ticketing system, is the appropriate system of record, with a clear cross-reference in the other so both records connect back to the same underlying event.

Regulatory and contractual notification obligations also compound in this space. A security incident affecting clinical trial data may trigger notification requirements under HIPAA, applicable state breach law, sponsor contractual terms, and potentially disclosure obligations tied to the trial itself. Build a clear map, maintained by Legal and Quality together, of which notification obligations apply under which circumstances, so that during an actual incident, the incident commander is executing a known process rather than discovering the full scope of notification requirements for the first time under time pressure.

## Common mistakes this section addresses

**A written plan that has never been tested through a real incident or a tabletop exercise.** Auditors testing a Type II report want evidence the process has actually been exercised during the observation window. A plan that exists only on paper, however well written, does not demonstrate operating effectiveness, and running at least one tabletop exercise before your observation window begins is one of the highest-value, lowest-cost steps in this entire program.

**Post-incident reviews that document what happened without producing tracked, specific action items.** A review that identifies a gap and stops there, without a concrete follow-up tracked to completion, misses the part of CC7 that matters most: evidence that the organization actually learns from incidents and improves, rather than simply logging that something occurred.

---

*Next: [Section 9, Business Continuity and Disaster Recovery](09-business-continuity-dr.md)*
