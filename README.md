# LibreCheck documentation

This website is built using [Docusaurus](https://docusaurus.io/), a modern static website generator.

## Installation

### Using Dev Containers (Recommended)

This project includes a development container configuration that provides a consistent, pre-configured development environment.
To use it, you'll need [Visual Studio Code](https://code.visualstudio.com/)
with the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) and a container runtime, such as [Docker](https://www.docker.com/) or [Podman](https://podman.io/), installed on your machine.

Once set up, open the project folder in VS Code and click "Reopen in Container" when prompted (or use the Command Palette: `Dev Containers: Reopen in Container`).
The devcontainer will automatically install all dependencies including Node.js, npm, TypeScript, and other required tools, ensuring you have everything needed to start developing immediately without manual setup.

### Manual Installation

```bash
npm install
```

## Local Development

```bash
npm start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

## Build

```bash
npm build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

## Deployment

Using SSH:

```bash
USE_SSH=true npm deploy
```

Not using SSH:

```bash
GIT_USER=<Your GitHub username> npm deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.
