# Week 12 public sample Endpoint Forensics Deep Dive

**Adapted from:** Final Assignment Book v2, Fall 2026 edition, Week 12  
**Author:** Dr. Atdhe Buja  
**Public adaptation:** October 2026

## Objective

Investigate Windows and Linux endpoint activity, correlate events, build a timeline, and explain whether the evidence supports a benign explanation, suspicious activity, or escalation.

## Two ways to use this sample

**Offline review:** Analyze the synthetic CSV files in this directory. They are simplified teaching tables, not native Velociraptor exports. They can be opened without SOC platform access.

**Authorized lab collection:** Use Velociraptor to collect event logs, process details, and startup/persistence evidence on an instructor-approved Windows endpoint; collect processes and authentication logs on an approved Linux endpoint. Select only those targets and an agreed exercise time window. Confirm artifact names and parameters in the installed version before collection.

The original manual names Windows.EventLogs.Evtx, Windows.Memory.ProcessInfo, Windows.Sysinternals.Autoruns, Linux.Sys.Processes, and Linux.Forensics.AuthLogs as examples. Availability and parameters must be checked locally; these names are not promised as a universally working configuration.

## Scenario

A routine update and unusual temporary-directory activity appear on WIN-LAB-01. LIN-LAB-01 records unsuccessful SSH logins followed by a successful login and temporary-path execution. Determine what the records establish and what remains uncertain. All users, hosts, timestamps, and addresses in the fixtures are fictional.

## Student tasks

1. Preserve the supplied evidence files and compute SHA-256 hashes before analysis.
2. Review `windows-events.csv` and `linux-events.csv`. Sort events in UTC and record a source row/event ID for each finding.
3. Compare expected administrative activity with the unusual process, task, authentication, and temporary-path records.
4. Build a combined timeline. Do not assume Windows and Linux records prove the same actor or campaign.
5. Map only supported behaviors to ATT&CK, such as PowerShell execution or a scheduled task. Identify evidence needed before asserting compromise.
6. Write a case summary in TheHive if available, or use the [report template](../../templates/incident-report.md).
7. Recommend a proportionate next action and identify limitations of the supplied evidence.

## Deliverables

- Evidence inventory and hashes.
- Timeline with evidence references.
- Windows and Linux findings, including plausible benign explanations.
- Classification and escalation recommendation with rationale.
- ATT&CK mappings with supporting records.
- A report and redacted screenshots if working in the live educational lab.

## Assessment questions

What distinguishes execution from persistence? Does a successful login prove account compromise? What missing context would change your assessment? What can a simplified fixture show that a live collection must verify?

## Fixture limitations

The fixtures intentionally include ambiguity and no malware payload. Synthetic evidence does not establish historical student performance or successful deployment of the lab. Instructor review guidance is in [sample validation notes](../../docs/sample-validation-notes.md).
