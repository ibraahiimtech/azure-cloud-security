# Month 3 · Day 2 — Authentication & MFA

**Platform:** Microsoft Entra admin center (entra.microsoft.com)
**Focus:** Proving identity, why passwords alone are weak, and MFA — the #1 cloud
security control.

## The big idea
Authentication = proving your claimed identity is true. When you log in you claim
"I'm X"; authentication is the check that it's really you. It can use one factor
(just a password) or several (MFA).

## The three factors
1. Something you KNOW — password, PIN (a secret in your head)
2. Something you HAVE — phone, security key (a physical thing)
3. Something you ARE — fingerprint, face (your body)
A password is just ONE factor — that's the weakness.

## Why passwords alone are weak
Identity is the new perimeter, so the login page is the wall — and a password-only
wall is thin. Passwords get stolen (phishing, malware, breaches), guessed
(brute-force, Month 1), and reused across sites (one leak unlocks everything).

## MFA = the fix
Multi-Factor Authentication = requiring TWO+ of the three factors. Most common:
password (know) + phone approval/code (have). The power: an attacker may steal your
password, but they don't have your phone — so they're stuck at the second check.
MFA blocks 99%+ of account-takeover attacks. It is the single most effective cloud
identity control. If you do one thing: turn on MFA.

## Common second factors
- Microsoft Authenticator app — approve a notification / rotating code (best)
- SMS text code — works, weaker (texts can be intercepted)
- Voice call — automated approval call
- FIDO2 / passkey — physical or device key, very strong

## Where MFA lives in Azure
- Security Defaults — one-click on/off that forces basic MFA for everyone. Often ON
  by default on new tenants. Enforces MFA even if the Authentication methods page
  shows methods "disabled" (the two systems don't always visibly agree).
- Per-user MFA — turn on for specific accounts.
- Conditional Access (Day 3) — advanced: require MFA only in risky situations.

## Hands-on done (live tenant)
1. Security menu -> Authentication methods: all methods showed disabled
   (Passkey/FIDO2, Microsoft Authenticator, SMS, Temporary Access Pass, Hardware
   OATH) — the modern per-method controls were all off.
2. Security menu -> Identity Secure Score: the tenant's security "report card."
   - Score: 68%
   - Ranked recommendations: Completed (do-not-expire passwords 8/8, password hash
     sync 5/5) and Active (block risky app consent 0/4, least-privileged admin
     roles 0/1, designate 2+ global admins 0/1).
   - No explicit "Require MFA" recommendation -> strong sign Security Defaults is ON
     and already enforcing MFA (Microsoft hides that nag when it's handled).

## The analyst move (interview-ready)
"To assess a tenant's posture, open the Identity Secure Score, read the ranked
recommendations, and prioritise high-value Active items — MFA enforcement, blocking
risky app consent, least-privilege admin." First thing a cloud SOC analyst checks.

## Key takeaways
1. Authentication = the proving step; MFA = proving with 2+ factors.
2. Three factors: know / have / are. A password is only one.
3. Passwords alone are weak — stolen, guessed, reused.
4. MFA blocks 99%+ of account takeovers — the #1 cloud control.
5. Two MFA systems in Azure (Security Defaults vs Authentication methods) can look
   like they disagree — Security Defaults can enforce MFA even when the methods
   page shows "disabled."
6. Identity Secure Score = the tenant report card; the analyst's first check.

MITRE ATT&CK (cloud): defends against T1110 (Brute Force), T1078 (Valid Accounts),
T1621 (MFA Request Generation), T1556.006 (Modify Auth Process: MFA).
