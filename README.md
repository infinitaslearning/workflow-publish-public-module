# workflow-publish-public-module
Publishes a public @ilpt module to npmjs

## Usage

```yaml
name: Publish Module
on:
  workflow_dispatch:
    inputs:
      version:
        description: "Type of version bump for this release."
        required: true
        default: patch
        type: choice
        options:
          - major
          - minor
          - patch

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - publish:
        uses: infinitaslearning/workflow-ci/.github/workflows/publishmodule@v1
        with:
          version: ${{ inputs.version }}
        secrets: inherit
```
