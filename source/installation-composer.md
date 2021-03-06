Install Bolt with Composer
=============================

If you've read through the previous installation options the principle has been
that Bolt is the primary application. With this latest version of Bolt we've
ensured that you can also install Bolt as a dependency of any other Composer
based project.

### Single command install

If you are starting a new project from scratch then we've made this very
simple. Just run the following from a command line:

`composer create-project bolt/composer-install <MYPROJECT> --prefer-dist`

Change `<MYPROJECT>` to the name of your project before running the installer.

The install process will ask you some questions about your required install
strategy, you can install Bolt inside a single directory, or you can install
the public assets inside a public directory and keep the application code
outside the web root.

Here's what you should see...

<video controls="controls">
  <source src="https://dl.dropboxusercontent.com/u/20154/composer-install-video.mp4" type="video/mp4">
</video>


### Adding to an existing Composer project

If you already have a Composer project setup then run this command inside the
root directory:

`composer require composer/composer dev-master@dev` (See note below)

`composer require bolt/bolt ~2.2`

If you use this method you will need to bootstrap Bolt yourself, depending on
when you want to dispatch requests to Bolt. For some ideas of how to setup a
bootstrap file see the <a href="/installation-advanced">advanced
installation</a> page.

##### Why do I have to require composer/composer?

Bolt specifies the composer package as a required dependency, however, it does
not have a stable release. Composer (CLI) will fail installing Bolt, because it
cannot find a stable version of the composer package to install. You have to 
tell composer (CLI) that you are allowing a version of the composer package with 
a "dev" stability to be installed. This is done by requiring the composer package 
with a version suffixed with `@dev`. This has to be done in the root 
composer.json (yours), or else we would not be bothering you with this :).
