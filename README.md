# Docker Base Image Build and Publish Action
A Composite Action that Builds and Publishes a Docker Base Image

## Inputs

### `github-token`

**Required** The GitHub Token used to Generate a Changelog and Create Releases

### `docker-image-name`

**Required** The Name of the Docker Image being Built

### `docker-image-platforms`

_Optional_ The Platforms that the Docker Image should be built for as a comma-separated list (e.g. linux/amd64,linux/arm64,linux/arm/v7)

Defaults to `linux/amd64`

### `dockerfile-path`

_Optional_ Path to the Dockerfile used to Build the Docker Image (e.g. ./ProjectFolder/Dockerfile)

Defaults to `./Dockerfile`

### `docker-hub-username`

**Required** Username to Authenticate with Docker Hub

### `docker-hub-password`

**Required** Password to Authenticate with Docker Hub

## Outputs

### `changelog`

A Markdown formatted changelog

## Example Usage

```yml
uses: ricado-group/docker-base-image-build-action@v1
with:
  github-token: ${{ secrets.GITHUB_TOKEN }}
  docker-image-name: MyDockerImage
  docker-hub-username: ${{ secrets.DOCKER_USERNAME }}
  docker-hub-password: ${{ secrets.DOCKER_PASSWORD }}
```

## Stay Updated with Dependabot

Use [Dependabot](https://docs.github.com/en/github/administering-a-repository/keeping-your-actions-up-to-date-with-github-dependabot) to update your GitHub Actions by creating a `.github/dependabot.yml` file:

```yaml
version: 2
updates:
  # Maintain Dependencies for GitHub Actions
  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "daily"
```