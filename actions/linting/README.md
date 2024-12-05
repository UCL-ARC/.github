# linting

This action can be used in the following manner:

```yaml
jobs:
  linting:
    runs-on: ubuntu-latest
    steps:
      - uses: UCL-ARC/.github/actions/linting@vx
        with:
          pre-commit-config: ./.pre-commit-config.yaml
```

where `x` is the `major` version of the action.

To benefit from autofixing in CI, one must install the
[GitHub App](https://github.com/apps/pre-commit-ci-lite/installations/new).
