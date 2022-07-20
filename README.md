# Create GHAS Trial Survey Links #

## What?

This action automatically creates a weblink to the GHAS trial survey. The links will be valid for 14 days by default.

## Example

```yaml
name: "Example"

on:
  workflow_dispatch:

jobs:
  analyze:
    name: Example
    runs-on: ubuntu-latest

    steps:
    - name: Create Link
      id: createlink
      uses: advanced-security/survey-link@main
      with:
        surveymonkey_token: ${{ secrets.surveymonkey_token }}
        name: acme limited

    - run: |
       echo "${{ steps.createlink.outputs.link }}"
```
