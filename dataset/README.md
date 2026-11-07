# Cyber Defense Public v1

Version 1.1.1. License: CDLA-Permissive-2.0 (SPDX `CDLA-Permissive-2.0`); full text in `LICENSE.md`.

Synthetic stateful cyber-defense agent trajectories projected from the Cyber Defense Rooms.

## Contents

- 10 total rows across ten source families, one row per family.
- 6 `train` rows and 4 `validation` rows; validation scenarios are whole scenarios withheld from train, not identifier copies.
- Every row is a distinct scenario; there are no duplicated or identifier-variant rows.
- Every row includes the actor-visible task, tool contract, deterministic reference tool trajectory, and final report.
- `export/sft_train_6.jsonl` provides chat/tool-call shaped training records for the 6 train rows.

## Files

- `canonical/public_10.jsonl`: all 10 rows.
- `canonical/train_6.jsonl` and `canonical/validation_4.jsonl`: the same rows split by `split`.
- `export/sft_train_6.jsonl`: chat/tool-call records for the 6 train rows.
- `manifest.json` and `reports/FILE_MANIFEST.tsv`: file sizes and SHA-256 digests.
- `reports/PROVENANCE.jsonl`: per-row source hashes and materialization records.
- `reports/SPLIT_RECEIPT.json`: split counts.
- `DATASET_CARD.md` and `LICENSE.md`.

## Diversity

Each source family is one distinct single-incident scenario with exactly one reference row. This pack contains no duplicated or identifier-variant rows: the ten rows are ten genuinely different episodes (task, reference trajectory, and final report).

The 4-row validation split is scenario-level: those four whole scenarios do not appear in train. (The former 100-row validation split consisted of identifier-renamed copies of the train templates, could not measure generalization, and was removed.) Validation still shares the synthetic enterprise policy, tooling, and grader structure with train, and four scenarios are too few for statistical claims. A separate 5-row source-family-disjoint evaluation set is withheld from this public pack.

## Evidence boundary

Rows are deterministic synthetic reference validation. They establish correct behavior only against the declared synthetic state/tool/oracle contract; `reference_status: pass` means the controller's scripted reference episode was accepted by the Room's deterministic grader. The rows do not measure any model's performance and do not establish hidden reasoning quality, general cyber-defense capability, or production capability.

All scenarios are synthetic. Source Room `COPYING` declarations state that the fixtures contain no copied incident, credential, malware sample, or personal data.

## License and copyright

Copyright 2026 Corey Jacobs. Room sources were authored by Corey Jacobs using AI-assisted tooling.

This dataset is made available under the Community Data License Agreement - Permissive - Version 2.0 (SPDX `CDLA-Permissive-2.0`). The full text is in `LICENSE.md`. If you share the data, with or without modifications, make the text of that agreement available with it.
