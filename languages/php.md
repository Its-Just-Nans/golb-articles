# PHP

## How to print and get errors

```php
ini_set('display_errors', '1');
ini_set('display_startup_errors', '1');
error_reporting(E_ALL);

//code here
```

Reference : [stackOverflow](https://stackoverflow.com/questions/1053424/how-do-i-get-php-errors-to-display)

## Start a simple PHP local server

```sh
# only localhost !
php -S localhost:8080
# for external access
php -S 0.0.0.0:8080
# or
php -S 0:8080
```

> Caption:
>
> `-S <addr>:<port>` :  Run with built-in web server

## phpMyAdmin - simple usage

```sh
cd /usr/share/phpmyadmin/
# or clone the repo
# then start a php web server
php -S localhost:8080
```
