# Cybersecurity: Threat Analysis & Incident Response

## Prompt 1 — Log Analysis & IOC Extraction

**Best with**: Claude, GPT-4, Gemini

```
You are a senior SOC analyst performing triage on a potential security incident. I will provide you with raw log data.

Your task:
1. Identify all Indicators of Compromise (IOCs): suspicious IPs, domains, file hashes, user agents, unusual ports
2. Map observed activity to MITRE ATT&CK techniques where possible
3. Establish a timeline of events in chronological order
4. Assess severity (Critical / High / Medium / Low) with justification
5. Recommend immediate containment actions

Output format: structured markdown with sections for each step above. Use tables for IOCs and timeline.

Logs:
[PASTE LOGS HERE]
```

**Why it works**: Role assignment ("senior SOC analyst") + structured output format + specific enumerated tasks prevents the model from giving generic advice. The MITRE ATT&CK mapping forces it to think systematically about attack patterns rather than surface-level observations.

**Variations**:
- Replace "SOC analyst" with "threat hunter" for more proactive analysis
- Add "Compare against known APT group TTPs" for attribution-style analysis
- Add "Assume the attacker has already achieved persistence" for worst-case scenario analysis

---

## Prompt 2 — Vulnerability Assessment from Code

**Best with**: Claude, GPT-4 (models with strong code understanding)

```
You are a senior application security engineer conducting a code review. Analyze the following code for security vulnerabilities.

For each vulnerability found:
- Vulnerability type (e.g., SQLi, XSS, IDOR, SSRF, path traversal)
- CWE ID if applicable
- Exact line(s) affected
- Severity (Critical/High/Medium/Low) using CVSS-like reasoning
- Proof of concept: show how an attacker would exploit it
- Fix: provide the corrected code snippet

If no vulnerabilities are found, explain what security controls are properly implemented.

Do NOT flag style issues or non-security bugs. Focus exclusively on exploitable security weaknesses.

Code:
[PASTE CODE HERE]
```

**Why it works**: Constraining to "exploitable security weaknesses" and explicitly excluding style issues prevents false positives. Asking for PoC forces the model to verify the vulnerability is real, not theoretical. CWE IDs anchor the response to established vulnerability taxonomies.

**Variations**:
- Add "Also check for hardcoded secrets, API keys, or credentials" for secret scanning
- Add "Consider the context: this runs as a public-facing API with unauthenticated access" for threat modeling
- Swap "application security engineer" for "red team operator" for more offensive-minded analysis
