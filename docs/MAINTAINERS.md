# Maintainers

This file identifies the people responsible for repository maintenance, review, and release coordination for **Peel Trace Evaluation for Soft Substrates**.

This repository is maintained as a reproducible research-software workflow for peel-trace analysis of soft substrates.

## Project lead

| Name | Role | Contact | Notes |
| --- | --- | --- | --- |
| Bhalaji Yadav Kantepalle | Project lead / primary maintainer | @kbhalajiyadav | Coordinates repository updates, documentation, release preparation, and manuscript-baseline workflow maintenance |

## PI / supervising investigator

| Name | Role | Contact | Notes |
| --- | --- | --- | --- |
| Dr. Christina Tang | PI / supervising investigator | - | Provides scientific supervision and project-level oversight through the VCU Soft Functional Materials Lab |

## Repository maintainers

| Name | Role | Contact | Responsibilities |
| --- | --- | --- | --- |
| Bhalaji Yadav Kantepalle | Repository maintainer | kantepalleb@vcu.edu | Reviews changes, maintains documentation, checks reproducibility-sensitive updates, coordinates release preparation, and tracks DOI/archive consistency |

## Maintainer responsibilities

Maintainers are responsible for:

- reviewing pull requests or proposed changes before merging into `main`;
- checking reproducibility-sensitive changes;
- keeping documentation current;
- updating `CHANGELOG.md` when appropriate;
- checking dependency and security alerts;
- confirming release tags and DOI/archive links;
- confirming that Binder, Colab, and local Jupyter usage remain functional where applicable;
- coordinating with the PI or project lead before public release, DOI archiving, or manuscript-linked changes.

## Manuscript-linked repository checks

Because this repository is linked to a manuscript-baseline workflow, maintainers should verify that changes do not silently alter:

- locked analysis settings;
- input data handling;
- method-profile behavior;
- metric definitions;
- validation files;
- benchmark files;
- notebook execution order;
- output files;
- figures or tables;
- release tags;
- Zenodo DOI/archive records.

The locked `manuscript_baseline_v1` profile should not be changed without explicit versioning and disclosure.

## Access review

Repository access should be reviewed periodically, especially when:

- students graduate or leave the project;
- collaborators leave the project;
- new maintainers are added;
- repository visibility changes;
- a new GitHub Release is created;
- a Zenodo archive or DOI record is updated.

## Contact note

For scientific questions about the manuscript or project direction, contact the project lead or PI.

For repository, workflow, or release-related questions, contact the repository maintainer.
