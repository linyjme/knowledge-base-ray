---
id: RSKB-SECURITY-004
title: Resolve network and malicious-IP login restrictions
product: raysync
components:
- user-portal
domain: security
access_level: public
audience:
- end-user
locale: en
applicable_versions:
  from: 8.1.8.7
  to: null
version_status: current
status: active
question_variants:
- Why is login blocked from my current network address?
- What does a malicious-IP blacklist mean for an end user?
- Who can review an IP restriction that prevents portal access?
keywords:
- malicious IP
- blacklist
- login restriction
- blocked IP
- 8.1.8.4
- Why was my IP blocked as malicious when I tried to log in?
- IP restriction
- whitelist
legacy_ids:
- FAQ-SECURITY-009
safety_tags:
- credentials
- sensitive-diagnostics
supersedes: []
superseded_by: []
related_articles: []
source_refs:
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-010 | Why was my IP blocked as malicious when I tried to log in?
  evidence_type: generated-faq
- file: raysync-user-faq/09-security-and-authentication.md
  section: FAQ-SECURITY-009 | Why can I log in from one network but not another?
  evidence_type: generated-faq
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-113 | IP black and white list for login
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-122 | Malicious IP Login Restriction Policy
  evidence_type: feature-matrix
- file: Raysync_Product_Edition_Feature_Knowledge_Base_EN.md
  section: RS-FEAT-112 | Set the IP black and white list for space access
  evidence_type: feature-matrix
verification:
  state: verified
  version: 8.1.8.7
  date: '2026-08-14'
  verified_by: documentation-review
---

# Resolve network and malicious-IP login restrictions

## Short answer

Your current public or internal IP may be outside an allowed list or inside a blocked list. Raysync supports a whitelist, where only listed IPs may log in to the user portal, and a blacklist, where listed IPs may not log in. Later login settings can also restrict IP login, and multi-factor verification can vary by listed IP.

## Version differences

Both legacy and later guides document IP allowlists and blocklists. The later guide additionally documents an IP-login restriction and IP-based scope for multi-factor verification. These controls remain administrator-managed prerequisites rather than end-user network settings.

## Important notes

Try only an organization-approved network or VPN; do not attempt to evade the policy. If access should be permitted, give the administrator the time of the attempt and the network/IP information your organization allows you to share. Only an administrator can change the lists.

Email or Authenticator App verification prompts may also vary because later multi-factor policies can use IP lists.

## Related documented boundaries

- **Why was my IP blocked as malicious when I tried to log in?:** Raysync 8.1.8.4 introduced a malicious-IP login restriction policy. If the service blocks your address, stop repeated login attempts and contact the administrator. The release documentation also records an email alert to administrators when an address is added to the malicious-IP blacklist.
- **IP black and white list for login:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
- **Malicious IP Login Restriction Policy:** SMB: Supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Not supported The source records 8.1.8.4 as an appearance or change milestone, not as proof of the onset of support.
- **Set the IP black and white list for space access:** SMB: Not supported; Enterprise: Supported; Cloud: Supported; Multiple Spaces: Supported
