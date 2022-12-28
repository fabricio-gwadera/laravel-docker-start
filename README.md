
# Docker for Laravel

A quick start to Docker for anyone working with Laravel.



## ToDo

Para rodar esse projeto, você vai precisar adicionar as seguintes variáveis de ambiente no seu .env

### Clone the repository to a folder of your choice

`git clone https://github.com/fabricio-gwadera/laravel-docker-start.git laravel`

### Change environment variables in .env file

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=database
DB_USERNAME=username
DB_PASSWORD=password
DB_ROOT_PASSWORD=root_password
```

### Run the build on Docker

`docker-compose build`

### Start the servers in docker

`docker-compose up -d`

### Start the servers in docker

```
docker-compose exec app bash
composer require package-name
```

### Generate new APP_KEY for Laravel use
```
docker-compose exec app bash
php artisan key:generate
```

### Access your page

`http://localhost`

This container works on your hosting server too, just access your domain address normally.

The docker-compose file already contains instructions for accessing port 443 which is a security protocol (https)

### PHPMyAdmin access
`http://localhost:8080`

### Server configuration

Access SSH on Ubuntu 22.*

Update the apt package index and install packages to allow apt to use a repository over HTTPS:

`sudo apt-get update`

```
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

Add Docker’s official GPG key:

```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

Use the following command to set up the repository:

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Update the apt package index:

`sudo apt-get update`

To install the latest version, run:

`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin`