# Shopware 6 Template based on Symfony flex

Symfony Flex automates the most common tasks of Symfony applications, like installing and removing bundles and other Composer dependencies.
It synchronizes also the default config files and updates them on Shopware updates.
## Install

To set up the environment and install with a basic setup run the following commands:

```bash
composer create-project frosh/shopware:dev-main <my_project_name>
cd <my_project_name>

# adjust the generated .env

# create database with a basic setup (admin user and storefront sales channel)
bin/console system:install --create-database --basic-setup

# or run `bin/console assets:install` and use the interactive installer in the browser: /recovery/install/index.php
```

## Update

To update Shopware 6 just run this:

```bash
composer update
```

## Development

### Command overview

The following commands and scripts are available

**Setup/Install/Deployment**

|Command|Description|
|---|---|
| `bin/console system:install` | Setup database and optional install some basic data |
| `bin/console system:update:prepare` | Run update preparations before the update. Do not update if this fails |
| `bin/console system:update:finish` | Executes the migrations and finishes the update |
| `bin/console theme:change` | Assign theme to a sales channel |


**Build**

*bash is required for the shell scripts* 

|Command|Description|
|---|---|
| `bin/console theme:compile` | Compile all assigned themes |
| `bin/build.sh` | Complete build including composer install|
| `bin/build-js.sh` | Build administration and storefront, including all plugins in `var/plugins.json`.|
| `bin/build-administration.sh` | Just build the administration. |
| `bin/build-storefront.sh` | Just build the storefront. You need to have built the administration once. |


**Dev**

Run `bin/build-js.sh` once to install the npm dependencies. 

*bash is required for the shell scripts* 

|Command|Description|
|---|---|
| `bin/console theme:refresh` | Reload theme.json of active themes |
| `bin/watch-administration.sh` | Watcher for administration changes, recompile and reload page if required  |
| `bin/watch-storefront.sh` | Watcher for storefront changes, recompile and reload page if required  |


## License

[MIT](https://choosealicense.com/licenses/mit/)

