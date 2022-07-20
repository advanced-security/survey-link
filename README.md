# Create GHAS Trial Survey Links #

## What?

This action automatically creates a weblink to GHAS trial survey. The links will be valid for 14 days by default (configurable).

## Example

```yaml
name: "Example"

on:
  workflow_dispatch:

jobs:
  analyze:
    name: Example
    runs-on: ubuntu-latest
    permissions:
      actions: read
      contents: read
      security-events: write

    steps:
    - name: Create Link
      id: createlink
      uses: advanced-security/survey-link@main
      with:
        surveymonkey_token: ${{ secrets.surveymonkey_token }}
        name: acmecorp 123

    - run: |
       echo "${{ steps.createlink.outputs.link }}"
```
