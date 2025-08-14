# 📨 Phishing Incident Playbook (Template)

## 1) Purpose & Scope
Standard steps to triage and respond to suspected phishing emails targeting end users.

## 2) Detection Signals
- User-reported suspicious email (helpdesk, phishing mailbox)
- SIEM alerts: mass “Report Phish”, unusual login after email open, OAuth grant prompts

## 3) Triage (First 15–30 min)
- Capture headers; check **SPF/DKIM/DMARC** results
- Inspect sender display vs. envelope-from; domain age; look-alike domains
- Hover URLs; expand with a safe redirector; check against threat intel
- Review attachments (do **not** open) → hash, detonate in sandbox if available
- Identify affected recipients (message trace)

## 4) Containment
- Block sender/domain/IP; quarantine matching emails tenant-wide
- Revoke malicious OAuth app consents
- Force password reset + session revoke for any clicked/compromised accounts

## 5) Eradication & Recovery
- Remove artifacts (rules, forwarding, inbox filters)
- EDR scan on endpoints that opened attachments/links

## 6) Evidence to Preserve
- Raw `.eml` with full headers
- URL list + final resolves, file hashes, sandbox reports
- SIEM timeline: first seen, recipients, actions taken

## 7) Communication
- Notify affected users with guidance (don’t click; report future phish)
- Brief stakeholders with summary + impact + actions

## 8) Post-Incident
- Add IOCs to blocklists; update detection rules
- Awareness reminder or targeted training if needed
- Lessons learned: what worked, what to improve

---
**Owner:** Waqas Ali Khan · **Version:** 0.1 (draft)
