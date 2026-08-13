# Month 3 · Day 1 — Cloud & Entra ID Basics

**Platform:** Microsoft Azure / Entra admin center (entra.microsoft.com)
**Focus:** What cloud identity is, and why it's the heart of cloud security.

## The big idea
The cloud = renting computers/storage/services over the internet instead of owning
them (Uber vs. owning a car). Microsoft's cloud is Azure.

On your own VM, security was about the machine. In the cloud, the machine is the
provider's problem — YOUR problem is identity: who can log in, and what can they do.

## Identity is the new perimeter
Old world: your data sat behind a network wall; attackers had to break through it.
Cloud world: your data is reachable from anywhere on the internet by design — so the
only thing between an attacker and your data is often just a username + password.
The login page IS the wall. That's why attackers target accounts in the cloud (steal
a password -> walk in), and why identity is where a cloud analyst spends most time.

## Entra ID — the cloud's guest list & front desk
Microsoft Entra ID (formerly Azure Active Directory / Azure AD, renamed 2023) is the
identity system. Its four jobs:
1. Holds all user accounts — everyone who can log in
2. Checks logins — verifies passwords, says "come in" or "no"
3. Manages groups — bundle users to assign permissions in bulk
4. Controls access to apps — who can open which cloud apps

If Month 1's /etc/passwd was the user list for ONE machine, Entra ID is the user list
for the ENTIRE cloud.

## Key words
- Tenant — your organisation's whole Entra ID space (your cloud "building")
- Directory — the list of all users/groups in your tenant
- User — one account (one person who can log in)
- Group — users bundled together to manage permissions easily
- Identity — who you are in the cloud (proven by logging in)

## Hands-on done (live tenant)
1. Signed into entra.microsoft.com, confirmed the tenant (the org's cloud space).
2. Viewed Users -> All users — the guest list (started with 1: the admin = me).
3. Created a user: + New user -> Create new user -> set User principal name
   (testuser@<domain>.onmicrosoft.com), display name, password. List went to 2.
4. Created a group: Groups -> + New group -> type Security, membership Assigned,
   name "Finance Team", added Test User as a member.
5. Confirmed the group shows Test User inside it.

Group types: Security = control access to resources. Microsoft 365 = collaboration.
Membership types: Assigned = pick members by hand. Dynamic = auto-add by rules.

## Key takeaways
1. Cloud = renting computing; the machine is the provider's problem, identity is yours.
2. Identity is the new perimeter — the login page is the wall; attackers target accounts.
3. Entra ID = the cloud's guest list + front desk: users, logins, groups, app access.
4. Tenant = your whole space · User = one login · Group = a bundle for permissions.
5. Every user/group is an identity = a potential way in -> next sessions PROTECT these
   (MFA, Conditional Access, monitoring).

MITRE ATT&CK (cloud): T1078 (Valid Accounts) · T1136 (Create Account) ·
T1098 (Account Manipulation).
