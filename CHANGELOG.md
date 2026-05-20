# Changelog

All notable changes to this repository are documented here.

This changelog is for software, notebook-interface, documentation, and repository-structure changes. The manuscript-baseline method profile should not be changed without explicit versioning and disclosure.

## v1.4.0-rc15

### Method status

- Manuscript-baseline calculations are unchanged.
- The locked `manuscript_baseline_v1` profile remains read-only.
- Recovery or sensitivity runs remain labeled as `NON_MANUSCRIPT_MODIFIED`.
- Built-in Scotch Tape validation remains separate from user-run diagnostics.
- User benchmarks remain separate from bundled reference-validation files.

### Added

- Step 3 mapping review with live-count filters.
- Step 3 batch editing for included/excluded sheets, geometry, labels, notes, and common units.
- Step 4 sheet-aware window-feasibility cautions for user-created profiles.
- Step 4 visible `Save and activate user profile` action in create/edit mode.
- Step 5 duplicate-run blocking for unchanged file, mapping, profile, and backend version.
- Step 6 duplicate-run blocking for unchanged non-manuscript modified recovery/sensitivity runs.
- Step 6 recovery-profile controls and user-profile reuse.
- Compact notebook display for audit/output tables, with full tables exported to CSV/Excel.
- Improved QC-plot layout with figure-level legend, status title, metric boxes, and tighter save padding.
- Closable help widgets for major mapping, profile, analysis, recovery, benchmark, and output-guide controls.
- Concise README quick-start instructions for Binder and local Jupyter use.
- Detailed workflow documentation in `docs/WORKFLOW.md`.
- Detailed output documentation in `docs/OUTPUT_GUIDE.md`.
- Troubleshooting documentation in `docs/TROUBLESHOOTING.md`.
- Method-profile documentation in `docs/METHOD_PROFILE.md`.
- Documentation index in `docs/README.md`.
- Release checklist in `docs/RELEASE_CHECKLIST.md`.
- Contributor guidance in `CONTRIBUTING.md`.
- `.gitignore` rules for local environments, notebook checkpoints, and generated analysis outputs.

### Changed

- Confirmed file, mapping, and profile panels collapse after confirmation to reduce visual clutter.
- Step 3 automatically switches from `Needs review (0)` to `All sheets` when no mapping items need review.
- Step 3 displays a problem-focused banner before mapping confirmation.
- Step 4 user-profile guidance is shown on demand so the activation button and acknowledgments are easier to find.
- Detailed audit tables are closed by default in the notebook view.
- The final reproducibility manager handles user benchmarks without overwriting bundled Scotch reference files.
- Moved long release-candidate history out of `README.md` and into `CHANGELOG.md`.
- Updated the README to keep public-facing instructions concise while linking to detailed documentation files.
- Removed the duplicate notebook copy from the `notebooks/` folder; the root notebook remains the public Binder/Colab entry point.

### Safeguards

- Step 1 built-in reference validation must pass before downstream user-data analysis.
- Step 3 blocks normal mapping confirmation when included sheets still need review unless the user explicitly acknowledges the remaining issues.
- Step 4 and Step 6 require explicit acknowledgment for advanced short-window or infeasible-window profiles.
- Output-consistency failures indicate that exported CSV/Excel outputs should not be used until rerunning or debugging.

### Notes

- The root notebook is kept at the repository root for Binder, Colab, and local Jupyter compatibility.
- The backend Python file is imported by the notebook and should not be run directly by most users.
- Release-specific interface notes are documented here instead of in the main README.
- The bundled Scotch Tape validation workbook currently uses the legacy filename `ScothTapeTpeel.xlsx`. This filename is retained in `v1.4.0-rc15` for notebook/backend compatibility and should not be renamed without updating and retesting all validation-file references.
