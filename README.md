# WordPress Project with Docker Compose

This README provides a comprehensive guide to setting up a WordPress environment using Docker Compose and `@wordpress/env` for development purposes.

## Prerequisites

Before you begin, ensure you have Docker installed on your system. You can download it from [Docker's official website](https://www.docker.com/products/docker-desktop). Additionally, you'll need Node.js and npm installed to use `@wordpress/env`. Download Node.js from [here](https://nodejs.org/).

## Setting up WordPress with Docker Compose

The provided `docker-compose.yml` file sets up a WordPress site with a separate MySQL database.

### 1. Docker Compose Configuration

The `docker-compose.yml` file contains the configuration for the WordPress and MySQL services:

- **MySQL Service**: Uses the `mysql:5.7` image and stores data in a named volume (`db_data`). The environment variables `MYSQL_DATABASE`, `MYSQL_ROOT_PASSWORD` specify the database name and root password, respectively.
  
- **WordPress Service**: Depends on the MySQL service. It uses the `wordpress:latest` image and maps port `8000` of the host to port `80` of the container. Environment variables are used to configure the database connection.

### 2. Running the Environment

To start your WordPress environment, navigate to the directory containing your `docker-compose.yml` file and run:

```bash
docker-compose up -d
This command starts the containers in the background. You can access your WordPress site by navigating to http://localhost:8000 in your web browser.

Setting up @wordpress/env
The @wordpress/env package provides a simple method to set up a WordPress development environment. It requires Node.js and npm.

Installing @wordpress/env
Install @wordpress/env globally using npm:

bash
Copy code
npm install -g @wordpress/env
Running @wordpress/env
Navigate to your WordPress project's directory and run:

bash
Copy code
wp-env start
This command starts a WordPress environment based on the configuration found in .wp-env.json in the current directory. If a .wp-env.json file does not exist, wp-env will attempt to start the environment based on the contents of the directory.

Important Notes
The docker-compose environment and @wordpress/env serve similar but distinct purposes. docker-compose is more flexible and allows for custom configurations, while @wordpress/env provides a quick and easy way to set up a standard WordPress development environment.
You might use docker-compose for more complex setups or when integrating with other services, and @wordpress/env for plugin or theme development.
Troubleshooting
If you encounter database connection errors, ensure the environment variables in docker-compose.yml match the credentials expected by WordPress.
If wp-env start does not work as expected, verify that you have Node.js and npm correctly installed and that @wordpress/env is installed globally.
For more information on @wordpress/env, check out the official documentation.