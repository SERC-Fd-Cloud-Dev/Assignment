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

## Additional Information

Add any environment prerequisites, startup steps, credentials guidance, or troubleshooting notes here.
