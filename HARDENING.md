<!-- markdownlint-disable -->

# Hardening Report: teraha-dev--statsfm-to-markdown/v1.1.2

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **teraha-dev--statsfm-to-markdown/v1.1.2** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow file uses `actions/checkout@v4`, which is pinned to a mutable tag rather than an immutable 40-character commit SHA. This means the action could be silently updated (or compromised) without the workflow noticing, enabling supply-chain attacks. It should be replaced with a full SHA pin, e.g. `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4`.

Locations:

- `.github/workflows/statsfm.yml:16`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Replaced `actions/checkout@v4` (mutable tag) with `actions/checkout@11d5960a326750d5838078e36cf38b85af677262 # v4` (full commit SHA) in `.github/workflows/statsfm.yml` line 16. The SHA was resolved via the GitHub API. The `# v4` comment preserves human readability while the pin prevents supply-chain attacks.

