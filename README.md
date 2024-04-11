# PHP Elastic Nomad

[![Latest Version](https://img.shields.io/github/v/release/not-empty/elastic-nomad-php.svg?style=flat-square)](https://github.com/not-empty/elastic-nomad-php/releases)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square&label=PRs%20Welcome)](http://makeapullrequest.com)

PHP script to execute Elasticsearch backups and restorations using S3.

### Installation

[Release 1.0.0](https://github.com/not-empty/elastic-nomad-php/releases/tag/1.0.0) Requires [PHP](https://php.net) 7.3

[Release 2.0.0](https://github.com/not-empty/elastic-nomad-php/releases/tag/2.0.0) Requires [PHP](https://php.net) 7.4

### Sample

it's a good idea to look in the sample folder to understand how it works.

First you need to building a correct environment to install dependences

```sh
docker build -t not-empty/elastic-nomad-php -f ops/docker/dev/Dockerfile .
```

Access the container
```sh
docker run -v ${PWD}/:/var/www/html -it not-empty/elastic-nomad-php bash
```

Verify if all dependencies is installed (if need anyelse)
```sh
composer install --no-dev --prefer-dist
```

and run
```sh
php index.php {operation} {param}
```

### Development

Want to contribute? Great!

The project using a simple code.
Make a change in your file and be careful with your updates!
**Any new code will only be accepted with all viladations.**

To ensure that the entire project is fine:

First you need to building a correct environment to install/update all dependences
```sh
docker build -t not-empty/elastic-nomad-php -f ops/docker/dev/Dockerfile .
```

Access the container
```sh
docker run -v ${PWD}/:/var/www/html -it not-empty/elastic-nomad-php bash
```

Install all dependences
```sh
composer install --dev --prefer-dist
```

Run all validations
```sh
composer check
```

### Backup
If you want to run a backup you can run the command:

```sh
php index.php backup {param}
```

In the backup command the {param} is the name of the index.

### Restore
If you want to restore your data in the elastic, you can run the command:

```sh
php index.php restore {param}
```

In the restore command the {param} is the name of the txt file located on storage/restore.


If you want to check if your data is on the elastic, you can use the collection available on /ops/collections.

**Not-empty - Open your code, open your mind!**