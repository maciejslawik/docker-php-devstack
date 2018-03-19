# PHP with xdebug + (almost) anything you need #

PHP development environment with xdebug.
Other services include:
* Apache
* Nginx
* MySQL
* PostgreSQL
* RabbitMQ
* ElasticSearch
* Redis
* Selenium
* Adminer
* MongoDB

It uses docker-compose v3.1.

### Installation ###

1. Simply put contents of this repository in
the root of your project
2. Configure the ``` docker/.env ``` file
3. Run ``` docker-compose up -d ```


#### PHP ####
Supported versions: 5.6, 7.0, 7.1, 7.2

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
 ``` docker/nginx/vhost.conf ```
 
#### Apache2 ####

Vhost configuration can be changed using 
``` docker/apache2/vhost.conf ```
 
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

#### Selenium ####

By default Selenium is included as a standalone
Firefox container. Change it to Chrome if you want.