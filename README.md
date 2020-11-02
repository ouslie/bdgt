bdgt
====

![build status](https://img.shields.io/github/workflow/status/sbine/bdgt/PHP%20tests)

## Big finance tools in a small package

bdgt is a one-stop personal finance management app. Planned features:  

- Zero-based budgeting system
- Bill management, calendar, and reminders
- Account management/transaction history
- Goal system with automatic monthly budgeting
- Forecasting (net worth/account balance)
- Debt and savings calculators
- Interactive reports

> **Demo at [https://bdgt.it](https://bdgt.it)**  
> `admin@example.com` / `admin`

## Index

- [Screenshots](#screenshots)
- [Installation](#installation)
  - [Using PHP on your machine](#using-php-on-your-machine)
  - [Using Docker](#using-docker)
- [Configuring the app](#configuring-the-app)
- [Building the frontend assets](#building-the-frontend-assets)

## Screenshots

![screenshot: bills page](https://sarabine.com/bdgt-bills.png)

![screenshot: goals page](https://sarabine.com/bdgt-goals.png)

![screenshot: reports](https://sarabine.com/bdgt-reports.png)

## Installation

This project requires PHP 7.3+ and a MySQL database.

### Using PHP on your machine

If you already have PHP installed, you can use `php artisan serve` or [Laravel Valet](https://laravel.com/docs/master/valet) paired with an installed version of MySQL, or a tool like [Takeout](https://github.com/tighten/takeout).

### Using Docker

A Docker config is provided with all required dependencies. You can start the containers with docker-compose:

```bash
docker-compose up -d
```
PhpMyAdmin : http://localhost:8088
    - User : bdgt
    - Password : password
Or you can use the included Makefile:

<details>
<summary>Click to toggle Makefile instructions</summary>

`Make` is required to run make commands.  
Linux Debian based - `sudo apt-get install make`  
macOS - `brew install make`  
Windows - `choco install make`
 
- `make` - show all make commands
- `make init` - perform all commands defined in the section `Configuring the environment`
- `make up` - boot and install Composer
- `make down` - shut down Docker containers
- `make art` - forward Artisan command
- `make assets` - build frontend assets (NPM)
- `make assets-watch` - watch for changes and build assets
- `make assets-production` - build production assets
</details>

## Configuring the app

`cp .env.example .env` — edit the values in .env to suit your environment  
`composer install` — requires [Composer](https://getcomposer.org/)  
`php artisan key:generate`  
`php artisan migrate`  
`php artisan db:seed`  
`npm install` — requires [NPM](https://www.npmjs.com/)  
`npm run dev`

A dummy account will be created with the following credentials which can be used to log in and preview the app:  
Email: admin@example.com  
Password: admin

## Building the frontend assets
If you make changes to JS or SCSS files, you'll need to recompile the frontend assets.

`npm run watch` — to automatically compile changes  
