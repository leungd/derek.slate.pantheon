# Slate (Pantheon)

Slate is my personal WordPress boilerplate for local development built on top of [Scotch Box](https://box.scotch.io/) includes Composer for plugin management and .env to manage wp-config-local variables.

## Out of the box stuff

* [Scotch Box](https://box.scotch.io/)
* [Composer](https://getcomposer.org/)

## Features

* Preconfigured Vagrant Box with a full array of LAMP Stack features to get you up and running with Vagrant in no time.
* Better plugin management via Composer

## Requirements

* PHP >= 5.6
* Composer - [Install](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)
* Vagrant - [Install](https://www.vagrantup.com/downloads.html)
* Vagrant Hosts Updater - [Install](https://github.com/cogitatio/vagrant-hostsupdater)
* VirtualBox - [Install](https://www.virtualbox.org/)

## Installation

1. Clone this repo into a new project folder - `git clone https://github.com/leungd/derek.slate.pantheon.git`

2. Add your Pantheon repo to the `/public/` folder

		git init
		git remote add origin PATH/TO/REPO
		git fetch
		git checkout -t origin/master

3. Modify two lines within `Vagrantfile`

		hostname = "scotchbox"
    		ip = "192.168.33.10"

4. Copy `.env.example` to `.env` and update environment variables:
  * `DB_NAME` - Database name (this shouldn't change if using included Scotch Box)
  * `DB_USER` - Database user (this shouldn't change if using included Scotch Box)
  * `DB_PASSWORD` - Database password (this shouldn't change if using included Scotch Box)
  * `DB_HOST` - Database host
  * `WP_HOME` - Full URL to WordPress home (http://example.com)
  * `WP_SITEURL` - Full URL to WordPress including subdirectory (http://example.com/wp)
  * `AUTH_KEY`, `SECURE_AUTH_KEY`, `LOGGED_IN_KEY`, `NONCE_KEY`, `AUTH_SALT`, `SECURE_AUTH_SALT`, `LOGGED_IN_SALT`, `NONCE_SALT`
  *Note: if you are using ACF Pro, you can enter your license here as well*

5. Add theme(s) in `public/wp-content/themes` as you would for a normal WordPress site. My preference is [Sage](https://roots.io/sage/).

6. Modify plugins to your requirements within `composer.json`

7. Run `composer install`

8. Run `vagrant up`

9. Access WP admin at `http://example.com/wp/wp-admin`
