# Fictional SOC Notes: Email Authentication Checks

## Purpose
These original teaching notes explain how a fictional SOC uses email-authentication signals during suspicious-message review. Authentication indicates whether sending infrastructure and signed content meet defined checks; it does not by itself prove the intent of a sender.

## SPF
Sender Policy Framework (SPF) checks whether the sending server is authorized by a domain's published policy for an envelope sender identity. An SPF pass is evidence about authorization of the sending infrastructure, not proof that a human sender can be trusted. Forwarding may complicate SPF interpretation. Analysts note both the result and the identity to which the SPF check applies.

## DKIM
DomainKeys Identified Mail (DKIM) uses a cryptographic signature to verify that selected message content was signed by an entity controlling the corresponding domain key. A valid DKIM signature does not guarantee a message is safe. Analysts record the signing domain and whether verification passed, failed, or was unavailable. A failed signature can have benign explanations, such as content modification, so it should be interpreted alongside other evidence.

## DMARC
Domain-based Message Authentication, Reporting, and Conformance (DMARC) combines alignment requirements with SPF and/or DKIM results and a published domain policy. DMARC evaluates whether authenticated identifiers align with the visible From domain. The three commonly discussed policy dispositions are none, quarantine, and reject. The policy requested by a domain and the action actually taken by a receiving system can differ. Analysts should inspect the results rather than assuming that a policy guarantees delivery behavior.

## Practical investigation workflow
In the fictional case record, analysts record SPF result, DKIM result, DMARC result, and the domain identities involved. Compare those details against sender reputation, message content, lookalike spelling, and employee interaction. A message with all authentication checks passing may still contain a malicious link from a compromised legitimate account. A message that fails one check is not automatically malicious without context.

## Escalation and reporting
If authentication anomalies appear alongside credential-harvesting indicators, route the case to phishing triage for prioritization. If the user already entered a password, initiate the incident-response workflow regardless of whether DMARC passed. Store only sanitized message examples in learning materials. An analyst's written conclusion should state which checks were performed and why the outcome is supported by the evidence.
