# Fictional SOC Runbook: Initial Incident Response

## Purpose and roles
This original training runbook describes a small fictional SOC's initial handling of suspected account compromise, malware, and suspicious endpoint activity. The incident lead coordinates decisions, the responding analyst documents actions, and the system owner confirms operational impact. The runbook intentionally does not specify a monetary incident budget or contractual notification deadlines.

## Detection and triage
On receiving an alert, open an incident record and capture the reporting source, affected account or host, observed time, and initial indicators. Verify whether the activity may be expected maintenance or a known false positive. Assign a preliminary severity using observed impact and scope rather than intuition alone. Document assumptions and missing facts so later analysts can audit the reasoning.

## Containment decision
If credible evidence suggests an account takeover, notify the incident lead and consider disabling active sessions or resetting credentials through approved administrative processes. Isolation of an endpoint must be coordinated with the system owner when it may affect critical business operations. Analysts must preserve available logs and relevant evidence before making changes when feasible. Containment should reduce ongoing harm without unnecessarily destroying forensic data.

## Evidence handling
Record a chronological timeline of observed events and response actions. Evidence entries should identify the collection time, source system, collector, and a protected storage location. Preserve relevant authentication logs, endpoint alerts, and related messages under the organization's approved retention rules. Do not paste real user credentials, private keys, or confidential customer data into the project repository or public services.

## Eradication and recovery
After containment, investigate the cause, remove persistence or unauthorized access through approved procedures, and verify that identified indicators no longer recur. The system owner approves service restoration and monitors for suspicious reappearance. A successful recovery requires both technical validation and a documented owner handoff. Avoid announcing full resolution solely because one detection alert disappeared.

## Closure and learning
Before an incident is marked resolved, the incident lead reviews the timeline, affected assets, containment actions, evidence references, and recovery validation. The team records at least one lesson learned and assigns any follow-up improvement to an owner. If the incident cannot be confirmed, the record should state the uncertainty and what additional evidence would change the classification.
