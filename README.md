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
    uses: infinitaslearning/workflow-publish-public-module/.github/workflows/publish-module.yml@v1
    with:
      version: ${{ inputs.version }}
    secrets: inherit
```
