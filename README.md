# Init project

`./composer create-project "symfony/skeleton" api`
cd api

# Setup API

`./composer req api`

Do not forget to change the Database URL in `.env`.

# Create database

## Implement Hello Entity (and API resource)

## Init the database

./bin/console doctrine:database:create
./bin/console doctrine:schema:create

# Web server

## Install Symfony web server

./composer req server

## Start

./bin/console server:start
