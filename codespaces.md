# Codespaces and Dev Container Settings

This document describes the devcontainer and codespace configuration for the Assignment repository.

## Overview

This repository is configured with a development container optimized for API development work. The configuration provides a consistent, reproducible development environment that works seamlessly with both GitHub Codespaces and VS Code Dev Containers.

## Dev Container Configuration

The devcontainer is defined in `.devcontainer/devcontainer.json` and provides:

### Base Image
- **Image**: `mcr.microsoft.com/devcontainers/universal:2`
- Universal development container with pre-installed tools and runtimes

### Included Features

#### Programming Languages & Runtimes
- **Node.js** (LTS version) - For JavaScript/TypeScript API development
- **Python** (latest) - For Python-based API services
- **Git** (latest) - Version control

#### Container Tools
- **Docker-in-Docker** - Enables running and building Docker containers within the devcontainer

### VS Code Extensions

The following extensions are automatically installed to enhance API development:

#### Language Support
- `ms-python.python` - Python language support
- `ms-python.vscode-pylance` - Advanced Python IntelliSense
- `ms-python.black-formatter` - Black code formatter for Python
- `ms-vscode.vscode-typescript-next` - TypeScript and JavaScript support
- `dbaeumer.vscode-eslint` - JavaScript/TypeScript linting

#### Code Quality & Formatting
- `esbenp.prettier-vscode` - Code formatter for multiple languages

#### API Development Tools
- `humao.rest-client` - Test REST APIs directly in VS Code
- `rangav.vscode-thunder-client` - Lightweight REST API testing client
- `42crunch.vscode-openapi` - OpenAPI (Swagger) specification support

#### Container & Infrastructure
- `ms-azuretools.vscode-docker` - Docker support and management

#### AI Assistance
- `github.copilot` - AI-powered code completion
- `github.copilot-chat` - AI-powered chat assistant

### Editor Settings

The devcontainer applies the following default editor settings:

- **Format on Save**: Enabled
- **Default Formatter**: Prettier
- **Python Linting**: Enabled with Pylint
- **Python Formatting**: Black formatter
- **Default Terminal**: Bash

### Port Forwarding

The following ports are automatically forwarded for easy access to your running services:

| Port | Label       | Description                    |
|------|-------------|--------------------------------|
| 3000 | Application | Common Node.js application port |
| 5000 | API         | Common Flask/API port          |
| 8000 | Backend     | Common backend service port    |
| 8080 | Web Server  | Common web server port         |

All ports are configured to notify you when auto-forwarded.

## Using GitHub Codespaces

### Starting a Codespace

1. Navigate to the repository on GitHub
2. Click the green **Code** button
3. Select the **Codespaces** tab
4. Click **Create codespace on [branch-name]**

Your codespace will be created with all the configured tools and extensions automatically installed.

### Working in a Codespace

- All development can be done directly in the browser or in VS Code Desktop (connected to the remote codespace)
- Your code is automatically saved to the cloud
- Port forwarding is handled automatically - access your running services through the **PORTS** panel
- Terminal access is available through the integrated terminal

### Stopping and Managing Codespaces

- Codespaces automatically stop after a period of inactivity
- Manually stop a codespace from the GitHub Codespaces dashboard
- Delete unused codespaces to free up resources

## Using VS Code Dev Containers (Local)

### Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop) installed and running
- [VS Code](https://code.visualstudio.com/) installed
- [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) installed

### Opening in a Dev Container

1. Clone the repository locally
2. Open the repository folder in VS Code
3. When prompted, click **Reopen in Container**
   - Or use Command Palette (F1) → **Dev Containers: Reopen in Container**

VS Code will build the container and reopen the workspace inside it.

## Customization

### Adding Extensions

To add more VS Code extensions, edit `.devcontainer/devcontainer.json`:

```json
"customizations": {
  "vscode": {
    "extensions": [
      "existing.extension",
      "new.extension-id"
    ]
  }
}
```

### Adding Features

To add more development tools, add to the `features` section:

```json
"features": {
  "ghcr.io/devcontainers/features/feature-name:version": {
    "option": "value"
  }
}
```

Browse available features at [containers.dev/features](https://containers.dev/features).

### Forwarding Additional Ports

To forward additional ports, add them to the `forwardPorts` array:

```json
"forwardPorts": [3000, 5000, 8000, 8080, 9000]
```

### Post-Create Commands

To run commands automatically after container creation, modify the `postCreateCommand`:

```json
"postCreateCommand": "npm install && pip install -r requirements.txt"
```

## Troubleshooting

### Container fails to build
- Check Docker is running (for local dev containers)
- Verify your internet connection
- Review the build logs for specific errors

### Extensions not loading
- Rebuild the container: Command Palette → **Dev Containers: Rebuild Container**
- Verify extension IDs in devcontainer.json are correct

### Port forwarding issues
- Check if the service is actually running on the specified port
- Verify the port is included in the `forwardPorts` array
- For Codespaces, check the PORTS panel to see forwarded ports

## Resources

- [Dev Containers Documentation](https://containers.dev/)
- [GitHub Codespaces Documentation](https://docs.github.com/en/codespaces)
- [VS Code Dev Containers Extension](https://code.visualstudio.com/docs/devcontainers/containers)
