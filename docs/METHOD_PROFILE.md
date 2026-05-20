# Method Profile Guide

This guide explains the method-profile system used by the Peel Trace Evaluation for Soft Substrates workflow.

The method profile controls analysis-sensitive settings such as selected-window length, start offset, terminal exclusion, drift filtering, peak detection, and extrema requirements.

## 1. Manuscript-baseline profile

The manuscript-baseline profile is:

`manuscript_baseline_v1`

This profile is read-only and is intended to reproduce the manuscript-baseline analysis settings.

Use this profile when generating outputs intended to match the manuscript-baseline workflow.

## 2. Locked manuscript-baseline settings

The manuscript-baseline profile uses the following locked settings:

| Parameter | Locked value |
|---|---:|
| start offset | 5.0 mm |
| window length | 25.0 mm |
| terminal exclusion | final 20% of displacement span |
| drift gate | `abs(m) * Lwin / Fbar_win <= 0.25` |
| peak prominence | `0.003 × global maximum corrected force` |
| minimum selected-window points | 10 |
| required peaks/troughs | ≥5 peaks and ≥5 troughs |
| break/drop proxy | post-window `0.10 × Fc`, 1-point detection; final recorded displacement fallback if no drop is found |
| extrema-spread QC | advisory in manuscript baseline; optional hard fail only in modified mode |

The backend protects these settings through a locked method-profile hash.

## 3. Modified profiles

Modified settings are allowed only for recovery, troubleshooting, or sensitivity analysis.

Modified outputs should be labeled as:

`NON_MANUSCRIPT_MODIFIED`

Modified outputs should not be mixed with manuscript-baseline outputs unless the modification is explicitly disclosed.

## 4. When a modified profile may be useful

A modified profile may be useful when:

- a trace does not contain enough usable displacement for the 25 mm manuscript-baseline window;
- peak or trough extraction fails because the trace has weak or nonstandard oscillations;
- a sensitivity analysis is needed to test whether conclusions depend on analysis settings;
- the user is analyzing a different material system where the manuscript-baseline settings are not appropriate.

Modified profiles should not be used to optimize adhesive rankings.

## 5. User-created profiles

User-created profiles can include:

- `profile_id`;
- `display_name`;
- `profile_note`;
- modified analysis settings;
- recovery or sensitivity-analysis rationale.

Saved user profiles are separate from the locked manuscript-baseline profile.

## 6. Reporting guidance

When reporting manuscript-baseline results, state that the read-only `manuscript_baseline_v1` profile was used.

When reporting modified or sensitivity results, disclose:

- which setting was changed;
- why it was changed;
- whether the output is `NON_MANUSCRIPT_MODIFIED`;
- whether the change affects metric interpretation.

## 7. Interpretation caution

Changing analysis settings can change selected windows, extrema extraction, `PSI`, `SSA`, displacement proxies, and replicate summaries.

Therefore, profile changes should be treated as method changes, not cosmetic changes.
