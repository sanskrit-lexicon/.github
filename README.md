# .github — org defaults

Community health files and reusable workflows for every repository in this account.
Nothing here runs on its own: repositories opt in by calling a workflow, and inherit
the templates automatically unless they ship a local override.

- `SECURITY.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `PULL_REQUEST_TEMPLATE.md` — inherited defaults.
- `ISSUE_TEMPLATE/` — bug, feature, data correction.
- `.github/workflows/` — reusable workflows: `data-validate`, `changelog-lint`, `codeql`, `pages`, `release`.
- [`README-TEMPLATE.md`](https://github.com/sanskrit-lexicon/.github/blob/main/README-TEMPLATE.md) — drop-in "Join the proofreading" README section for dictionary repositories (three-step ladder: report → verify → change file; pilot: [MWS](https://github.com/sanskrit-lexicon/MWS)).

Caller shape:

```yaml
jobs:
  validate:
    uses: OWNER/.github/.github/workflows/data-validate.yml@main
```
