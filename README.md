# A simple Payara + Postgres sample

## Usage 
 
To start payara (apps on host port 8080, web admin on host port 4848) 
and postgresql (host port 5432)

  ```bash
  docker compose up -d
  ```

## Configuration

payara configuration is done in `mypayara-full/post-boot-commands.asadmin`.
