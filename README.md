# Mono helps to manage your PHP Mono Repositories

Managing a monorepository?

Mono helps you to run composer and other commands for all your package directories.

## Installation

```bash
composer require schranz/mono --dev
```

## Usage

Mono does search for all the directories containing a `composer.json` 
and does run the given command in all of them.

To install the dependencies of all your mono repositories, just run:

```bash
vendor/bin/mono composer install
```

To update them run:

```bash
vendor/bin/mono composer update
```

To run a custom custom composer script use:

```bash
vendor/bin/mono composer fix # runs in my case rector + php-cs-fixer

vendor/bin/mono composer lint # runs in my case various linters (phpstan, php-cs, ...)
```

Mono is used and was build for managing [schranz-search monorepository](https://github.com/schranz-search/schranz-search).
