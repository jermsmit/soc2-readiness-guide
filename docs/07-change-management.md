# 7. Change Management

Change management, CC8, governs how changes to code, infrastructure, and configuration move from an idea into production. It is one of the more mechanical control domains to build, since most engineering teams already have some version of code review and deployment process in place before SOC 2 ever enters the conversation. The work here is less about inventing new practices from scratch and more about making sure the practices you already have produce evidence, cover every path a change can take into production, and hold up when tested against a real sample of changes rather than the best-case example everyone remembers.

## What auditors are actually testing

An auditor testing CC8 wants to see three things for a sample of changes pulled from across your observation window: the change was reviewed by someone other than the person who made it, the change was approved before it reached production, and there is a clear, connected record linking the change to its review and approval. All three need to be true together. A change that was reviewed but deployed before approval finished, or a change where the approver and the author are the same person, is a finding regardless of how good the underlying code was.

## Defining what counts as a change

Before building process around change management, define scope clearly. Most programs cover:

- **Application code changes**, deployed through your normal release process
- **Infrastructure changes**, whether managed through infrastructure as code or made directly against cloud consoles
- **Configuration changes** to production systems, including access control settings, network rules, and application configuration values that affect behavior without a code deployment
- **Database schema changes**, which often move through a different pipeline than application code and get missed if change management is defined too narrowly around code deploys alone

A common gap: a company has excellent GitHub pull request review practices for application code, which satisfies the auditor's sample when they pull application deploys, but has no equivalent review process for infrastructure changes made directly through the cloud provider's console. If an engineer can log into AWS and change a security group rule without any review, that is a CC8 gap even if every application code change goes through pristine pull request review. Map out every path a change can reach production through, not just the one your engineering team thinks of first when asked about "deployments."

## Standard change: code review and deployment example

For most SaaS companies, the standard change path looks something like this, and it is worth walking through concretely since the details matter for evidence:

1. A developer opens a pull request against the main branch, describing the change.
2. At least one other engineer reviews the pull request and approves it in the version control system. The approval itself, recorded in the tool, is the evidence.
3. Automated tests run against the pull request, and the branch protection rule on the repository requires those tests to pass before merge is even possible.
4. Once approved and passing, the change merges to main.
5. A deployment pipeline builds and deploys the merged code to production, either automatically or with a manual trigger, depending on your release process.
6. The deployment itself is logged, with a timestamp and a link back to the merged pull request that produced it.

If your pipeline works this way already, most of the evidence-generation work is done for you by tools you already use. The task is confirming branch protection rules actually enforce the review requirement, rather than being a setting that was configured once and could technically be bypassed by someone with admin rights, and confirming your deployment logs actually retain the link back to the originating change for the length of your observation window.

## Infrastructure as code example

For infrastructure changes managed through code, for example a Terraform configuration change to add a new database instance or modify a network rule, the same review-before-merge pattern applies, but the evidence needs to extend one step further: proof that the applied infrastructure state actually matches what was reviewed and approved, not just that a pull request was approved at some point.

A CI pipeline that runs `terraform plan` on every pull request, requires review and approval of that plan output before merge, and then runs `terraform apply` only through an automated pipeline triggered by the merge, produces exactly this evidence. What creates a gap is any path where an engineer can run `terraform apply` locally, or make an equivalent change directly through a cloud console, bypassing the reviewed pipeline entirely. If that path exists technically, even if it is discouraged by policy, assume an auditor sampling infrastructure changes will eventually find one that went through it, and either close the technical path or build a documented exception process for when it happens.

## Emergency changes

Every change management process eventually meets a production incident that cannot wait for standard review. Auditors do not expect emergency changes to never happen. They expect a defined, documented emergency change process that still produces evidence, even if that evidence is captured after the fact rather than before deployment.

A workable emergency change process looks like: a defined threshold for what qualifies as an emergency, generally tied to active production impact rather than convenience; a requirement that the change still be deployed by, or with real-time awareness of, someone with deployment authority, rather than happening entirely outside any visibility; and a mandatory retrospective review within a short window afterward, where a second engineer reviews what was changed and confirms it after the fact, with that review documented the same way a standard pull request approval would be.

For example, if a production outage requires an immediate configuration rollback at 2am, the on-call engineer makes the change to restore service, and by the next business day, a peer reviews the exact change that was made, documents the retrospective approval in a ticket linked to the incident, and confirms whether any follow-up work is needed to bring the change fully in line with standard process. This produces a real evidence trail even though the sequence, review after deployment rather than before, is inverted from the standard path. What matters to an auditor is that the inversion is documented, bounded, and consistently followed, not treated as a loophole that gets used whenever standard review feels inconvenient.

## CI/CD pipeline controls and automated evidence

Where CI/CD pipelines are configured correctly, they generate stronger and more consistent evidence than manual approval processes, since a pipeline cannot forget to log a step the way a person can forget to update a ticket. The evidence an auditor can pull directly from pipeline logs, showing every deployment, the commit it corresponds to, and the approvals gathered before it triggered, is often cleaner than anything a manual change management system produces.

The condition for this to work as evidence is that the pipeline configuration itself is protected: if any engineer can modify the CI/CD pipeline definition without review, they could in principle weaken or bypass its own controls, which undermines the evidence it produces. Treat changes to your pipeline configuration, and to branch protection rules themselves, as changes that require the same review rigor as the code they are meant to protect.

## Life sciences note: aligning with computer system validation change control

For any system in your SOC 2 boundary that is also GxP-validated, you likely already have a formal change control process governed by your quality system, typically requiring a documented change request, impact assessment, testing, and approval before a validated system is modified. This process, done well, already satisfies CC8 for that system, often more rigorously than a typical SaaS company's pull request review does.

The risk is not that your GxP change control is insufficient for SOC 2. It is usually the opposite: the GxP process is well documented for the validated system itself, but the SOC 2 boundary often extends to supporting infrastructure and non-validated systems that sit outside the formal change control SOP entirely. A validated clinical data application might have exemplary change control, while the underlying cloud infrastructure it runs on, managed by an infrastructure team outside the quality system's direct scope, has a much less rigorous process. An auditor testing CC8 across your full SOC 2 boundary will sample both, and the gap between them is where findings tend to appear.

Map your SOC 2 system boundary against your GxP change control scope explicitly, identify anywhere the two do not fully overlap, and either extend GxP-equivalent rigor to the gap or build a comparable SOC 2 specific change management process for it. Involve Quality in this mapping rather than having IT Security assume the two processes already align.

## Common mistakes this section addresses

**Reviewing application code changes rigorously while leaving infrastructure or configuration changes unreviewed.** A pull request process for application code is necessary but not sufficient. Map every path a change can reach production, including infrastructure as code, direct cloud console access, and configuration management tools, and apply equivalent review requirements across all of them.

**Treating emergency changes as an unofficial exception rather than a documented process with its own evidence trail.** Emergency changes will happen. What auditors are testing is whether your process anticipates that and still produces evidence, through a retrospective review requirement, rather than allowing emergency change to become a routine way to bypass standard review whenever it is inconvenient.

---

*Next: [Section 8, Incident Response](08-incident-response.md)*
