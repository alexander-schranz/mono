# Mono helps to manage your PHP Mono Repositories

Managing a monorepository?

Mono helps you to initialize subtree split and run composer and other commands for all your package directories.

## Installation

```bash
composer require schranz/mono --dev
```

## Usage

## Init Split Command

First create your mono repository and push it to Github.

Create your packages into different directories make sure
for to create for all packages you want to split a `composer.json` with a `name` in it.

Then run:

```bash
vendor/bin/mono init-split
```

It will create the configuration for [frankdejonge/use-subsplit-publish](https://github.com/frankdejonge/use-subsplit-publish)
Github Action. Make sure to configure your `PERSONAL_ACCESS_TOKEN` as a secret in your Github repository.
And configure the user in the newly created `.github/workflows/publish-subsplits.yml` file.

## Run Command

To install the dependencies of all your mono repositories, just run:

```bash
vendor/bin/mono run composer install
```

To update them run:

```bash
vendor/bin/mono run composer update
```

To run a custom custom composer script use:

```bash
vendor/bin/mono run composer fix # runs in my case rector + php-cs-fixer

vendor/bin/mono run composer lint # runs in my case various linters (phpstan, php-cs, ...)
```

Mono is used and was build for managing [schranz-search monorepository](https://github.com/schranz-search/schranz-search).

## Upgrade dependency

If you have one dependency used in multiple packages and want to upgrade it in all packages you can use:

```bash
vendor/bin/mono upgrade-dependency phpstan/phpstan
```

Mono search for all packages which has then `phpstan/phpstan` in it and update it to the latest stable version.

## Projects using mono

 - [schranz-search](https://github.com/schranz-search/schranz-search)
 - [modelflow-ai](https://github.com/modelflow-ai/.github)

Let me know via [an issue](https://github.com/alexander-schranz/mono) if you are using mono.
