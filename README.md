# GitHub Action to Check if Docker Image Tag Exists

## Usage

```yaml
on: [push]

jobs:
  github_latest_release_job:
    runs-on: ubuntu-latest
    steps:
      - id: check-docker-image-tag
        uses: razonyang/github-action-docker-image-tag-exists@v1
        with:
          owner: hugomods
          name: hugo
          tag: '0.128.0'
      - if: ${{ steps.check-docker-image-tag.outputs.exists }}
        run: echo "image tag exists"
```
