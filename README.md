# workflow-publish-public-module
Publishes a public @ilpt module to npmjs. 

This workflow is intended for infinitaslearning modules only.

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
    uses: infinitaslearning/workflow-publish-public-module/.github/workflows/publish-module.yaml@v1
    with:
      version: ${{ inputs.version }}
    secrets:
      NPMJS_ILPT_PUBLISH: ${{ secrets.NPMJS_ILPT_PUBLISH }}
```
