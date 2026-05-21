# Contributing Guide

This repository is maintained as a reproducible research-software workflow for peel-trace analysis of soft substrates.

The main public workflow is:

`Peel_Trace_Evaluation_for_Soft_Substrates.ipynb`

The backend file is:

`fabric_peel_guided_core_v1_4_0_rc15.py`

Most users should run the notebook, not the backend file directly.

## 1. Branch workflow

Do not edit `main` directly for nontrivial changes.

Use a working branch for edits:

- `readme-cleanup` for README and documentation cleanup;
- `docs-update` for documentation-only changes;
- `bugfix-*` for bug fixes;
- `feature-*` for new features;
- `release-*` for release-preparation changes.

After review and testing, merge the branch into `main`.

## 2. Documentation-only changes

Documentation-only changes may include edits to:

- `README.md`;
- `CHANGELOG.md`;
- `CONTRIBUTING.md`;
- files in `docs/`.

These changes do not alter the manuscript-baseline analysis method, unless they change reported settings, formulas, or instructions in a way that conflicts with the notebook or backend.

## 3. Higher-risk software changes

The following files should be changed carefully:

- `Peel_Trace_Evaluation_for_Soft_Substrates.ipynb`;
- `fabric_peel_guided_core_v1_4_0_rc15.py`;
- files in `method_profiles/`;
- files in `validation_data/`;
- bundled reference or benchmark files;
- `requirements.txt`.

Changes to these files may affect analysis behavior, reproducibility, Binder behavior, or validation outputs.

## 4. Manuscript-baseline profile rule

The locked manuscript-baseline profile:

`manuscript_baseline_v1`

should not be modified without explicit versioning and disclosure.

If analysis-sensitive settings are changed, the change should be treated as a method change, not a documentation change.

## 5. Validation before release

Before creating a release or merging software changes into `main`, check that:

- the notebook opens from the repository root;
- Step 0 runs successfully;
- Step 1 built-in Scotch Tape validation passes;
- the notebook imports the correct backend file;
- output files are generated correctly;
- output-consistency audit passes;
- README version and release notes match the notebook/backend version;
- `CHANGELOG.md` is updated.

For the full pre-merge and release checklist, see [`docs/RELEASE_CHECKLIST.md`](docs/RELEASE_CHECKLIST.md).

## 6. Modified or recovery profiles

Modified settings are allowed for recovery or sensitivity analysis, but outputs should remain labeled as:

`NON_MANUSCRIPT_MODIFIED`

These outputs should not be mixed with manuscript-baseline outputs unless explicitly disclosed.

## 7. Release notes

Release-specific changes should be recorded in:

`CHANGELOG.md`

Long release-history notes should not be placed in the main `README.md`.

## 8. General rule

Keep the README concise. Put detailed instructions in the `docs/` folder.

## 9. License

By contributing to this repository, contributors agree that their contributions are provided under the repository license:

`Apache License 2.0`

See [`LICENSE`](LICENSE) for the full license text.

