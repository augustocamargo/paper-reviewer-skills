---
name: paper-security-ethics-safety
description: >
  Audit CS/AI papers for security, privacy, ethics, safety, misuse, human-subject
  risk, data licensing, consent, personally identifiable information, dual use,
  and responsible-release issues. Use for AI, data, security, web, biomedical,
  user-study, scraping, or deployment-facing papers.
---

# Security, ethics, privacy & safety audit

## Risk inventory
Check whether the paper involves: human subjects, user data, scraped data,
private logs, biomedical/clinical data, minors, biometric data, geolocation,
security exploits, malware, dual-use models, persuasive systems, surveillance,
or model outputs that can cause harm.

## Required checks
1. **Data rights.** Dataset source, license, consent, redistribution permission,
   terms-of-service constraints, and citation requirements.
2. **PII/privacy.** Collection, storage, anonymization, de-identification limits,
   retention, access control, and whether examples leak identities.
3. **IRB/ethics.** Approval/exemption ID where required; consent and participant
   compensation for user studies.
4. **Dual use.** Misuse pathways, threat model, release choices, safeguards, and
   why benefits justify disclosure.
5. **Security claims.** Define attacker capability, trust assumptions, assets,
   threat model, baselines, and failure modes. Do not let "secure", "private",
   or "safe" stand without an adversary and evidence.
6. **Model safety.** For generative AI, check hallucination, toxicity, bias,
   jailbreaks, sensitive inference, memorization, and deployment limitations.
7. **Responsible artifact release.** Decide whether to release full code/data,
   redacted data, synthetic examples, a gated artifact, or only scripts.

## Output
- Risk table: `risk area | present? | current statement | gap | severity`.
- Draft ethics/privacy/safety paragraph when the needed facts are present.
- Claims requiring downgrade: secure/private/fair/safe/anonymous/consented.
- Release recommendation: open / redacted / gated / delayed / do not release,
  with reason.
