## Docker compose for PrestaShop

A little docker-compose to setup a dockerized prestashop in no time.

The docker-compose will launch two containers, a _mysql_ and the [official prestashop docker image](https://hub.docker.com/r/prestashop/prestashop/).

Two volumes are used to persist your installation:

* `www`: contains the prestashop source;
* `db-data`: contains the mysql database files. 

## Usage

```sh
git clone git@github.com:derlin/prestashop-docker-compose.git
cd prestashop-docker-compose
docker-compose up -d
```

Then, go to [http://localhost](http://localhost) and follow the PrestaShop setup wizard.

To stop it, use:

```
docker-compose down
```

Data will be persisted between ups/downs thanks to the two volumes.

## Other tips

* To change the port of the prestashop, see the _prestashop > ports_ section in  `docker-compose.yaml`;
* To ssh into the prestashop container, use `docker exec -it prestashop_www_1 bash`. For mysql, replace `prestashop_www_1` by `prestashop_db_1`;


