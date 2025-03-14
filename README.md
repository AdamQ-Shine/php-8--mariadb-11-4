# Setup Guide

Follow these steps to set up PrestaShop in your Docker environment:

### 1. Create project & clone the repository
Create a folder with the name of your project.
Go in then run `git clone https://github.com/AdamQ-Shine/php-8--mariadb-11-4`


### 2. Download PrestaShop
Download the desired version of PrestaShop from the [official releases page](https://github.com/PrestaShop/PrestaShop/releases).


### 3. Extract the PrestaShop Files
Unzip the `prestashop.zip` file (found inside the downloaded `prestashop_x.x.x.zip`) directly into the project’s root directory.

Desired result: a folder named "prestashop" (important) at project's root, containing the Prestashop installation files.


### 4. Configure PHP Settings
Ensure that the `php.ini` file located at the project's root meets PrestaShop's system requirements based on your environment.


### 5. Set File Permissions
Verify that the necessary folders and files have the correct permissions:
- They should be **readable**, **writable**, and **executable** by both your host user and the `www-data` group (used by the web server).
- It's recommended to grant ownership to your host user and add the user to the `www-data` group for easier management.


### 6. Ensure Inherited Ownership
Make sure that new files created within the PrestaShop directory inherit the correct group ownership (`www-data`).

This can be achieved by applying the proper permissions and ownership rules.


### 7. Build and Start Docker Containers
You probably want to replace the placeholder credentials set in docker-compose.yml before.

Once ready, run the Docker setup:
- Build the containers using `docker-compose build`.
- Start the containers using `docker-compose up -d`.


### 8. Install PrestaShop
Once the containers are running, access PrestaShop by navigating to [localhost:8080](http://localhost:8080) in your web browser.

Follow the on-screen instructions to complete the PrestaShop installation.

Note: when you're asked for database credentials, set "mariadb" as the host instead of the default localhost, since PrestaShop is running inside a container and must connect to the database container.
