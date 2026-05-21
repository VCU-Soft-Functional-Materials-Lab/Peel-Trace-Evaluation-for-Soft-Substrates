# Governance

This file describes repository governance, maintenance responsibility, and review expectations for **Peel Trace Evaluation for Soft Substrates**.

This repository is maintained as a manuscript-linked research-software workflow for reproducible peel-trace analysis of soft substrates.

## Lab and supervision

This repository is maintained under the supervision of Dr. Christina Tang and the VCU Soft Functional Materials Lab at Virginia Commonwealth University.

The repository supports notebook-based analysis, documentation, validation files, release preparation, and software/archive records associated with peel-trace evaluation of compliant bonded systems.

## Roles

### PI / supervising investigator

The PI or supervising investigator provides scientific oversight, approves major project direction, and determines whether repository materials may be made public, archived, or linked to scholarly outputs.

| Name | Role | Affiliation |
| --- | --- | --- |
| Dr. Christina Tang | PI / supervising investigator | Virginia Commonwealth University |

### Project lead

The project lead coordinates the manuscript-linked workflow, documentation, release preparation, and repository updates.

| Name | Role |
| --- | --- |
| Bhalaji Yadav Kantepalle | Project lead / primary maintainer |

### Repository maintainer

The repository maintainer is responsible for day-to-day repository upkeep.

Responsibilities include:

- reviewing proposed changes;
- maintaining documentation;
- checking dependency and security alerts;
- managing release preparation;
- verifying reproducibility-sensitive changes;
- keeping changelog, citation, and archive information current.

| Name | Role |
| --- | --- |
| Bhalaji Yadav Kantepalle | Repository maintainer |

## Decision-making

Routine documentation and repository-structure updates may be reviewed by the repository maintainer.

Major changes should be reviewed with the PI or project lead, especially when they affect:

- data availability;
- analysis settings;
- method-profile behavior;
- metric definitions;
- validation files;
- benchmark files;
- generated outputs;
- figures or tables;
- manuscript-linked results;
- repository visibility;
- licensing;
- DOI/archive records;
- public releases.

## Manuscript-baseline protection

The locked `manuscript_baseline_v1` profile should not be changed without explicit versioning and disclosure.

Changes should be treated as analysis-sensitive if they affect:

- force/displacement preprocessing;
- stable-window selection;
- extrema extraction;
- metric calculation;
- quality-control flags;
- output consistency checks;
- bundled validation files;
- expected validation outputs;
- manuscript-baseline exports.

Modified or recovery workflows should remain labeled as `NON_MANUSCRIPT_MODIFIED` and should not be mixed with manuscript-baseline outputs unless explicitly disclosed.

## Public release and archiving

Before creating a GitHub Release, linking a Zenodo archive, or citing this software version in a manuscript, poster, thesis, report, or public archive, confirm:

- PI or project-lead approval, if required;
- license status;
- data availability statement;
- release version;
- changelog entry;
- citation metadata;
- archived software/data DOI, if applicable;
- release checklist completion;
- repository access and protection settings.

## Data and intellectual-property caution

This governance file does not define legal ownership of code, data, figures, or intellectual property.

Do not make ownership claims in repository documentation unless they have been approved by the PI, institution, and relevant collaborators.

When in doubt, use neutral language such as:

> This repository is maintained under the supervision of the PI and project lead.

## Access review

Repository access should be reviewed when:

- a student graduates or leaves the project;
- an outside collaborator joins or leaves;
- repository visibility changes;
- a manuscript is submitted or accepted;
- a GitHub Release is created;
- a Zenodo archive or DOI record is created or updated;
- repository maintenance responsibility changes.
