# How to run a simple PostGis Tileserver

TODO: What is PostGis
TODO: What is a Tileserver

## Assumption

- Ubuntu ...
- something else?

## Docker postgis

```sh
docker run --name some-postgis -p 5433:5432 -e POSTGRES_PASSWORD=postgres -d postgis/postgis
```

### Verifying it works

connect with psql

## Preparing the database

```sh
psql --host=localhost --port=5433 --username=postgres
```

```
CREATE DATABASE osm;
```

and then those extensions (TODO: why?)

```
CREATE EXTENSION postgis;

CREATE EXTENSION postgis_topology;

CREATE EXTENSION hstore;
```

## Inserting the data


```sh
./osm2pgsql --host localhost --port 5433 --username postgres -W -d osm --style=streets.lua -O flex da0875e7-5909-4f02-8d3d-8990c898d8de.osm.pbf
```

## Serving with pg_tileserv

```sh
 export DATABASE_URL=postgresql://postgres:postgres@localhost:5433/osm
 ./pg_tileserv
 ```
 
 -> 
  
 ```sh
INFO[0000] pg_tileserv latest
INFO[0000] Run with --help parameter for commandline options
INFO[0000] Using database connection info from environment variable DATABASE_URL
INFO[0000] Serving HTTP  at http://0.0.0.0:7800/
INFO[0000] Serving HTTPS at http://0.0.0.0:7801/
INFO[0000] Using CoordinateSystem.SRID 3857 with bounds [-2.00375083427892e+07, -2.00375083427892e+07, 2.00375083427892e+07, 2.00375083427892e+07]
INFO[0000] Connected as 'postgres' to 'osm' @ 'localhost'
INFO[0000] Serving HTTP  at 0.0.0.0:7800
```



[Based in this example](https://osm2pgsql.org/examples/vector-tiles/)

Open Webbrowser at 0.0.0.0:7800



