# Security Policy

This repository is maintained for research code, analysis workflows, documentation, and reproducible scientific computing.

## Supported versions

For active project repositories, only the current maintained branch or most recent release is generally supported.

For manuscript-linked repositories, the archived release used for a publication should not be silently modified. Corrections should be made through a new release, with the change documented in `CHANGELOG.md`.

## Reporting a security or data-exposure concern

Report concerns to the repository maintainer, project lead, or PI according to the lab's internal communication process.

Examples of concerns include:

- accidentally committed credentials, tokens, or API keys
- exposed private, restricted, unpublished, or sensitive data
- dependency vulnerabilities that may affect repository use
- unsafe workflow permissions
- unexpected GitHub Actions behavior
- incorrect public exposure of files intended to remain private

## Do not report sensitive details publicly

If the concern involves credentials, private data, unpublished data, or access control, do not post the sensitive details in a public issue.

Instead, contact the project maintainer or PI directly.

## Maintainer response

Maintainers should:

- assess the concern promptly
- remove or rotate exposed credentials if needed
- check repository history if sensitive material was committed
- document corrective action when appropriate
- create a new release if the correction affects archived or manuscript-linked code

## Dependency security

Projects should use GitHub dependency alerts, Dependabot security updates, or equivalent review processes where appropriate.

For manuscript-linked repositories, dependency changes should be reviewed carefully because package updates may affect reproducibility.
