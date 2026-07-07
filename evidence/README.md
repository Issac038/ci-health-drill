# CI Health Analysis Evidence

This directory contains evidence artifacts supporting the findings in `CI-HEALTH-REPORT.md`.

## Evidence Artifacts

### Observation 1 — `test` job configuration failure
- **File:** `run-28-jest-not-found.png` (screenshot)
- **Proves:** Run #28 (docs-only commit) fails with `jest: not found`, demonstrating configuration failure independent of code changes.

### Observation 2 — Disabled security scan
- **File:** `security-scan-if-false.yaml` or workflow screenshot
- **Proves:** `security-scan.yml` had `if: false`, disabling vulnerability scanning on all `main` pushes.

### Observation 3 — Flaky gateway integration test
- **File:** `run-23-vs-24-same-commit.png` (comparison screenshot)
- **Proves:** Runs #23 (fail, timeout) and #24 (pass) on identical commit `22d3b40`, demonstrating non-deterministic behavior.

### Observation 4 — Direct pushes to main
- **File:** `main-commit-history.png` (screenshot)
- **Proves:** Commits like `fbd120d hotfix: urgent payment fix` and `0d9287c quick auth patch` pushed directly to `main` without PR review.

### Observation 5 — Skipped test coverage
- **File:** `validateAmount.test.js` (code snippet)
- **Proves:** Negative-amount validation test was skipped, hiding coverage gap (now fixed in this PR).

## Note

Screenshots are referenced in the Risk Analysis. If running this analysis manually, capture the relevant GitHub Actions run logs and workflow configuration files as indicated above.
