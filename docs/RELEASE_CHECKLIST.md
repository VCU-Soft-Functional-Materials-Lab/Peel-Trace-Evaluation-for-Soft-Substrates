# Release Checklist

Use this checklist before merging major changes into `main` or preparing a GitHub release.

## 1. Repository status

- Confirm the working branch is not `main`.
- Confirm all intended changes are committed.
- Confirm no temporary files, test outputs, or local notebook checkpoints are included.
- Confirm `README.md` is concise and does not contain long release-history notes.
- Confirm release-specific notes are in `CHANGELOG.md`.

## 2. Version consistency

Check that the version is consistent across:

- `README.md`
- `CHANGELOG.md`
- `CITATION.cff`
- `Peel_Trace_Evaluation_for_Soft_Substrates.ipynb`
- `fabric_peel_guided_core_v1_4_0_rc15.py`
- method-profile files
- GitHub release tag
- Zenodo release record, if a new archive is created

## 3. Notebook startup

Before release, confirm that:

- the notebook opens from the repository root;
- the notebook imports `fabric_peel_guided_core_v1_4_0_rc15.py`;
- Step 0 runs successfully;
- no required package is missing;
- Binder or local Jupyter can start the notebook.

## 4. Built-in validation

Run Step 1 and confirm that the bundled Scotch Tape reference validation passes.

Expected for `v1.4.0-rc15`:

- Scotch expected-output validation: `33/33 PASS`
- Output consistency audit: `194/194 PASS`

The exact output-consistency count may change if exported table schemas change.

## 5. User-data workflow check

Using a real or test peel-trace input file, confirm that:

- Step 2 selects or uploads the data file;
- Step 3 detects or allows correction of columns, units, geometry, group labels, and adhesive labels;
- Step 4 activates the intended method profile;
- Step 5 generates metrics, plots, diagnostics, audits, and output archive;
- output-consistency audit passes;
- QC plots are generated and readable.

## 6. Documentation check

Confirm that these files exist and are current:

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `docs/WORKFLOW.md`
- `docs/OUTPUT_GUIDE.md`
- `docs/TROUBLESHOOTING.md`
- `docs/METHOD_PROFILE.md`
- `docs/RELEASE_CHECKLIST.md`

Confirm that README links to the relevant documentation files.

## 7. Manuscript-baseline protection

Confirm that the locked manuscript-baseline profile remains unchanged unless this is an explicitly versioned method change.

Check that:

- `manuscript_baseline_v1` remains read-only;
- recovery or sensitivity outputs remain labeled `NON_MANUSCRIPT_MODIFIED`;
- modified profiles are not mixed with manuscript-baseline outputs;
- method-profile changes are disclosed in release notes if any analysis-sensitive setting changes.

## 8. File organization

Confirm that repository files are organized as expected:

- root notebook remains at the repository root for Binder, Colab, and local Jupyter compatibility;
- backend file remains at the repository root;
- method profiles are in `method_profiles/`;
- validation data are in `validation_data/`;
- documentation files are in `docs/`;
- templates are in `templates/`.

## 9. GitHub release

Before creating a GitHub release:

- merge reviewed changes into `main`;
- confirm `main` is up to date;
- create an appropriate tag, such as `v1.4.0-rc15`;
- use `CHANGELOG.md` content as the basis for release notes;
- verify that the release assets and source archive are correct.

## 10. Zenodo release

If a new GitHub release is archived on Zenodo:

- confirm the Zenodo metadata are correct;
- confirm author/contributor names and roles;
- confirm title and version;
- confirm license is Apache License 2.0;
- confirm DOI information;
- confirm the correct GitHub release was archived.

A documentation-only cleanup does not necessarily require a new manuscript-baseline software DOI unless a new release/archive is intentionally created.

## 11. Final review before merge

Before merging into `main`, confirm:

- README renders correctly on GitHub;
- all internal links work;
- no chat/instruction text was accidentally pasted into documentation;
- no broken Markdown code blocks exist;
- branch protection or pull-request review is used if enabled;
- the merge does not unintentionally change notebook logic, backend code, validation files, or method profiles.
