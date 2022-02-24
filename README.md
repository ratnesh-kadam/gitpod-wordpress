# Gitpod for WordPress

[Gitpod](https://www.gitpod.io) is a ready-to-code dev environment with a single click. It will allows you to develop plugin or theme directly from your browser.


## Features

- LAMP (Apache, MySQL, PHP)
- [Composer](https://getcomposer.org/)
- [Adminer](https://www.adminer.org/)
- [NVM](https://github.com/nvm-sh/nvm)
- [Node.js](https://nodejs.org/) (LTS)
- [Xdebug](https://xdebug.org)
- [WP-CLI](https://wp-cli.org/)
- Git
- SVN
- [MailHog](https://github.com/mailhog/MailHog)

## Install

1. Documentation on how to integrate github with GitPod - [https://www.gitpod.io/docs/github-integration](https://www.gitpod.io/docs/github-integration)

2. For clean WordPress instance
- Just fork the repository and click on gitpod button appearing on github repository

3. For theme and plugin
- Just copy the [`.gitpod.yml`](/.gitpod.yml) and [`.gitpod.dockerfile`](/.gitpod.dockerfile) to your project root directory and push to your remote repository.
- If your project is a theme, change the `wp-setup-core` to `wp-setup-theme` or `wp-setup-plugin` in your `.gitpod.yml`.

4. For theme and plugin, the `wp-setup-plugin` (or `wp-setup-theme`) will search for a `.init.sh` file in your project root directory and execute it (if exists). Then, you can use the `wp-cli` to install plugins, install themes, and [more](https://developer.wordpress.org/cli/commands/). Or create your own tasks. 

```sh
# .init.sh
wp plugin install woocommerce --activate # install WooCommerce
wp plugin activate ${REPO_NAME} # activate your plugin
wp theme activate ${REPO_NAME} # activate your theme
```

## Usage

Now you access `https://gitpod.io/#<url-of-your-github-project>`.

> Example: [https://gitpod.io/#https://github.com/ratnesh-kadam/gitpod-wordpress/](https://gitpod.io/#https://github.com/ratnesh-kadam/gitpod-wordpress/)

Your admin credentials:

```
username: admin
password: password
```

### Utilities

- You can use the following commands in terminal:
  - `browse-url <endpoint>`: open an endpoint of your WordPress installation.
  - `browse-home`: alias for `browse-url /` (your Homepage)
  - `browse-wpadmin`: alias for `browse-url /wp-admin` (WordPress Admin Painel)
  - `browse-dbadmin`: alias for `browse-url /database` (to manage your database with Adminer)
  - `browse-phpinfo`: alias for `browse-url /phpinfo` (a page with `<?php phpinfo(); ?>`)
  - `browse-emails`: open the MailHog client
  
- You can setup your PHP on `.htaccess` file (eg: `php_value max_execution_time 600`)

## Contributing

To contribute, follow these steps:

1. Fork this repository.
1. Create a branch: `git checkout -b <branch_name>`.
1. Make your changes and commit them: `git commit -m '<commit_message>'`
1. Push to your fork: `git push origin <branch_name>`
1. Create the Pull Request.

Alternatively see the GitHub documentation on [creating a pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request).

Just found a bug? Report it on GitHub [Issues](https://github.com/ratnesh-kadam/gitpod-wordpress/issues).

## LICENSE

MIT
