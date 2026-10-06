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
