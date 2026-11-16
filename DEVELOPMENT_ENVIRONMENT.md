# Development Environment

TODO: update with features and usage instructions for the development environment provided with the assignment.

## Features

- **VS Code Dev Container:** Uses the `cloud-dev-assignment` development container image.
- **Database tooling:** Includes SQLTools connection profiles for MariaDB, PostgreSQL, Microsoft SQL Server, and SQLite.
- **Forwarded ports:** PostgreSQL (`5432`) and Redis (`6379`) ports are forwarded from the container.

## Database and Cache Defaults

- **PostgreSQL**
  - Host: `localhost`
  - Port: `5432`
  - Username: `postgres`
  - Password: `P@ssw0rd`
  - Database: `postgres`
  - Connection string: `postgresql://postgres:P%40ssw0rd@localhost:5432/postgres`
- **SQLite**
  - Database file: `database.sqlite` in the workspace root
  - SQLite runs as a local file, so it does not use a host, port, username, or password.
  - Connection string: `sqlite:///database.sqlite`
- **Redis**
  - Host: `localhost`
  - Port: `6379`
  - No username or password configured by default.
  - Connection string: `redis://localhost:6379`

## Starting Services

Use the **Services Manager** extension in VS Code to start the services you need:

1. Open **Services Manager** from the VS Code Activity Bar.
2. Select **Start** for PostgreSQL and/or Redis.
3. Wait for the service status to show that it is running, then connect using the settings above.

Additional services can be added using the **Add Service** button in the Services Manager. You can also stop services when they are not needed to free up resources.

SQLite is a local database file, so it does not need to be started as a service.

## Troubleshooting

- **The Dev Container will not start:** For a local setup, make sure Docker Desktop (or another compatible container engine) is running and VS Code has the Dev Containers extension installed. In GitHub Codespaces, Docker Desktop is not needed; check that the Codespace has finished starting. If the image fails to download, check network access to GitHub Container Registry.
- **Development tools or settings seem missing:** Confirm the workspace is open inside the Dev Container, not just in a local VS Code window. Rebuild the container if its setup or image has changed.
- **A forwarded service port is unavailable:** Check the VS Code Ports view to confirm the port is forwarded, and make sure another process on your computer is not already using it.
- **PostgreSQL authentication fails:** Check the username (`postgres`), database (`postgres`), and password (`P@ssw0rd`). In connection URLs, encode the `@` in the password as `%40`.
- **SQLite cannot open the database:** Confirm you have opened the assignment workspace and that its root directory is writable. The database file may be created when you first connect.
- **Redis cannot be reached:** Confirm the Dev Container is running and port `6379` is forwarded. No username or password is configured by default.
