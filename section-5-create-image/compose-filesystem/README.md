Normaly, it's called "BIND VOLUME"

This docker-compose.yml file configures two services: a PostgreSQL database and pgAdmin for managing the database, similar to the previous example but with a key difference: local filesystem persistence. Here's a breakdown:

PostgreSQL service (db):

Runs a PostgreSQL container (postgres:15.1 image).
Stores database data in the local folder ./postgres on the host machine, mapped to the container's /var/lib/postgresql/data. This provides persistent storage tied to the local filesystem.
Requires a password (POSTGRES_PASSWORD=123456) for database access.
pgAdmin service (pgAdmin):

Runs a pgAdmin container (dpage/pgadmin4:6.17 image) for managing the database.
Exposes pgAdmin on port 8080 of the host machine.
Stores pgAdmin data (e.g., configurations) in the local folder ./pgadmin on the host machine, mapped to the container's /var/lib/pgadmin.
Uses environment variables to set the default email and password for pgAdmin access.
