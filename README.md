# devcontainers

Development environments in Docker containers. Inspired by
[microsoft/vscode-dev-containers][vsc-github-url].

## Usage

The [`containers`](containers/) folder holds reusable container definitions.
Copy the `.devcontainer` folder from one of the containers definitions to use in
your project. Then open the project using VS Code's Remote Containers extension.

## How it works

### What [microsoft/vscode-dev-containers][vsc-github-url] does

VS Code publishes several container definitions using the
[Microsoft Container Registry](https://mcr.microsoft.com/v2/_catalog) (images
prefixed with `vscode/devcontainers`). The GitHub repository
[microsoft/vscode-dev-containers][vsc-github-url] uses these published images in
the `.devcontaioner/Dockerfile` files for each container definition (in the
`FROM` expression).

The images published to the Microsoft Container Registry are built from
non-Microsoft Docker images using the `base.Dockerfile` files in the
aforementioned GitHub repository.

[vsc-github-url]: https://github.com/microsoft/vscode-dev-containers

### What this repository does

Rather than rely upon the Microsoft base images, this repository publishes its
own set of base Docker images using the GitHub Container Registry. Images are
published automatically using GitHub Actions. See the [`base`](base/) folder for
the Dockerfile definitions used to build these images.

The container definitions all rely upon the base images published by this
repository.
