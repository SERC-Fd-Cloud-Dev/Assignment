# Assignment

Development environment for assignment with preconfigured devcontainer for API work.

## Getting Started

### Using GitHub Codespaces
Click the green **Code** button → **Codespaces** tab → **Create codespace** to start developing in the cloud with all tools preconfigured.

### Using VS Code Dev Containers (Local)
1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop) and [VS Code](https://code.visualstudio.com/)
2. Install the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
3. Clone this repository and open in VS Code
4. Click **Reopen in Container** when prompted

For detailed information about the devcontainer configuration, see [codespaces.md](codespaces.md).

## Adding Your Existing Code

### Option 1: Copy Files into This Repository
1. Clone this repository
2. Copy your existing project files into the cloned directory
3. Commit and push your changes:
   ```bash
   git add .
   git commit -m "Add existing project files"
   git push
   ```

### Option 2: Merge Another Repository
To merge an existing repository into this one while preserving its history:

```bash
# Clone this repository
git clone <this-repo-url>
cd <repository-name>

# Add your existing repository as a remote
git remote add existing-repo <your-existing-repo-url>

# Fetch the existing repository's content
git fetch existing-repo

# Merge the existing repository (allow unrelated histories)
git merge existing-repo/main --allow-unrelated-histories

# Resolve any merge conflicts if they occur
# Then commit and push
git push origin main
```

**Note**: Replace `main` with the appropriate branch name if different.

### Option 3: Import via GitHub
1. Go to GitHub repository settings
2. Navigate to the **Import code** option
3. Follow GitHub's import wizard to bring in code from another repository

## Development Environment

This repository includes a devcontainer configuration optimized for API development with:
- Node.js and Python support
- Docker-in-Docker capability
- API testing tools (REST Client, Thunder Client)
- OpenAPI/Swagger support
- Pre-configured port forwarding (3000, 5000, 8000, 8080)

See [codespaces.md](codespaces.md) for complete details on the development environment setup.
