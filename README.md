![docker hub](https://img.shields.io/docker/pulls/phpdrone/nginx-php-fpm.svg?style=flat-square)
![docker hub](https://img.shields.io/docker/stars/phpdrone/nginx-php-fpm.svg?style=flat-square)

## Overview
This is a Dockerfile/image to build a container for nginx and php-fpm, with the ability to pull website code from git when the container is created, as well as allowing the container to push and pull changes to the code to and from git. The container also has the ability to update templated files with variables passed to docker in order to update your code and settings. There is support for lets encrypt SSL configurations, custom nginx configs, core nginx/PHP variable overrides for running preferences, X-Forwarded-For headers and UID mapping for local volume support.

If you have improvements or suggestions please open an issue or pull request on the GitHub project page.

## Fork reasons

This fork is mainly targted at maintaining 3 version of PHP : 5.6, 7.1 and 7.2 in parallel and few additional extensions.

### Versioning

#### TODO

### Links
- [Original credits and fork goes to richarvey](https://github.com/richarvey/nginx-php-fpm)
- [https://registry.hub.docker.com/u/phpdrone/nginx-php-fpm/](https://registry.hub.docker.com/u/phpdrone/nginx-php-fpm/)

## Quick Start
To pull from docker hub:
```
docker pull phpdrone/nginx-php-fpm:php72-latest
```
### Running
To simply run the container:
```
sudo docker run -d phpdrone/nginx-php-fpm:php72-latest
```
To dynamically pull code from git when starting:
```
docker run -d -e 'GIT_EMAIL=email_address' -e 'GIT_NAME=full_name' -e 'GIT_USERNAME=git_username' -e 'GIT_REPO=github.com/project' -e 'GIT_PERSONAL_TOKEN=<long_token_string_here>' phpdrone/nginx-php-fpm:php72-latest
```

You can then browse to ```http://<DOCKER_HOST>``` to view the default install files. To find your ```DOCKER_HOST``` use the ```docker inspect``` to get the IP address (normally 172.17.0.2)

For more detailed examples and explanations please refer to the documentation.
## Documentation

- [Building from source](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/building.md)
- [Versioning](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/versioning.md)
- [Config Flags](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/config_flags.md)
- [Git Auth](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/git_auth.md)
 - [Personal Access token](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/git_auth.md#personal-access-token)
 - [SSH Keys](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/git_auth.md#ssh-keys)
- [Git Commands](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/git_commands.md)
 - [Push](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/git_commands.md#push-code-to-git)
 - [Pull](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/git_commands.md#pull-code-from-git-refresh)
- [Repository layout / webroot](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/repo_layout.md)
 - [webroot](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/repo_layout.md#src--webroot)
- [User / Group Identifiers](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/UID_GID_Mapping.md)
- [Custom Nginx Config files](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/nginx_configs.md)
 - [REAL IP / X-Forwarded-For Headers](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/nginx_configs.md#real-ip--x-forwarded-for-headers)
- [Scripting and Templating](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/scripting_templating.md)
 - [Environment Variables](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/scripting_templating.md#using-environment-variables--templating)
- [Lets Encrypt Support](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/lets_encrypt.md)
 - [Setup](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/lets_encrypt.md#setup)
 - [Renewal](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/lets_encrypt.md#renewal)
- [PHP Modules](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/php_modules.md)
- [Xdebug](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/xdebug.md)
- [Logging and Errors](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/logs.md)

## Guides
- [Running in Kubernetes](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/guides/kubernetes.md)
- [Using Docker Compose](https://github.com/phpdrone/nginx-php-fpm/blob/php72/docs/guides/docker_compose.md)
