# Les Commandes SQL

SQL fournit plusieurs commandes permettant de manipuler les données:

- `SELECT` : sélectionner des données issues de la base de données.
- `INSERT` : ajouter de nouvelles lignes a une table.
- `UPDATE` : changer des valeurs d'attributs de lignes existantes.
- `DELETE` : enlever des lignes dans une table.

## Fonctions de calculs

SQL fournit des fonctions de calcul operant sur I'ensemble des valeurs d'une colonne de table. Elle comporte plusieurs parties:

- `COUNT` : nombre de valeurs
- `SUM` : somme des valeurs
- `AVG` : moyenne des valeurs
- `MAX` : plus grande valeur
- `MIN` : plus petite valeur

On peut faire précéder I'argument du mot cle `DISTINCT` pour indiquer que les valeurs redondantes doivent être éliminées avant application de la fonction.

La fonction spéciale `COUNT` compte toutes les lignes dans une table. Les valeurs nulles ne sont pas prises en compte, sauf pour `COUNT(*)`.

## MySQL using MariaDB

```sh
sudo mysql -u root

# in mysql
SHOW DATABASES;

# create database
CREATE DATABASE db_name;

# create user
CREATE USER username@localhost IDENTIFIED BY 'password';
# check creation
SELECT User FROM mysql.user;

GRANT ALL PRIVILEGES ON db_name.* TO 'username'@'localhost';
exit

# load old database
mysql -u root db_name < save.sql

# verify
mysql -u root db_name -e "SHOW TABLES;"
```

> - replace `db_name`, `username`, `password`

## MySQL docker

```sh
# remove docker if exists
docker rm --force docker-mysql

docker run --name docker-mysql -d -p 3306:3306 \
-e MYSQL_ROOT_PASSWORD="random-root-password" \
-e MYSQL_DATABASE="DATABASE_NAME" \
-e MYSQL_USER="username" \
-e MYSQL_PASSWORD="password" \
-v $(pwd)/save.sql:/docker-entrypoint-initdb.d/dump.sql \
mysql:latest
```

> - replace `DATABASE_NAME`, `username`, `password` (and `random-root-password`)
> - or you can use `-e MYSQL_ROOT_PASSWORD="$(openssl rand -base64 42)"` to have a random password
> - `docker-mysql` is the name of the docker
> - [hub.docker.com -mysql](https://hub.docker.com/_/mysql)
> - more info on docker at [/golb/docker](https://its-just-nans.github.io/golb/docker)

## PostgreSQL commands

```plaintext
\l to list databases
\c database to change database
\dt to list tables
\d table to show details about a table

EXPLAIN ... -- plan
EXPLAIN ANALYZE ... -- time
```
