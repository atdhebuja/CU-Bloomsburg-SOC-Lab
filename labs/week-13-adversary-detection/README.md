# Week 13 public sample Adversary Emulation and Detection Pipeline

**Adapted from:** Final Assignment Book v2, Fall 2026 edition, Week 13  
**Author:** Dr. Atdhe Buja  
**Public adaptation:** October 2026

## Objective

Compare controlled lab behavior with SIEM evidence, justify ATT&CK mappings, distinguish event visibility from alerting, and explain a detection gap.

## Offline route

Use `operation-records.csv` and `synthetic-siem-events.json`. They are newly created simplified fixtures, not actual Caldera operation exports or Wazuh alert exports, and are not import-ready platform configuration. A record with `alert_generated: false` represents telemetry without an alert in this example.

## Authorized lab route

In an isolated, instructor-approved environment, select an approved Caldera agent and a short discovery operation. Start with non-destructive commands such as `uname -a`, `whoami`, and `ip addr show`. Record the actual ability ID, command, target, status, and execution time. Verify telemetry collection is enabled before running the operation; platform installation alone does not ensure command visibility.

Search the matching Wazuh agent and time window, record the events and alerts found, and identify commands that appear in execution records but lack matching SIEM evidence. Do not use illustrative fixture results as proof of live detection.

## Student tasks

1. Preserve and hash the source files; identify their timezone and target IDs.
2. Match operation rows to SIEM events using target, command, and time; explain any tolerance applied.
3. Record whether each behavior has telemetry, an alert, both, or neither in the supplied records.
4. Justify a behavior-specific ATT&CK mapping. Use T1082 for system information discovery, T1033 for user discovery, and T1016 for local network configuration discovery where supported.
5. Explain one gap and propose how to investigate it. Missing alerting may reflect a rule choice; missing events may reflect collection, execution, timing, or search scope.
6. Document the analysis in TheHive or the [report template](../../templates/incident-report.md).

## Corrections carried into this adaptation

- `whoami` concerns user discovery (T1033), rather than every discovery command being T1082.
- `sudo -l` is a privilege check; it does not by itself demonstrate exploitation for privilege escalation (T1068).
- Listing local interfaces with `ip addr show` concerns network configuration discovery (T1016); it is not automatically remote network service discovery (T1046).
- Local ability names from a manual are not assumed to be installed Caldera ability IDs.
- An authorized discovery command is not automatically malicious. Classify it using the exercise context and observed evidence.

## Deliverables

Operation summary, evidence hashes, correlation table, telemetry/alert gap analysis, justified ATT&CK mapping, and a case report. Live exercises should additionally provide redacted execution and SIEM screenshots.

[Correlation table template](../../templates/detection-correlation.csv) · [Sample validation notes](../../docs/sample-validation-notes.md)
