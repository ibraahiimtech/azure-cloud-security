# Month 3 · Day 5 — Secure Baselines + Review

**Platform:** Azure Portal (portal.azure.com) -> Policy
**Focus:** Locking a cloud to a known-good standard — and the whole Month 3 picture.

## What a secure baseline is
A known-good starting point — security settings every cloud SHOULD have on from day
one. Like a plane's pre-flight checklist: same checks, every time, no exceptions.
(Same idea as Month 1 Day 5 Linux hardening — now for the cloud.)
Why: attackers find the ONE thing someone forgot. A baseline means nothing gets
forgotten — every cloud starts from the same safe standard.

## How baselines work in Azure
- Azure Policy = the rules ("all storage must have encryption"). Automatically
  blocks or flags anything that breaks a rule.
- Microsoft Cloud Security Benchmark = Microsoft's ready-made checklist of
  recommended settings (the baseline itself).
- Defender for Cloud = the scorecard showing how well you follow the benchmark
  (that's where the Secure Score comes from).
Simple: Policy = the rules · Benchmark = the recommended list · Defender = the score.

## Hands-on done (live, free tier)
Opened Azure Portal -> Policy. Policy Compliance donut showed:
- 217 total checks (from the Microsoft Cloud Security Benchmark)
- 196 Compliant (green) · 21 Non-compliant (red) ~= 90% compliant
Reading it: the 21 red = the to-do list (baseline rules not met = weak spots). Work
them down toward zero, same as the Defender High->Medium->Low fix-list. Policy and
Defender are two windows on the same question: "does this cloud follow the safe standard?"

## MONTH 3 REVIEW — how it all connects
Every session is a layer protecting identity + the cloud:
- S1 Entra ID — the guest list (who exists)
- S2 MFA — a second lock (proving it's really you) — blocks 99%+ of takeovers
- S3 Conditional Access — the smart bouncer (rules for WHEN to challenge)
- S4 Defender for Cloud — the dashboard (what's weak across everything)
- S5 Baselines — the safe standard (nothing left weak by accident)

The one big idea: IDENTITY IS THE NEW PERIMETER. In the cloud the login page is the
wall, so: lock the door (MFA, Conditional Access), watch the house (Defender),
follow the safety checklist every time (baselines).

## Key takeaways
1. A secure baseline = a known-good standard applied to every cloud, every time.
2. Azure Policy enforces rules (blocks/flags); the Benchmark is the rule list.
3. Policy compliance % and Defender Secure Score both answer "how well does this
   cloud follow the safe standard?" — the non-compliant items are the fix-list.
4. Month 3 in one line: identity is the new perimeter — protect it hardest.

MITRE ATT&CK (cloud posture): baseline enforcement defends against T1078 (Valid
Accounts), T1190 (Exploit Public-Facing App), T1526 (Cloud Service Discovery).
