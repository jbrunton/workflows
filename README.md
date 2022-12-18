# workflows

Shared GitHub workflows

## build-image

Builds a Docker image using `paketobuildpacks/builder:base`.

Example usage:

```yml
jobs:

  build:
    uses: jbrunton/workflows/.github/workflows/build-image.yml@develop
    with:
      repo-name: jbrunton/my-image
      working-directory: api
      publish: true
      docker-username: jbrunton
    secrets:
      docker-access-token: ${{ secrets.DOCKER_ACCESS_TOKEN }}
```

See the [workflow definition](https://github.com/jbrunton/workflows/blob/develop/.github/workflows/build-image.yml) for more details on the inputs and outputs.
