# Website Setup

![License](https://img.shields.io/github/license/michagrandel/website-setup)
![Version](https://img.shields.io/github/v/release/michagrandel/website-setup)
![Language](https://img.shields.io/github/languages/top/michagrandel/website-setup)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)

Bootstrap package for website projects

## Features

This project will help you to start your website project very quick.

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

### Prepare to start

Clone this repository into your file. Then customize the composer file as you
need it.

### How to run

Use docker-compose to fire up your development environment:

```
docker-compose up
```

Then install your composer.json file with

```
composer install
```

Now you are ready to develop your website!

## Customize

To customize your website setup you can edit the `composer.json` file.

If you want to customize your server settings, you may customize the `Dockerfile`
or the `docker-compose.yml`.

## Built With

* [composer](http://lxml.de/) \
  *is a tool for dependency management in PHP.*
* [docker](https://getcomposer.org/)\
  *is a tool to build and share containerized apps*
* [Apache 2.4](https://httpd.apache.org/)\
  *is a free and open-source cross-platform web server software*
* [PHP 7.4](https://www.php.net/)\
  *is a popular general-purpose scripting language.*
* [MariaDB 10.1](https://mariadb.org/)\
  *is one of the most popular open source relational databases*
* [Mailcatcher](https://mailcatcher.me/)\
  *catches mail and serves it through a dream*

## Contributing

First of all: Thank you very kindly for your interest in contributing to our code!

Please take a moment and read [CONTRIBUTING.md](Contributing.md) to get you started!

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available,
see the [releases on this repository][github-releases].

## Authors

* **Micha Grandel** - *Author and maintainer* - [Github][github]

We thank all of our [contributors][github-contributors], who participated in this project.

## License

This project is licensed under the Apache 2.0 License - see the [LICENSE](LICENSE.md) file for details

## Code of Conduct

Everyone interacting in the ProjectSetup project's codebases, issue trackers, chat rooms, and mailing lists 
is expected to follow the [Code of Conduct][code_of_conduct].

[github]: https://github.com/michagrandel
[github-releases]: https://github.com/michagrandel/website-setup/releases
[github-contributors]: https://github.com/michagrandel/website-setup/graphs/contributors
[gitflow]: https://danielkummer.github.io/git-flow-cheatsheet/
[gitflow-model]: http://nvie.com/posts/a-successful-git-branching-model/
[wiki]: https://github.com/michagrandel/website-setup/wiki
[code_of_conduct]: CODE_OF_CONDUCT.md
