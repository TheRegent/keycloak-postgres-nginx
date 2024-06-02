# Guide

Before you start, you need to prepare your environment:

1. Clone repository

2. Create an ssl certificate for your domain
```sudo certbot certonly --standalone -d <domain>```

3. Replace the domain with your own in nginx.conf
```sed -i "s/34.132.255.41.sslip.io/<domain>/g" nginx.conf```

4. Fill in the variables in .env

This table provides a description of the environment variables used in the project.

| Variable Name              | Description                                         |
|----------------------------|-----------------------------------------------------|
| `DB_VENDOR`                | The type of database being used (e.g., `postgresql`, `mysql`). |
| `DB_ADDR`                  | The address of the database server.                 |
| `DB_DATABASE`              | The name of the database.                           |
| `DB_USER`                  | The username for accessing the database.            |
| `DB_PASSWORD`              | The password for accessing the database.            |
| `KEYCLOAK_ADMIN`           | The username for the Keycloak admin user.           |
| `KEYCLOAK_ADMIN_PASSWORD`  | The password for the Keycloak admin user.           |
| `KC_HOSTNAME_URL`          | The URL for the Keycloak server.                    |

5. Run docker compose
``` docker-compose up -d --build```
