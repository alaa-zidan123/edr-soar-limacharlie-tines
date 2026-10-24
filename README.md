# EDR-SOAR Automation with LimaCharlie, Tines, and Slack

## Overview
This project automates endpoint detection and response using LimaCharlie, Tines, and Slack. It detects suspicious Windows processes associated with LaZagne, sends alerts for analyst review, and supports automated endpoint isolation with status verification.

## Tools
- **LimaCharlie:** Endpoint detection and isolation.
- **Tines:** SOAR workflow automation.
- **Slack:** Security alerts and analyst approval.
- **Webhooks & HTTP APIs:** Integration and response automation.

## Workflow
1. **Detection:** LimaCharlie identifies suspicious Windows process activity.
2. **Alerting:** Tines forwards alerts to Slack.
3. **Approval:** The analyst decides whether to isolate the endpoint.
4. **Response:** Tines requests endpoint isolation through LimaCharlie.
5. **Verification:** The workflow retrieves the isolation status and sends a follow-up notification.

## Detection Rule
The `lazagne-detection.yml` rule monitors Windows process events and matches configured indicators:
- File path ending in `\lazagne.exe`.
- Command line ending in `all` or containing `lazagne`.
- Specified SHA-256 hash.

Detection matches require further investigation before taking action.

## Repository Structure
```text
edr-soar-limacharlie-tines/
├── README.md
├── edr-soar.json
├── lazagne-detection.yml
└── docs/
    ├── tines.png
    └── limacharlie (2).png
```
