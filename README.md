# Flask App with MySQL – CI/CD Pipeline (GitHub Actions)

# 📌 What the App Does

This is a simple Flask web application backed by a MySQL database.

The app allows users to submit text messages.

Messages are stored in a MySQL database.

On startup, the app automatically initializes the database and creates the required table if it does not exist.

The home page retrieves and displays all stored messages.

The purpose of the application is not feature complexity, but to act as a realistic service that depends on an external database, similar to real-world cloud applications.

# ⚙️ What the Pipeline Does

The GitHub Actions CI pipeline automates validation and testing of the application.

On each push to the main branch or manual trigger, the pipeline:

Checks out the source code

Sets up a Python environment

Installs application dependencies

Provision a MySQL service container for testing

Injects configuration via environment variables

Waits for the database to become available

Initializes the database schema

Starts the Flask application

Performs a basic smoke test to confirm the app is running successfully

This demonstrates a complete CI workflow with service dependencies, automation, and validation.

# 🔐 Why Services and Secrets Are Used
GitHub Actions Services

The pipeline uses GitHub Actions services to run MySQL as a containerized dependency during CI.

This allows the application to:

Be tested against a real database

Avoid using shared or external infrastructure

Run in a fully isolated and repeatable environment

This mirrors how applications depend on managed services in real cloud environments.

# GitHub Secrets

Sensitive information such as database credentials are stored using GitHub Secrets.

This ensures:

Credentials are never hardcoded in source code

Secrets are encrypted and masked in logs

Configuration follows 12-factor app principles

Secrets are injected into the pipeline as environment variables at runtime, which is the same pattern used in production cloud deployments.

# 🎯 Project Goal

The primary goal of this project is to showcase:

CI/CD automation using GitHub Actions

Secure handling of secrets

Service dependency management

Environment-based configuration

Practical DevOps workflows

The Flask application serves as a realistic example to demonstrate these concepts rather than being the main focus of the project.

# 🧠 Skills Demonstrated

GitHub Actions CI/CD

Python application automation

MySQL service orchestration

Secure secret management

Cloud-ready configuration practices

Debugging CI environment issues
