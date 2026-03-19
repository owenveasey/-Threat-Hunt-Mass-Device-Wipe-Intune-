# -Threat-Hunt-Mass-Device-Wipe-Intune-
This repository contains a collection of KQL (Kusto Query Language) and SIEM queries designed to detect advanced adversary behaviors. Each hunt is mapped to the MITRE ATT&CK Framework and includes a hypothesis, detection logic, and recommended SOC response.

1. Intune Mass Device Wipe
Goal: Detects "Stryker" style attacks where a compromised admin account attempts to brick the fleet.

Logic: Monitors IntuneAuditLogs for a high volume (5+) of Wipe, Retire, or Factory Reset commands within a 10-minute window.

Safety: Includes JSON parsing to identify targeted devices while maintaining a high-level summary for SOC triage.

2. "God-Mode" Role Assignment
Goal: Detects the moment a user is promoted to high-privilege roles like Global Administrator or Privileged Role Administrator.

Logic: Audits AuditLogs for specific role-addition operations targeting mission-critical permissions.

Visibility: Maps the Target User, the Role Granted, and the Admin who authorized the change.
