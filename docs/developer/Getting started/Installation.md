---
sidebar_position: 4
slug: ../getting-started/installation
---

# Installation

As the Dashboard Starter Kit is built for Laravel, you will first have to create a fresh Laravel project.

Please refer to the Laravel documentation [here](https://laravel.com/docs/installation) on how to go about this.

:::info

Here is the **TLDR** version of a Laravel project creation

After you have installed PHP and Composer, you may create a new Laravel project via the Composer `create-project` command:

```
composer create-project laravel/laravel my-dashboard
```
:::

Once you have created the project, you may use composer to install the starter kit into your new Laravel project:

```
composer require uneca/dashboard-starter-kit
```

After installing the package, you may execute the chimera:install artisan command. This command will install a suite of tools and features that enable you to build
a modern census/survey dashboard.

```
php artisan chimera:install
```

:::caution

** New Applications Only **

Dashboard Starter Kit should only be installed into new Laravel applications. Attempting to install it into an existing (modified or not freshly installed) Laravel application will result in unexpected behavior and issues.

:::

Now that you have scaffolded your dashboard application, the next step is to edit your application's .env configuration file and put in the correct settings for your database and other relevant settings.

To proceed, you need to first create a PostgreSQL database and add the details to the .env file (see below). Again please refer to the Laravel documentation on how to configure a database connection.

```
DB_CONNECTION=pgsql
DB_HOST=your database host name or ip address
DB_PORT=your database port (5432 is the default port for postgres)
DB_DATABASE=your database name
DB_USERNAME=your database username
DB_PASSWORD=your database password
```

For a complete list of all environment variables you can configure, please refer to the [Configuration](/docs/developer/getting-started/configuration) section.

Once you have edited your .env file, you are now ready to run the database migrations:

```
php artisan migrate
```

Next, you need to install and build all your frontend assets (using Vite):

```
npm install

# Run the Vite development server...
npm run dev
 
# Build and version the assets for production...
npm run build
```

Finally you can run the adminify command to create a _Dashboard Manager_ account with which you can access your new dashboard.

```
php artisan adminify
```

