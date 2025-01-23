# Example PostgreSQL Docker Compose with Database Creation

This repository demonstrates how to set up a PostgreSQL environment using Docker Compose, including the execution of database initialization scripts upon startup.

<img src="https://upload.wikimedia.org/wikipedia/commons/2/29/Postgresql_elephant.svg" alt="PostgreSQL Logo" width="200" />

## Repository Contents

- `docker-compose.yml`: Defines the Docker services, including the PostgreSQL database service.
- `01-basegeografica.sql` and `02-basegeografica.sql`: SQL scripts intended for database initialization.

## Usage

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/altairlage/example-postgres-docker-compose-with-db-creation.git
   cd example-postgres-docker-compose-with-db-creation
   ```

2. **Start the Services**:

   <img src="https://miro.medium.com/v2/format:webp/0*lQHBTNViWBhPsTtF." alt="Docker Compose Logo" width="300" />

   Use Docker Compose to build and start the services defined in `docker-compose.yml`:

   ```bash
   docker-compose up -d
   ```

   This command will set up the PostgreSQL container and execute the provided SQL scripts to initialize the database.

3. **Access the PostgreSQL Database**:

   Once the services are running, you can connect to the PostgreSQL database using a client of your choice. The default connection parameters are:

   - **Host**: `localhost`
   - **Port**: `5432`
   - **User**: `postgres`
   - **Password**: `your_password`
   - **Database**: `your_database`

   Ensure that the credentials match those specified in your `docker-compose.yml` file.

## Customization

To modify the database initialization process:

- **SQL Scripts**: Place your custom SQL scripts in the appropriate directory as specified in the `docker-compose.yml` file. These scripts will be executed in alphabetical order during the container's initialization phase.

- **Environment Variables**: Adjust the environment variables in the `docker-compose.yml` file to set your desired PostgreSQL user, password, and database name.

## Notes

- **Initialization Behavior**: The SQL scripts are executed only when the PostgreSQL data directory is empty. If the data directory already contains data (i.e., the database has been initialized previously), the initialization scripts will be ignored.

- **Persistence**: The PostgreSQL data is stored in a Docker volume as defined in the `docker-compose.yml` file. This ensures that your data persists across container restarts.

## References

- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [PostgreSQL Official Docker Image](https://hub.docker.com/_/postgres)

For more detailed information, please refer to the official documentation of Docker Compose and PostgreSQL.
