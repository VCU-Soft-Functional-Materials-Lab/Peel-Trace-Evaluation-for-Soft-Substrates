# Workflow Guide

This guide explains how to run the Peel Trace Evaluation for Soft Substrates notebook from start to finish.

The main workflow file is:

`Peel_Trace_Evaluation_for_Soft_Substrates.ipynb`

The backend file:

`fabric_peel_guided_core_v1_4_0_rc15.py`

is imported automatically by the notebook and should not be run directly by most users.

## 1. Start the notebook

Use one of the following options.

### Binder

Click the Binder badge in the main `README.md`, then open:

`Peel_Trace_Evaluation_for_Soft_Substrates.ipynb`

### Local Jupyter

Clone the repository, install the requirements, start Jupyter, and open:

`Peel_Trace_Evaluation_for_Soft_Substrates.ipynb`

## 2. Run Step 0: setup

Step 0 loads packages, initializes the notebook, checks paths, and imports the backend.

If Step 0 fails, stop and inspect the error before continuing. Most setup errors are caused by missing packages, an incorrect working directory, or a missing backend file.

## 3. Run Step 1: built-in reference validation

Step 1 validates the bundled Scotch Tape reference file.

Later user-data analysis steps are blocked unless the built-in validation passes.

This validation checks that the notebook and backend can reproduce the expected reference outputs. It does not replace inspection of user-data QC plots.

## 4. Run Step 2: select or upload user data

Step 2 is used to select the real peel-test force-displacement data file.

Accepted input formats include:

- `.xlsx`
- `.xlsm`
- `.xls`
- `.csv`

Do not select method-profile files, benchmark files, template files, prior-output files, or release-note files as raw data.

## 5. Run Step 3: confirm mapping

Step 3 scans the selected file and lets the user confirm or correct:

- included or excluded sheets;
- force column;
- displacement column;
- force unit;
- displacement unit;
- specimen width;
- specimen thickness;
- group label;
- adhesive label;
- optional notes.

Do not confirm the mapping until the included sheets, units, geometry, and labels are correct.

## 6. Run Step 4: choose method profile

Use the read-only `manuscript_baseline_v1` profile for manuscript-baseline analysis.

User-created or recovery profiles are allowed, but those outputs should be treated as modified or sensitivity analyses. They should not be mixed with manuscript-baseline outputs unless explicitly disclosed.

## 7. Run Step 5: analyze traces

Step 5 generates the primary outputs, including:

- per-trace metrics;
- group summaries;
- QC plots;
- diagnostic tables;
- output-consistency audits;
- formula and metric guides;
- provenance records;
- output archive.

Inspect the QC plots before interpreting the numerical metrics.

## 8. Use Step 6 only for recovery or sensitivity analysis

Step 6 is intended for cases where the manuscript-baseline profile is not feasible for one or more traces, or when the user wants to explore sensitivity to method settings.

Outputs from Step 6 are labeled as `NON_MANUSCRIPT_MODIFIED`.

These outputs should not be reported as manuscript-baseline results unless the modification is explicitly described.

## 9. Use Step 7 only after a trusted run

Step 7 is for reproducibility management and optional user benchmarks.

Use it only after reviewing the Step 5 results, QC plots, diagnostics, and output-consistency checks.

## 10. Recommended inspection order

After a successful run, inspect outputs in this order:

1. `analysis_report.xlsx`
2. `qc_plots/`
3. `paper_metrics.csv`
4. `group_summary.csv`
5. `diagnostic_summary.csv`
6. `output_consistency_audit.csv`
7. `provenance.json`

The QC plots should be checked before drawing conclusions from `PSI`, `SSA`, `Fc/w`, or `Fci/w`.

## 11. Common rerun cases

Use this guide:

- New data file: return to Step 2.
- Wrong columns, units, labels, or geometry: return to Step 3.
- Different method profile: return to Step 4.
- Same settings but rerun needed: rerun Step 5.
- Recovery or sensitivity analysis: use Step 6.
- User benchmark creation or validation: use Step 7 after a trusted run.

## 12. Interpretation caution

The outputs are protocol-defined descriptors of the measured peel response under the selected geometry, testing protocol, and analysis settings.

They should not be treated as intrinsic adhesive material constants unless additional fracture-mechanics assumptions, substrate-deformation checks, and interpretation limits are satisfied.
