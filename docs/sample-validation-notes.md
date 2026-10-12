# Public sample validation notes

These are instructor/reviewer notes for the newly generated synthetic samples, not a historical student answer key.

## Week 12

The Windows sample pairs an approved update with undocumented temporary-path execution and a scheduled task. PowerShell execution can support T1059.001; the task record can support T1053.005 as a behavior mapping. Neither record alone proves malicious intent. Network destination 192.0.2.50 is a documentation address and is not a real IOC.

The Linux sample shows two failed logins, a later successful login, and a temporary-path script execution. It does not establish brute force, a reverse shell, account compromise, or a link to the Windows activity. Good reports state the missing authorization context and request additional evidence.

## Week 13

OP01 matches S01 by command, target, and a two-second difference: telemetry and an illustrative alert are present. OP02 matches S02: telemetry is present but alerting is absent. OP03 has no matching event in the supplied fixture. This distinction demonstrates three visibility states, not measured coverage of the live university lab.

Appropriate proposed mappings are T1082, T1033, and T1016 respectively. Live technique coverage would require a documented execution, collected telemetry, rule behavior, search scope, and result.

## Validation performed

Fixture JSON parses; CSV records use consistent headers; operation/event references and timestamps are internally coherent. No fixture was imported into a live TheHive, Wazuh, Caldera, or Velociraptor deployment. They are offline learning examples, not installation or interoperability tests.
