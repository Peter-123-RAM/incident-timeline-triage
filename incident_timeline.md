Incident Timeline Report

Scope

Data Sources:

- Linux auth.log
- Sysmon Host Logs
- HTTP Access Logs

Analysis Period:
24 Hours (UTC)

Objective:
Identify suspicious activity, classify events, and provide actionable alerts for a Tier-1 SOC analyst.

---

Chronological Timeline

UTC Time| Log Source| Event| Classification| Evidence
08:15:04| auth.log| Failed SSH login for invalid user admin| Suspicious| Failed password for invalid user admin
08:15:20| auth.log| Additional failed SSH attempts| Suspicious| Same IP generated multiple failures
08:16:02| auth.log| Successful SSH login| Suspicious| Success immediately after failures
08:18:40| Sysmon EID 1| powershell.exe executed with EncodedCommand| Suspicious| EncodedCommand parameter present
08:20:10| access.log| GET /admin.php returned 404| Suspicious| Sensitive path request
08:20:18| access.log| GET /phpmyadmin returned 404| Suspicious| Enumeration behavior
08:20:31| access.log| GET /wp-admin returned 404| Suspicious| Enumeration behavior
09:00:00| auth.log| Backup account login| Benign| Expected scheduled task

---

Findings

Finding 1: SSH Brute Force Followed by Access

Classification: Suspicious

Reasoning:
Multiple failed passwords followed by a successful login from the same IP.

---

Finding 2: Web Directory Enumeration

Classification: Suspicious

Reasoning:
Requests for common administrative paths indicate reconnaissance.

---

Finding 3: Scheduled Backup Activity

Classification: Benign

Reasoning:
Occurs at the same time daily using a known service account.

---

What I Would Alert On

1. More than 10 failed SSH logins from one IP within 5 minutes.
2. Successful SSH login after repeated failures.
3. PowerShell launched with EncodedCommand.
4. Requests for phpMyAdmin or wp-admin paths.
5. More than 20 HTTP 404 responses from one IP within 5 minutes.
6. New administrator account creation.
7. Privileged process execution from unusual parent processes.

---

Conclusion

The highest-risk activity observed was an SSH brute-force sequence followed by successful authentication and suspicious PowerShell execution. These events warrant investigation and containment.
