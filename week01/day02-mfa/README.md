# Day 02 — Authentication & MFA (browser-based, no local files)

Session 2 was done in the Entra admin center (entra.microsoft.com). No scripts or
captures — the work was configuration review in the browser.

What was done live:
- Security menu -> Authentication methods: checked which second factors were
  enabled (all showed disabled: Passkey/FIDO2, Microsoft Authenticator, SMS,
  Temporary Access Pass, Hardware OATH).
- Security menu -> Identity Secure Score: read the tenant's security report card.
  Score: 68%. Reviewed ranked recommendations (completed vs active items).
- Reasoned out the two-MFA-systems puzzle: Authentication methods showed "disabled"
  while Security Defaults was quietly enforcing MFA (no "Require MFA" nag in the
  Secure Score = strong sign Security Defaults is ON).

The learning artifact for this session is the reference card:
notes/day2-reference.md
