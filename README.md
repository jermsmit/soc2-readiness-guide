# SOC 2 Readiness Guide for Life Sciences Companies

A practical, field-tested guide to preparing for a SOC 2 audit, written from the perspective of an IT leader who has run this process inside life sciences organizations. It covers the standard SOC 2 body of knowledge along with the specific issues that come up when SOC 2 overlaps with GxP, 21 CFR Part 11, HIPAA, and clinical data handling.

This is not a marketing piece from a compliance vendor. It is the sequence of decisions, documents, and conversations that actually get a company through a Type I and Type II audit without burning out the engineering and IT teams along the way.

## Who this is for

IT leaders, security leads, and compliance owners at life sciences companies (biotech, pharma, medtech, digital health, clinical research) who are:

- Preparing for a first SOC 2 audit, often because a customer or investor is requiring it
- Rebuilding a SOC 2 program that was assembled too quickly the first time
- Trying to run SOC 2 and GxP/21 CFR Part 11 compliance without duplicating work

## How to use this guide

Read it in order if you are starting from zero. If you already have a program underway, jump to the section that matches your current gap. Every section stands on its own.

Each section in `/docs` includes:

- What the requirement actually means, in plain language
- What auditors look for as evidence
- Common mistakes and where companies lose the most time
- Life sciences specific notes, where relevant

The `/templates` folder has usable starting points: policy templates, an evidence tracker, and a RACI matrix. These are drafts, not legal advice. Have your counsel and your auditor review anything before you publish it internally.

## Table of contents

1. [Trust Services Criteria, explained](docs/01-trust-services-criteria.md)
2. [Scoping and choosing Type I vs Type II](docs/02-scoping-and-audit-type.md)
3. [Running the gap assessment](docs/03-gap-assessment.md)
4. [Policies and procedures](docs/04-policies-and-procedures/)
5. [Access control and identity](docs/05-access-control-and-identity.md)
6. [Vendor and third-party risk management](docs/06-vendor-and-third-party-risk.md)
7. [Change management](docs/07-change-management.md)
8. [Incident response](docs/08-incident-response.md)
9. [Business continuity and disaster recovery](docs/09-business-continuity-dr.md)
10. [Evidence collection and audit readiness](docs/10-evidence-collection.md)
11. [Life sciences specific considerations](docs/11-life-sciences-considerations.md)
12. [Choosing an auditor and preparing for fieldwork](docs/12-audit-prep-and-auditor-selection.md)
13. [Staying compliant after the report](docs/13-continuous-compliance.md)

## Templates

- [Access Control Policy](templates/policies/access-control-policy.md)
- [Incident Response Policy](templates/policies/incident-response-policy.md)
- [Vendor Risk Management Policy](templates/policies/vendor-risk-management-policy.md)
- [Evidence Collection Tracker](templates/trackers/evidence-tracker.md)
- [RACI Matrix](templates/trackers/raci-matrix.md)

## Status

The core guide is complete. All thirteen sections, the three policy templates, and both tracker templates are fully written and ready to use. Feedback and pull requests are still very welcome, this guide will keep improving as readers point out where it doesn't match what they actually experienced.

## License and contributions

Released under [MIT License](LICENSE). Issues and pull requests are welcome. If something here doesn't match what you experienced during your own audit, open an issue and tell me why.

## About

Written by Jermal Smith, an IT leader and security champion with over a decade of hands-on experience building and running security compliance programs inside life sciences organizations. Jermal was a founding member of his organization's corporate security compliance function and served as the incident handling focal point, the person responsible when something actually happened, not just when a policy needed a signature.

Over that decade, the programs he built and led carried the organization through repeated SOC 2 Type II audits with zero findings, controls that were designed to be enforced, not just documented, and evidence that held up because the practices behind it were real. This guide exists because most SOC 2 content available publicly is written by consultants and vendors who have never actually sat across from an auditor defending a control they built themselves. Jermal has, for ten years running, and wanted the people doing this work for the first time to have something written by someone who has actually lived it.
