# workflows

Shared GitHub workflows

## build-image

Builds a Docker image using `paketobuildpacks/builder:base`.

Example usage:

```yml
jobs:

  build:
    uses: jbrunton/workflows/.github/workflows/build-image.yml@v1
    with:
      repo-name: jbrunton/my-image
      buildpack: paketo-buildpacks/nodejs
      working-directory: api
      publish: true
      docker-username: jbrunton
    secrets:
      docker-access-token: ${{ secrets.DOCKER_ACCESS_TOKEN }}
```

See the [workflow definition](https://github.com/jbrunton/workflows/blob/develop/.github/workflows/build-image.yml) for more details on the inputs and outputs.

## tag-release

Updates major release tags (e.g. `v1`) from semantic release tags (e.g. `v1.2.3`).

Example usage:

```yml
jobs:

  build:
    uses: jbrunton/workflows/.github/workflows/tag-release.yml@v1
    with:
      user-name: ci-user
      user-email: ci-user@example.com
```

See the [workflow definition](https://github.com/jbrunton/workflows/blob/develop/.github/workflows/tag-release.yml) for more details on the inputs and outputs.
