# add-to-project

This action can be used in the following manner to add issues to project boards:

```yaml
jobs:
  add-issue-to-project:
    runs-on: ubuntu-latest
    steps:
      - uses: UCL-ARC/.github/actions/add-to-project@vx
        with:
          app-id: ${{ secrets.APP_ID }}
          app-pem: ${{ secrets.APP_PEM }}
          project-url: project_board_url
```

where `x` is the `major` version of the action, and `project_board_url` is the
full URL of the project board to which the repository's issues should be added.
If a particular label should trigger the action to go to a different project
board then one may specify the `label` input as follows:

```yaml
jobs:
  add-issue-to-project:
    runs-on: ubuntu-latest
    steps:
      - uses: UCL-ARC/.github/actions/add-to-project@vx
        with:
          app-id: ${{ secrets.APP_ID }}
          app-pem: ${{ secrets.APP_PEM }}
          label: label_name
          project-url: project_board_url
```

where `label_name` is a
[comma-separated list of labels](https://github.com/actions/add-to-project/tree/main?tab=readme-ov-file#inputs).
Lastly, `label-operator` may be used to specify the logical operator to be used
when checking for the presence of labels. The default value is `OR`, but may be
configured as follows:

```yaml
jobs:
  add-issue-to-project:
    runs-on: ubuntu-latest
    steps:
      - uses: UCL-ARC/.github/actions/add-to-project@vx
        with:
          app-id: ${{ secrets.APP_ID }}
          app-pem: ${{ secrets.APP_PEM }}
          label: label_name
          label-operator: AND
          project-url: project_board_url
```

where `label-operator` may be set to `AND`, `NOT` or `OR`.
