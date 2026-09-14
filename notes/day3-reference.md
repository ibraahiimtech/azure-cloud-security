# Month 3 · Day 3 — Conditional Access

**Platform:** Microsoft Entra admin center (entra.microsoft.com)
**Focus:** Smart, situation-aware access rules — MFA and blocking, but only when it
makes sense.
**Note:** Concepts + guided walkthrough complete. Live hands-on deferred —
Conditional Access and Named locations require Entra ID P1/P2 (not on free tier).

## The big idea
Basic MFA is blunt: it asks everyone for a second factor every time. Conditional
Access makes it smart — it looks at the situation of each login and decides what to
require. Access is conditional: it depends on conditions.

Bouncer analogy: a dumb door checks "got a ticket?" for everyone. A smart bouncer
sizes up who you are, where you came from, what you're carrying, how you're acting —
then decides: let in, ask for extra ID, or refuse.

## Every policy is an IF ... THEN rule

IF (Assignments / conditions):
- Users — who it applies to (all, or a group). Has an Exclude option — always
  exclude a break-glass admin.
- Target resources — which apps (all, or specific).
- Conditions — the situation:
  - Locations (uses Named locations — e.g. include "any" except "UK")
  - Device platforms (iOS/Android/Windows)
  - Sign-in / user risk (Azure's suspicion score — needs P2)
  - Client apps (browser vs legacy protocols)

THEN (Access controls):
- Grant — Block access, OR Grant with requirements:
  - Require MFA (the common one)
  - Require compliant / trusted device
  - (can require several at once)
- Session — session length / limits (advanced, optional)

## Real example rules
1. IF login from outside the UK -> THEN require MFA.
2. IF user is an admin -> THEN always require MFA (admins = top targets).
3. IF login from a country we never do business with -> THEN block entirely.
4. IF device is not a trusted company laptop -> THEN require MFA.

## Example policy (the one we designed)
- Name: Require MFA from outside UK
- IF: all users (except break-glass admin), all cloud apps, any location except UK
- THEN: grant access but require MFA
- Mode: Report-only (test first)

## The safety rule (same as Month 1 "never lock yourself out")
Conditional Access is powerful, so a bad policy can lock you out of your own tenant.
Two protections, one idea — leave a safe way out and test before enforcing:
1. Exclude a break-glass admin account — an emergency account the policy never
   touches, so a broken rule can't trap you out. (Like a spare key hidden outside.)
2. Start in report-only mode — the policy logs what it WOULD do without enforcing.
   Run it a few days, check sign-in logs, confirm nothing breaks, THEN turn it On.
   (Same "verify before enforce" as sshd -t and fail2ban testing in Month 1.)

## Licensing lesson (real-world)
Conditional Access and Named locations need Entra ID P1; risk-based conditions need
P2. The free tier blocks them. A free P2 trial (30 days, no charge) unlocks them for
real hands-on. Knowing product tiers is itself interview-relevant.

## Key takeaways
1. Conditional Access = MFA/blocking made smart — decisions based on the situation.
2. Every policy is IF (who/where/device/app/risk) THEN (allow/MFA/block).
3. Named locations define the "where" (countries or IP ranges) policies reference.
4. Exclude a break-glass admin + use report-only mode — never lock yourself out.
5. It needs P1/P2 licensing — a real constraint cloud analysts work around.

MITRE ATT&CK (cloud): defends against T1078 (Valid Accounts), T1133 (External Remote
Services), T1556 (Modify Authentication Process); enforces Zero Trust access.
