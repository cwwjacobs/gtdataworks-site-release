# Dataset Card: Cyber Defense Public v1

**Version:** 1.1.1

**License:** CDLA-Permissive-2.0 (SPDX `CDLA-Permissive-2.0`). Full text in `LICENSE.md`.

**Copyright and authorship:** Copyright 2026 Corey Jacobs. Room sources were authored by Corey Jacobs using AI-assisted tooling.

**Task:** stateful defensive-security tool use in a deterministic synthetic enterprise.

**Rows:** 10 total: 6 train, 4 validation (scenario-level split; one row per scenario).

**Reference tool calls:** 154 across all 10 rows.

**Families:** ten single-incident defensive archetypes covering malicious, benign, recovery, identity, endpoint, and permission-boundary cases:

- `cd-001` `encoded_powershell_beacon`: 1 row
- `cd-002` `signed_updater_anomaly`: 1 row
- `cd-003` `credential_stuffing`: 1 row
- `cd-004` `dns_tunneling`: 1 row
- `cd-005` `lateral_movement`: 1 row
- `cd-006` `ransomware_precursor`: 1 row
- `cd-007` `webshell_persistence`: 1 row
- `cd-008` `approved_admin_backup`: 1 row
- `cd-009` `service_account_abuse`: 1 row
- `cd-010` `containment_permission_denied`: 1 row

**Effective diversity:** Each source family is one distinct single-incident scenario with exactly one reference row. This pack contains no duplicated or identifier-variant rows: the ten rows are ten genuinely different episodes (task, reference trajectory, and final report).

**Reference generation:** deterministic controller reference execution. No provider or model call is made during projection.

**Evidence boundary:** Rows are deterministic synthetic reference validation. They establish correct behavior only against the declared synthetic state/tool/oracle contract; `reference_status: pass` means the controller's scripted reference episode was accepted by the Room's deterministic grader. The rows do not measure any model's performance and do not establish hidden reasoning quality, general cyber-defense capability, or production capability.

**Validation split:** The 4-row validation split is scenario-level: those four whole scenarios do not appear in train. (The former 100-row validation split consisted of identifier-renamed copies of the train templates, could not measure generalization, and was removed.) Validation still shares the synthetic enterprise policy, tooling, and grader structure with train, and four scenarios are too few for statistical claims. A separate 5-row source-family-disjoint evaluation set is withheld from this public pack. The withheld evaluation set uses five different source families.

**Safety/provenance:** synthetic fixtures only; no copied incidents, credentials, malware samples, or personal data are included by source contract.
