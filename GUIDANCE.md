# Adminer on Wodby

A database administration interface for the MariaDB, MySQL or PostgreSQL service of the environment.

## Link and login

- The required `db` link points to one database service. It sets `ADMINER_DEFAULT_DB_DRIVER`, `ADMINER_DEFAULT_DB_HOST` (host and port) and `ADMINER_DEFAULT_DB_NAME`.
- The image uses them to prefill the login form: the system, the server and the database. The user name and the password are not prefilled and are not stored in the container; they are typed in by the person logging in.
- The interface listens on port `80`.

## Configuration

Changed through environment variables on the service:

- `ADMINER_PLUGINS`: space-separated plugin names, `tables-filter edit-textarea` by default. A name that the Adminer version does not ship stops the container at start.
- `ADMINER_DESIGN`: a bundled theme.
- `PHP_UPLOAD_MAX_FILESIZE`, `PHP_POST_MAX_SIZE`, `PHP_MEMORY_LIMIT`, `PHP_MAX_EXECUTION_TIME`: limits for uploading and running SQL files.

The service has no volume: nothing it holds is persistent.

## Basic auth

Wodby protects this service's public domains with basic auth by default: each app service of it gets its own generated password, which members reveal on the environment's Endpoints > Auths page. Services inside the environment reach it directly, without the password. The protection can be switched off when the app is created, or later by deleting the entry; a stack can also turn the default off.
