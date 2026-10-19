# Changelog

All notable changes to this repository are documented here.

This changelog covers software, notebook-interface, documentation, and repository-structure changes. The manuscript-baseline method profile should not be changed without explicit versioning and disclosure.

## Unreleased

### Method status

- Manuscript-baseline calculations are unchanged.
- No metric definitions, preprocessing settings, analysis thresholds, validation thresholds, or backend calculations were changed.
- This update improves repository usability, Colab launch behavior, README first-screen clarity, scholarly provenance linking, README visual documentation, and notebook text readability only.

### Added

- Added a Google Colab badge to the README.
- Added Google Colab quick-start instructions explaining that Step 0 automatically clones the repository when the backend file is missing.
- Added Colab-safe Step 0 bootstrap logic to the notebook so Colab can load the backend module without requiring manual repository setup.
- Added a representative QC plot at `docs/example_outputs/scotch_tape_qc_trace.png`.
- Added an Example outputs section to the README showing a processed peel trace, selected analysis window, Top5/Bot5 extraction points, force descriptors, and QC diagnostics.
- Documented the new README visual asset in `docs/README.md`.
- Added an `Associated publication and research records` section to the README linking the published article, source dataset, all-versions software archive, exact `v1.4.0-rc15` software release, and related M.S. thesis repository record.

### Changed

- Simplified the README title by moving `v1.4.0-rc15` from the main heading into a separate manuscript-baseline release line.
- Revised the README opening description to frame the repository as a multi-criteria peel-trace analysis workflow for soft substrates.
- Updated the README Quick start section to separate Binder, Colab, and local execution paths.
- Updated the README repository layout tree to include `docs/example_outputs/`.
- Cleaned notebook text-encoding artifacts in displayed Markdown and UI labels, including corrupted dash, multiplication, inequality, registered-trademark, bullet, and stick-slip symbols.
- Consolidated scholarly provenance links near the top of the README so the publication, data, software archive, exact analysis release, and related thesis record can be located from one place.

### Notes

- In Colab, the notebook intentionally does not force-install the full `requirements.txt` file because replacing NumPy/SciPy inside an active Colab runtime can cause package mismatch errors.
- Binder and local installations continue to use the repository environment and `requirements.txt`.
- The new example QC image is a README display asset and does not change the analysis workflow or generated manuscript-baseline outputs.

## v1.4.0-rc15

### Method status

- Manuscript-baseline calculations are unchanged.
- The locked `manuscript_baseline_v1` profile remains read-only.
- Recovery or sensitivity runs remain labeled `NON_MANUSCRIPT_MODIFIED`.
- Built-in Scotch Tape validation remains separate from user-run diagnostics.
- User benchmarks remain separate from bundled reference-validation files.

### Added

- Added Step 3 mapping review with live-count filters.
- Added Step 3 batch editing for included/excluded sheets, geometry, labels, notes, and common units.
- Added Step 4 sheet-aware window-feasibility cautions for user-created profiles.
- Added a visible `Save and activate user profile` action in Step 4 create/edit mode.
- Added Step 5 duplicate-run blocking for unchanged file, mapping, profile, and backend version.
- Added Step 6 duplicate-run blocking for unchanged non-manuscript modified recovery/sensitivity runs.
- Added Step 6 recovery-profile controls and user-profile reuse.
- Added compact notebook display for audit and output tables, with full tables exported to CSV/Excel.
- Added an improved QC-plot layout with a figure-level legend, status title, metric boxes, and tighter save padding.
- Added closable help widgets for major mapping, profile, analysis, recovery, benchmark, and output-guide controls.
- Added concise README quick-start instructions for Binder and local Jupyter use.
- Added detailed workflow documentation in `docs/WORKFLOW.md`.
- Added detailed output documentation in `docs/OUTPUT_GUIDE.md`.
- Added troubleshooting documentation in `docs/TROUBLESHOOTING.md`.
- Added method-profile documentation in `docs/METHOD_PROFILE.md`.
- Added a documentation index in `docs/README.md`.
- Added a release checklist in `docs/RELEASE_CHECKLIST.md`.
- Added contributor guidance in `CONTRIBUTING.md`.
- Added a pull request template in `.github/pull_request_template.md` for documenting analysis-sensitive changes before merging.
- Added a CODEOWNERS file in `.github/CODEOWNERS` for review ownership of reproducibility-sensitive files.
- Added issue templates in `.github/ISSUE_TEMPLATE/` for bug reports and documentation updates.
- Added Dependabot configuration in `.github/dependabot.yml` for dependency-maintenance guidance.
- Added security reporting guidance in `SECURITY.md`.
- Added project governance guidance in `docs/GOVERNANCE.md`.
- Added maintainer information in `docs/MAINTAINERS.md`.
- Added repository formatting support through `.editorconfig`.
- Added Git attributes configuration through `.gitattributes`.
- Added `.gitignore` rules for local environments, notebook checkpoints, and generated analysis outputs.
- Added a workflow overview figure at `docs/peel_trace_workflow_overview.png` and documented it in `docs/README.md`.
- Added a GitHub Actions workflow for automated Scotch Tape reference validation using the bundled validation workbook.
- Added attribution, repository, and reproducibility notes to generated HTML and Markdown run reports.

### Changed

- Updated confirmed file, mapping, and profile panels to collapse after confirmation and reduce visual clutter.
- Updated Step 3 to switch automatically from `Needs review (0)` to `All sheets` when no mapping items require review.
- Updated Step 3 to display a problem-focused banner before mapping confirmation.
- Updated Step 4 user-profile guidance to appear on demand so the activation button and acknowledgments are easier to find.
- Updated detailed audit tables to remain closed by default in the notebook view.
- Updated the final reproducibility manager to handle user benchmarks without overwriting bundled Scotch reference files.
- Moved long release-candidate history out of `README.md` and into `CHANGELOG.md`.
- Updated the README to keep public-facing instructions concise while linking to detailed documentation files.
- Removed the duplicate notebook copy from the `notebooks/` folder. The root notebook remains the public Binder, Colab, and local Jupyter entry point.
- Updated `requirements.txt` with compatible version ranges for reproducible Binder and local setup.
- Updated `README.md` and `docs/README.md` with links to repository governance and maintenance documentation.
- Updated the Peel-specific release checklist in `docs/RELEASE_CHECKLIST.md`.
- Removed the UTF-8 byte-order mark from `Peel_Trace_Evaluation_for_Soft_Substrates.ipynb` to prevent Binder/Jupyter `NotJSONError` loading failures.
- Updated the Binder badge to use the `urlpath=tree/...` notebook-opening route.
- Replaced the corrupted or incorrectly named Scotch Tape validation workbook with the corrected `ScotchTapeTpeel.xlsx` file at the repository root and in `validation_data/`.
- Improved notebook upload guidance and hid code cells by default to improve public usability.

### Safeguards

- Step 1 built-in reference validation must pass before downstream user-data analysis.
- Step 3 blocks normal mapping confirmation when included sheets still require review unless the user explicitly acknowledges the remaining issues.
- Step 4 and Step 6 require explicit acknowledgment for advanced short-window or infeasible-window profiles.
- Output-consistency failures indicate that exported CSV/Excel outputs should not be used until the workflow is rerun or debugged.

### Notes

- The root notebook is kept at the repository root for Binder, Colab, and local Jupyter compatibility.
- The backend Python file is imported by the notebook and should not be run directly by most users.
- Release-specific interface notes are documented here instead of in the main README.
- The bundled Scotch Tape validation workbook is named `ScotchTapeTpeel.xlsx` and is included at the repository root and in `validation_data/` for notebook and validation compatibility.
