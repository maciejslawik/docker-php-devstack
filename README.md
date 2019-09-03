# PHP with xdebug + (almost) anything you need #

PHP development environment with xdebug.
Other services include:
* Apache
* Nginx
* Varnish
* MySQL
* PostgreSQL
* RabbitMQ
* ElasticSearch
* Redis
* Selenium
* Adminer
* MongoDB
* Varnish

It uses docker-compose v3.7.

### Installation ###

1. Simply put contents of this repository in
the root of your project
2. Configure the ``` .env ``` file
3. Configure ```docker-compose.yml``` to use only the services you need
4. Run ``` docker-compose up -d ```


#### PHP ####
Supported versions: 5.6, 7.0, 7.1, 7.2

##### Emails #####
To enable sending emails using ssmtp you need to adjust configuration in
```docker/php/ssmtp.conf``` with your email relay configuration, e.g. for Gmail.

Under ```hostname``` you need to place the hostname of your PHP container. To get it use
the following command after running docker-compose and remember that the hostname of 
a container changes everytime you destroy a container.

``
docker-compose exec php hostname
``

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

#### Varnish ####
Vcl configuration can be changed using
``` docker/varnish/default.vcl ```

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

#### Blackfire.io ####

You have to set up environment variables for Blackfire
to be able to profile your app. You can profile the app
using web interface (Chrome extension) or via CLI using
```blackfire``` executable inside the PHP container.

## Docker
Useful Docker and Docker-compose commands
```
docker-compose up    - starts containers
docker-compose up -d    - starts containers in background (without showing logs)
docker-compose ps    - lists all containers in current directory
docker-compose stop    - stops all containers in current directory
docker-compose down    - stops and destroys all containers in current directory

docker-compose exec <<container_name>> bash    - logs into container as www-data
docker-compose exec -u root <<container_name>> bash    - logs into container as root
```

Make sure to always run PHP commands inside PHP container as www-data - this way you will
not encounter file permission problems.