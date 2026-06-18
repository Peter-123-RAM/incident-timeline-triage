Incident Timeline Triage

Overview

This project analyzes 24 hours of Linux authentication logs, Sysmon host logs, and HTTP access logs to build a defensible incident timeline.

The objective is to identify suspicious activity, classify findings as benign or suspicious, and provide actionable alert recommendations for a Tier-1 SOC analyst.

Deliverables

- incident_timeline.md
- incident_timeline.pdf
- sample_logs/

Data Sources

- Linux auth.log
- Sysmon Host Logs
- HTTP Access Logs

Key Findings

- SSH brute-force activity followed by successful authentication.
- Suspicious PowerShell execution with encoded commands.
- Web directory enumeration targeting administrative interfaces.
- Benign scheduled backup activity correctly identified and excluded from escalation.

Outcome

The final report provides:

- Chronological UTC timeline
- Source log citations
- Event classification
- Investigation reasoning
- Recommended detection rules
