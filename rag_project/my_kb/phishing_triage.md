# Fictional SOC Runbook: Phishing Email Triage

## Purpose and scope
This runbook is an original educational simulation for a fictional small security operations center (SOC). It defines how analysts should handle employee-reported suspicious messages. It is not an employer policy, and all cases are synthetic. The SOC must preserve evidence, avoid opening unsafe links, and route confirmed compromise indicators for incident response.

## Intake and case creation
When an employee reports a suspicious email, the analyst creates a case using the report timestamp and a unique case identifier. The analyst should preserve the original message and its headers where approved. The analyst records the sender domain, reply-to address, and authentication results before deciding how to classify the report. Additional intake notes include the recipient, subject, observed delivery time, and whether the reporter interacted with a link or attachment. Reporting employees should not be blamed for asking for help.

## Header and sender review
Compare the display name with the actual sender address; they are not always the same. Look for unusual reply-to destinations, near-match domains, unexpected external senders, and urgent language. SPF, DKIM, and DMARC results can inform triage, but passing authentication alone does not establish that a message is benign. Analysts document both the outcome and any limitations of the checks.

## URL and attachment triage
Treat links and attachments as untrusted evidence. Copy URL strings for safe inspection through approved tools rather than opening suspicious pages in a normal browser session. When permitted, inspect URL redirects and reputation results in a controlled environment. Do not upload confidential documents or private customer data to public scanning services. If a malicious attachment is suspected, refer it to the malware-analysis procedure rather than executing it on an analyst workstation.

## Severity and escalation
Classify a message as informational, suspicious, or confirmed malicious based on documented indicators. If a user entered credentials or approved an unexpected sign-in prompt, escalate immediately to the incident response queue; do not wait for reputation results. A confirmed malicious campaign affecting multiple mailboxes should be escalated to the incident lead so they can coordinate scope and containment. A benign classification needs written reasoning, not simply an absence of alerts.

## Case closure
Before closing, record the classification, supporting indicators, actions taken, evidence locations, and any user notification. The closing analyst must record a short rationale explaining why the case was closed or escalated. If facts remain unresolved, mark the case pending and identify who owns the follow-up. Use only the fictional examples supplied with this teaching knowledge base.
