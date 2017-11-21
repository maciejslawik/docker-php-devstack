# PHP7 with xdebug + Nginx + MySQL + PostgreSQL + ElasticSearch + Redis + MongoDB + RabbitMQ #

PHP7 development environment with xdebug, Nginx
web server, MySQL, PostgreSQL and ElasticSearch.
It uses docker-compose v3.

### Installation ###

1. Simply put contents of this repository in
the root of your project
2. Configure the ``` docker/.env ``` file
3. Run ``` docker-compose up -d ```

#### MySQL ####

Configuration can be changed using 
``` docker/mysql/my.cnf ```
By default the data is stored in a named
container. You can change it to store
the data in a visible directory,
e.g. ``` docker/data/mysql ```

#### PostgreSQL ####

By default the data is stored in a named
container. You can change it to store
the data in a visible directory,
e.g. ``` docker/data/postgresql ```

#### Nginx ####

Vhost configuration can be changed using 
 ``` docker/vhost/vhost.conf ```
 
#### Redis ####

By default the data is stored in a named
container. You can change it to store
the data in a visible directory,
e.g. ``` docker/data/redis ``` 

#### MongoDB ####

By default the data is stored in a named
container. You can change it to store
the data in a visible directory,
e.g. ``` docker/data/mongodb ``` 

#### Elasticsearch ####

By default the data is stored in a named
container. You can change it to store
the data in a visible directory,
e.g. ``` docker/data/elasticsearch ``` 

#### RabbitMQ ####

RabbitMQ is available via web management console
and from PHP container using ports defined in
environment variables.