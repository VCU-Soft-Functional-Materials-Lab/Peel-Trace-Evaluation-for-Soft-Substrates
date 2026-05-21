# Documentation

This folder contains detailed documentation for the Peel Trace Evaluation for Soft Substrates workflow.

For most users, start with the main repository [`README.md`](../README.md), then use the guides below as needed.

## Guides

| File | Purpose |
|---|---|
| `WORKFLOW.md` | Step-by-step guide for running the notebook from Step 0 through Step 7 |
| `OUTPUT_GUIDE.md` | Explanation of output files, QC plots, diagnostic files, audits, and provenance records |
| `TROUBLESHOOTING.md` | Common notebook, validation, mapping, metric-extraction, and export problems |
| `METHOD_PROFILE.md` | Explanation of locked manuscript-baseline settings, user profiles, and modified-profile rules |
| `RELEASE_CHECKLIST.md` | Pre-merge, validation, GitHub release, and Zenodo archive checklist |
| `GOVERNANCE.md` | Repository governance, review expectations, and manuscript-baseline protection |
| `MAINTAINERS.md` | Project lead, maintainer, and PI/supervision information |

## Visual assets

| File | Purpose |
|---|---|
| [`peel_trace_workflow_overview.png`](peel_trace_workflow_overview.png) | Workflow overview figure used in the main README to summarize the notebook pipeline from input data to validation, mapping, trace processing, metric extraction, and QC-reviewed outputs |

## Main workflow file

The main notebook is kept at the repository root for Binder, Colab, and local Jupyter compatibility:

`Peel_Trace_Evaluation_for_Soft_Substrates.ipynb`

The backend file is also kept at the repository root:

`fabric_peel_guided_core_v1_4_0_rc15.py`

Most users should run the notebook, not the backend file directly.

## Interpretation caution

The workflow reports protocol-defined descriptors of measured peel response. These descriptors should not be treated as intrinsic adhesive material constants without additional mechanical justification, substrate-deformation checks, and fracture-mechanics interpretation.
