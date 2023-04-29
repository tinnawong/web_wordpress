# Wordpress Website

This website is developed using the Wordpress framework, MySQL, and PHPMyAdmin.

## Install prerequisites

Before installing the system, make sure you have installed the following software:

- [Git](https://git-scm.com/downloads)
- [Docker](https://docs.docker.com/engine/installation/)

## Run the application on local

#### 1. Open the cloned project directory

```sh
cd project_path
```

#### 2. Edit Environment Variables (.env)

You can edit the environment variables in the `.env` file as follows:

- `MYSQL_ROOT_PASSWORD` : the root password for MySQL
- `MYSQL_DATABASE` : the name of the database
- `MYSQL_USER` : the name of the MySQL user
- `MYSQL_PASSWORD` : the password for the MySQL user

#### 3. Run Docker Compose

```sh
docker-compose up -d
```

You can adjust the mount volume configuration and ports to suit your machine as follows:

| Container  | Port |
| ---------- | ---- |
| db         | 3306 |
| wordpress  | 5005 |
| phpmyadmin | 5001 |

#### 4. Import Database
1. Access PHPMyAdmin via `http://localhost:5001`
2. Log in using `MYSQL_USER` and `MYSQL_PASSWORD` as configured.
3. Import the database, and name it `wordpress`.

**If you change the port or deploy to production some, you need to modify the URL address in the database as follows:**

1. Select the `wp_options` table.
2. Edit the option_value of `siteurl` to the domain used.
3. Edit the option_value of `home` to the domain used.

5. Modify Upload Folder Permissions (For Production Deployment)

1. Select the `wordpress_data/wp-content/uploads` folder.
2. Change the permissions to `777`.