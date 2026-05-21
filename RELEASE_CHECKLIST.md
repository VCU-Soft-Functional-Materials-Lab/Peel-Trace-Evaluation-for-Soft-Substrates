# Release Checklist 

Use this checklist before making a repository public, creating a GitHub Release, linking a DOI archive, or citing the software in a manuscript, poster, thesis, or report.

## Repository metadata

- [ ] Repository name is clear and project-specific.
- [ ] Repository description is accurate.
- [ ] README has been updated from the template.
- [ ] Maintainer/contact information is correct.
- [ ] Repository visibility has been approved by the PI or project lead.

## Documentation

- [ ] `README.md` explains the project purpose.
- [ ] `docs/user_guide.md` explains how to run the workflow.
- [ ] `docs/output_dictionary.md` defines output files, columns, metrics, and units.
- [ ] `CHANGELOG.md` records major changes.
- [ ] `CITATION.cff` has the correct title, authors, version, date, and repository URL.
- [ ] License choice has been approved and added if appropriate.

## Reproducibility

- [ ] Input data sources are documented.
- [ ] Analysis settings are documented.
- [ ] Dependency files are current.
- [ ] Example inputs or usage instructions are available.
- [ ] Generated outputs can be reproduced from documented inputs.
- [ ] Figures and tables are traceable to scripts, notebooks, or documented workflows.

## Data and outputs

- [ ] Large raw data are not committed directly unless approved.
- [ ] Sensitive, restricted, or unpublished data are not exposed.
- [ ] Data archive link or DOI is documented if applicable.
- [ ] Generated results used in manuscripts or reports are clearly identified.
- [ ] Output files match the documented output dictionary.

## Repository protection

- [ ] Default branch is `main`.
- [ ] Pull requests are required before merging, if applicable.
- [ ] Force pushes are blocked.
- [ ] Release/version tags are protected when possible.
- [ ] Workflow permissions are not broader than needed.
- [ ] Secrets and deploy keys have been checked.

## Release and archive

- [ ] Version number is selected.
- [ ] GitHub Release notes summarize the release.
- [ ] Release tag points to the correct commit.
- [ ] Zenodo or other archive record is linked if applicable.
- [ ] DOI information is added to README and/or Data Availability Statement if applicable.
- [ ] The archived release matches the version cited in manuscripts or reports.

## Final check

- [ ] A maintainer has reviewed the repository before public release.
- [ ] The PI or project lead has approved public release if required.
