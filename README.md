# Tracker.md
This is a list of links tracking my personal cyber Community contributions 

CVE-2026-34916-RCE revive-adserver
CVE-2026-34917-Improper Authentication revive-adserver



CVE-2026-8327 . Prior to the fix, Concrete CMS was vulnerable to password change without reauthorization and session-hardening bypass. The user-profile edit controller passed the entire raw POST array to UserInfo::update() without field whitelisting, allowing password changes without requiring the current password and while also enabling registered users to disable the per-user IP-pinning in the session validator intended to detect hijacking. The Concrete CMS security team gave this vulnerability a CVSS v.4.0 score of 5.3 with vector CVSS:4.0/AV:N/AC:L/AT:N/PR:L/UI:N/VC:N/VI:L/VA:N/SC:N/SI:N/SA:N. Thanks 0x4c616e for reporting H1 3636712.

CVE-2026-7887 . Prior to the fix, Concrete CMS OAuth 2.0 Authorization-Code Handler bypassed account status checks. A user with uIsActive=0 (suspended, banned, or terminated) could still authenticate via OAuth and receive valid API tokens. The Concrete CMS security team gave this vulnerability a CVSS v.4.0 score of 2.3 with vector CVSS:4.0/AV:N/AC:L/AT:P/PR:L/UI:N/VC:L/VI:L/VA:N/SC:L/SI:L/SA:N. Thanks 0x4c616e for reporting H1 3636728.

CVE-2026-7890-Fixed CVE-2026-7890 Prior to the fix, the RSS Displayer block accepted a feed URL from any page editor and fetched it server-side without validation, enabling redirect-to-internal bypasses. The Concrete CMS security team gave this vulnerability a CVSS v.4.0 score of 2.1 with vector CVSS:4.0/AV:N/AC:L/AT:P/PR:H/UI:N/VC:N/VI:L/VA:N/SC:L/SI:N/SA:N. Thanks 0x4c616e for reporting H1 3636720.


https://www.revive-adserver.com/security/revive-sa-2026-002/

========================================================================
Remote Code Execution
========================================================================
Vulnerability Type: CWE-94: Code Injection
CVE-ID: CVE-2026-34916
Risk level: High
CVSS Base Score: 8.8
CVSS Vector: CVSS:3.0/AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H
========================================================================

Description
———–
HackerOne community member 0x4c616e has reported a missing validation of user input when saving delivery limitations in Revive Adserver 6.0.6 and earlier. A low‑privileged user could use the logical parameter to inject malicious PHP code into the `compiledlimitations` field, which would then be executed during banner delivery.

Resolution
———-
Input sanitisation has been improved to ensure that the parameter is properly validated.

References
———-
https://hackerone.com/reports/3656781
https://github.com/revive-adserver/revive-adserver/commit/de3525e12
https://cwe.mitre.org/data/definitions/94.html


========================================================================
6. Improper Authentication
========================================================================
Vulnerability Type: CWE-287: Improper Authentication
CVE-ID: CVE-2026-34917
Risk level: Medium
CVSS Base Score: 4.3
CVSS Vector: CVSS:3.0/AV:N/AC:L/PR:L/UI:N/S:U/C:L/I:N/A:N
========================================================================

Description
———–
HackerOne community member 0x4c616e has reported that low‑privileged session IDs generated for the web admin console could be reused in the XML‑RPC API, whose authentication is normally restricted to admin users. An attacker could leverage this to gain unauthorised access and exploit API‑level vulnerabilities.

Resolution
———-
The session context (web/API) is now recorded along with other session data, preventing session IDs from being used interchangeably.

References
———-
https://hackerone.com/reports/3672641
https://github.com/revive-adserver/revive-adserver/commit/50c7dd3ba
https://cwe.mitre.org/data/definitions/287.html


Link:https://documentation.concretecms.org/9-x/developers/introduction/version-history/951-release-notes
