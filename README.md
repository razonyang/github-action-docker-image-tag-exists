# GitHub Action to Check if Docker Image Tag Exists

## Usage

```yaml
on: [push]

jobs:
  check_docker_image_tag:
    runs-on: ubuntu-latest
    steps:
      - id: check-docker-image-tag # used by other steps.
        uses: razonyang/github-action-docker-image-tag-exists@v1
        with:
          owner: hugomods
          name: hugo
          tag: '0.128.0'
      - if: ${{ steps.check-docker-image-tag.outputs.exists == true }}
        run: echo "image tag exists"
      - if: ${{ steps.check-docker-image-tag.outputs.exists != true }}
        run: echo "image tag does not exist"
```
