# Adminer service for Kubernetes on Wodby

This repository defines the Wodby Adminer service. It provides a lightweight database administration interface for linked MariaDB, MySQL, and PostgreSQL services.

The service preselects the linked database host and database name but never injects database credentials. Users authenticate with the database account in Adminer.

Adminer is included as a disabled component in the managed MariaDB and PostgreSQL stacks and can also be referenced from custom stacks.

Validate the manifest with:

```bash
wodby service validate-manifest service.yml --org <org-id>
```
