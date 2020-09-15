# Website Setup

![License](https://img.shields.io/github/license/Plywoodpirate/website)
![Version](https://img.shields.io/github/v/release/Plywoodpirate/website)
![Language](https://img.shields.io/github/languages/top/Plywoodpirate/website)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)
![Deploy docker image](https://github.com/michagrandel/website-setup/workflows/Deploy%20docker%20image/badge.svg)

Bootstrap package for website projects

## Features

This project will help you to start your website project very quickly.

It will provide you with a full development environment:

* environment based on docker, composer
* ready to use for development
* provides Apache2, PHP 7.4, MariaDB 10.1 and mailcatcher
* add **Community Files**
    * Readme.md
    * Contributing.md
    * CODE_OF_CONDUCT.md
    * issue_template.md
    * PULL_REQUEST_TEMPLATE.md
* add important project files like **LICENSE**

## Getting Started

### Prepare environments

Before you can start, you might need adjust your environment. Do so by adding
a global `.env` file to your project root. Each environment in 
`/environments` can hold its own `.env` file, which might be really useful.

Please consult the [wiki](../../wiki/Getting-started) for a more detailed 
description about these `.env` files and how to set them up.

#### Mail Setup

If you use the provided [.env sample configuration](../../wiki/Getting-started#full-example-for-a-env-file) from the wiki, please adjust it
to your needs. You may want to register a free account at [mailtrap.io](https://mailtrap.io/), create an
inbox for your project and enter the username and password in the .env file accordingly.

You might choose not to use mailtrap.io at all. Just adjust the settings in the .env
file to your needs.

#### Prepare your docker to run the containers

If your host machine is running Windows or Mac, ignore this step. This is for
Linux only.

If you run Linux on your host machine, please include your user id and group id
inside of the `.env` file. Otherwise you may run into file permission problems.
Example (if your user id and group id are both 1000):

```bash
USERID=1000
GROUPID=1000
```

Please consult the [wiki](../../wiki/Getting-started) for more details.

#### Setup your MariaDB database

Enter these variables in your .env file to setup your mariadb database.
If you don't use TYPO3, you still need them to configure your docker container.

- **MariaDB Database:** TYPO3__DB__Connections__Default__dbname
- **MariaDB User:** TYPO3__DB__Connections__Default__user
- **MariaDB Password:** TYPO3__DB__Connections__Default__password

#### Further information

There are more options (optional) to configure in your `.env` file.
Please consult the [wiki](../../wiki/Getting-started) for further or 
more defailed information. 

### How to run a local development environment

Use docker-compose to fire up your local development environment:

```
docker-compose up
```

Then install your composer.json file with

```
composer install
```

If your docker container started successfully, you can access your website
at [localhost](http://localhost).

### How to use it in a extern project

You might want to use this setup in a external project, maybe even a production
environment.

You can build your Dockerfile with the github package, which will be updated
on a regular basis.

Example:

```
FROM docker.pkg.github.com/michagrandel/website-setup/website-base:apache

# add your instructions here ...
```

If you want to use the development version of that image, add `-dev` after
`apache`, e.g.


```
FROM docker.pkg.github.com/michagrandel/website-setup/website-base:apache-dev

# add your instructions here ...
```

## Customize

To customize your website setup you can edit the `composer.json` file.

If you want to customize your server settings, you may customize the `Dockerfile`
or the `docker-compose.yml`.

Please check out our [wiki](../../wiki/Getting-started) for more 
information about how to customize your setup.

## Built With

* [composer](http://getcomposer.org/) \
  *is a tool for dependency management in PHP.*
* [docker](https://www.docker.com/) \
  *is a tool to build and share containerized apps*
* [Apache 2.4](https://httpd.apache.org/) \
  *is a free and open-source cross-platform web server software*
* [PHP 7.4](https://www.php.net/) \
  *is a popular general-purpose scripting language.*
* [MariaDB 10.1](https://mariadb.org/) \
  *is one of the most popular open source relational databases*
* [Mailcatcher](https://mailcatcher.me/) \
  *catches mail and serves it through a dream*

## Contributing

First of all: Thank you very kindly for your interest in contributing to our code!

Please take a moment and read [CONTRIBUTING.md](CONTRIBUTING.md) to get you started!

## Code of Conduct

Everyone interacting in this project's codebases, issue trackers, chat rooms, and mailing lists 
is expected to follow the [Code of Conduct][code_of_conduct].

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available,
see the [releases on this repository][github-releases].

## Authors

* **Micha Grandel** - *Author and maintainer* - [Github][github]

We thank all of our [contributors][github-contributors], who participated in this project.

## License

This project is licensed under the [Apache 2.0 License](LICENSE.md).


[github]: https://github.com/Plywoodpirate
[github-releases]: https://github.com/Plywoodpirate/website-setup/releases
[github-contributors]: https://github.com/Plywoodpirate/website-setup/graphs/contributors
[gitflow]: https://danielkummer.github.io/git-flow-cheatsheet/
[gitflow-model]: http://nvie.com/posts/a-successful-git-branching-model/
[code_of_conduct]: CODE_OF_CONDUCT.md
