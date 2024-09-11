# Account-Lockout-Analysis-Custom-Analytical-Rule
IDENTIFYING ANOMALOUS LOCKOUT EVENTS  USING KUSTO QUERY LANGUAGE (KQL)

# Description
This Kusto Query Language (KQL) script is designed to analyze account lockout events (EventID 4740) over the last 5 working days, focusing on specific working hours (8 PM to 8 AM) in the US/Pacific time zone. The objective is to identify and highlight potential security anomalies where the frequency of lockouts exceeds the normal rate.

# Business Requirements
•	Reduce False Positives: By focusing on non-standard working hours and using a rolling average for anomaly detection, the system should minimize false positives and reduce alert fatigue for security teams.

•	Timely Alerts: The solution must ensure that security teams are alerted to abnormal lockout activities in near real-time, allowing for swift investigation and response.

•	Enhance Security Posture: The system should help the organization proactively detect and respond to potential security incidents, reducing the risk of unauthorized access.

# Prerequisites
•	An active Azure subscription

•	Contributor RBAC role assigned to a resource group

•	An active Sentinel workspace

•	A Log Analytics workspace linked to Sentinel

•	The SecurityEvent table must be populated with relevant log data, including EventID 4740 (Account Lockout events).

•	Ensure that at least 30 days of historical log data is available in the SecurityEvent table.

•	An alerting mechanism should be set up to notify the security team when the query detects abnormal lockout activities.

# MITRE ATT&CK
The following are the MITRE ATT&CK tactics and techniques associated with the analytical rule:

Credential Access

•	T1110 - Brute Force

Account lockouts are often a result of brute force attacks, where an adversary repeatedly attempts to guess a user's password until the account is locked.

Defense Evasion 

•	T1098 - Account Manipulation

Adversaries may intentionally lock user accounts as a means of disrupting normal operations or as part of a broader strategy to evade detection.

Persistence

•	T1078 – Valid Accounts

An adversary who has successfully obtained valid credentials may attempt to trigger account lockouts to mislead defenders or hinder the user's ability to access their account.

# Query Scheduling

•	Query Frequency: - Run query every 15 minutes

•	Query Lookup data: - Lookup data from the last 5 days.

# Output
![image](https://github.com/user-attachments/assets/1d181321-d96c-4e2f-b607-1392b8b0e7ab)

