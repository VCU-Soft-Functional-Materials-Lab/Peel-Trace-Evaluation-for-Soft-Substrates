# Troubleshooting Guide

This guide lists common problems in the Peel Trace Evaluation for Soft Substrates workflow and conservative next actions.

## 1. Step 0 setup fails

Possible causes:

- required packages are missing;
- the notebook is not running from the repository root;
- the backend file is missing;
- the Python environment is incorrect.

Recommended actions:

1. Confirm that `fabric_peel_guided_core_v1_4_0_rc15.py` is present in the repository root.
2. Confirm that `requirements.txt` was installed.
3. Restart the kernel and rerun Step 0.
4. If running locally, confirm that Jupyter was started from the repository root.

## 2. Built-in Scotch Tape validation fails

Step 1 must pass before user-data analysis.

Possible causes:

- the bundled Scotch Tape validation file is missing or renamed;
- the backend file version does not match the notebook;
- expected validation files are missing;
- the repository was edited incompletely.

Recommended actions:

1. Do not continue to user-data analysis.
2. Confirm that the validation workbook and expected-output files are present.
3. Confirm that the notebook and backend version both match `v1.4.0-rc15`.
4. Reopen the notebook, restart the kernel, and rerun Step 0 and Step 1.

## 3. User data file does not appear in Step 2

Possible causes:

- the selected file is not an accepted input format;
- the file is a profile, benchmark, template, release-note, or prior-output file;
- the file was not uploaded into the active notebook session.

Accepted raw-data formats are:

- `.xlsx`
- `.xlsm`
- `.xls`
- `.csv`

Recommended actions:

1. Convert `.txt` instrument exports to `.csv` or Excel.
2. Confirm that the file contains real force-displacement peel-test data.
3. Re-upload the file or place it in the expected working directory.

## 4. Force or displacement columns are detected incorrectly

Possible causes:

- unusual column names;
- extra header rows;
- merged cells;
- multiple force-like or displacement-like columns;
- nonstandard units.

Recommended actions:

1. Use Step 3 to manually select the correct force and displacement columns.
2. Confirm the units before analysis.
3. Exclude sheets that are not real peel traces.
4. Add notes when the mapping required manual correction.

## 5. No valid 25 mm selected window is found

Possible causes:

- displacement units are incorrect;
- the trace is shorter than the required analysis window;
- the trace contains too little usable force signal;
- terminal exclusion removes too much usable displacement;
- the trace does not contain a stable region under manuscript-baseline settings.

Recommended actions:

1. Check displacement units first.
2. Inspect the raw trace and QC plot.
3. Confirm that the trace has enough displacement travel after the start offset and terminal exclusion.
4. Do not force manuscript-baseline metrics if the trace is not feasible.
5. Use Step 6 only for clearly labeled recovery or sensitivity analysis.

## 6. Top5 or Bottom5 extrema are incomplete

Possible causes:

- the trace has fewer than five meaningful peaks or troughs;
- peak prominence is too strict for the trace;
- the trace is smooth rather than oscillatory;
- the selected window is too short or too quiet.

Recommended actions:

1. Inspect the QC plot.
2. Do not force Top5/Bottom5 metrics without visual evidence that real extrema were missed.
3. Treat incomplete extrema as a metric-quality limitation.
4. Use recovery/sensitivity settings only if justified and labeled as modified.

## 7. Extrema are clustered in one small region

Possible causes:

- local noise;
- one macroscopic hump;
- unstable local fluctuation;
- peak detection identifying nearby points rather than distributed stick-slip behavior.

Recommended actions:

1. Inspect the QC plot before interpreting `SSA`.
2. Check whether peaks and troughs are distributed across the selected window.
3. Treat clustered extrema as a caution for metric interpretation.

## 8. Strong drift appears inside the selected window

Possible causes:

- peeling force is still increasing or decreasing systematically;
- the selected window includes a transition region;
- the trace does not have a stable plateau-like region.

Recommended actions:

1. Review the drift ratio and QC plot.
2. Do not interpret high `PSI` alone as reliable if the force trace has systematic drift.
3. Use manuscript-baseline output only if the selected window passes the locked drift gate.
4. Use Step 6 only for explicitly labeled sensitivity analysis.

## 9. Output-consistency audit fails

Possible causes:

- exported CSV or Excel values do not match in-memory calculated tables;
- file-writing was interrupted;
- output files were overwritten or edited externally;
- a backend or notebook mismatch occurred.

Recommended actions:

1. Do not use exported CSV or Excel outputs.
2. Restart the kernel.
3. Rerun the analysis.
4. Check `output_consistency_audit.csv` again.
5. Use outputs only after the audit passes.

## 10. No post-window break or drop is detected

Possible causes:

- the specimen did not show a clear post-window drop;
- the trace ended before failure;
- the force response remained elevated to the terminal displacement.

Recommended actions:

1. Inspect the full-trace QC plot.
2. Treat the final recorded displacement as a terminal-displacement fallback, not a confirmed failure displacement.
3. Report this limitation if displacement or break proxy is used.

## 11. Recovery or sensitivity run differs from manuscript baseline

Recovery and sensitivity runs are labeled as `NON_MANUSCRIPT_MODIFIED`.

Recommended actions:

1. Do not mix modified outputs with manuscript-baseline outputs.
2. Record the modified settings.
3. Use modified outputs only for troubleshooting, sensitivity analysis, or clearly disclosed secondary analysis.

## 12. General interpretation caution

The workflow reports protocol-defined descriptors of the measured peel response.

For soft substrates, the measured trace may include contributions from:

- interfacial separation;
- peel-arm deformation;
- test-system compliance;
- viscoelastic dissipation;
- plastic deformation;
- stick-slip behavior;
- terminal failure behavior;
- instrument and fixture configuration.

Do not treat the reported descriptors as intrinsic adhesive material constants without additional mechanical justification.
