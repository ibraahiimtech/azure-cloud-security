# Month 3 · Day 4 — Defender for Cloud

**Platform:** Azure Portal (portal.azure.com) -> Defender for Cloud
**Focus:** The security dashboard for your WHOLE cloud — read its score and fix-list.

## What it is
Your cloud has lots of resources (VMs, storage, databases). Any can be set up badly
and become a way in. Defender for Cloud is the dashboard that watches all of it —
one screen: what's weak, how bad, how to fix.
(Session 2's Identity Secure Score checked USERS. This checks the WHOLE cloud.)

## Its two jobs
1. Find weaknesses (FREE) — scans for bad setups: storage open to the internet,
   risky ports exposed, no encryption, missing MFA. Gives a ranked fix-list.
   (Technical name: CSPM — Cloud Security Posture Management.) Today's focus.
2. Catch attacks (PAID) — like an alarm; spots live attacks (brute-force, malware)
   and raises alerts. (Technical name: CWP — Cloud Workload Protection.)
Remember: job 1 = find weak spots, job 2 = catch live attacks.

## Secure Score
One percentage = how secure the whole cloud is. Higher = better. Fix weaknesses ->
score rises. Useful because it's a quick health-check number PLUS a ranked to-do
list underneath. Handed a new cloud? Open this, read the score, work the list.

## Recommendations (the fix-list)
Each item has: severity (High/Medium/Low) · what's wrong (plain English) · how to
fix (often a Fix button) · points it adds to the score.
Shown as a colour bar: Orange = High, Yellow = Medium, Blue = Low.
Work left to right — fix High first (most dangerous), then Medium, then Low.

## Hands-on done (live, free tier)
Opened Defender for Cloud. Cloud was empty (fresh account):
- 1 Azure subscription · 0 assessed resources · 0 alerts · 0 attack paths
- "All recommendations by risk": High 0 | Medium 0 | Low 0 (the ranked fix-list,
  empty because nothing is deployed to check).

## KEY READING LESSON
0 recommendations + 0 assessed resources != "secure." It means Defender isn't
watching anything yet. An empty dashboard is NOT a safe dashboard — a real analyst
asks "why are no resources being assessed?" rather than assuming all is well. The
"limited information / tenant-wide visibility" banner is normal on a free account.

## Key takeaways
1. Defender for Cloud = one dashboard watching the whole cloud's security posture.
2. Two jobs: find weaknesses (free) vs catch live attacks (paid).
3. Secure Score = one health number + a ranked fix-list; the analyst's first check.
4. Recommendations are ranked High -> Medium -> Low; fix the worst first.
5. An empty dashboard means "not watching," not "safe."

MITRE ATT&CK (cloud posture): supports defending against T1190 (Exploit Public-
Facing App), T1078 (Valid Accounts), T1526 (Cloud Service Discovery).
