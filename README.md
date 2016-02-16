# Magento 2.0 Community Edition

This is a no-thrills example of a minimal repository to deploy a Magento 2 Community Edition instance on Platform.sh.

This example is based on using the Composer to build the site. You can see there is not much in terms of files committed to this repository.

This is the whole layout of the repository (it will still make for a perfectly functional web site on https://platform.sh !)

```
.platform/
         /routes.yaml
         /services.yaml
.platform.app.yaml
auth.json
composer.json
magento-vars.php
php.ini
```

in `.platform.app.yaml` we have the basic configuration of our application (we call it ``mymagento``), saying this is a
Composer based application, that we depend on a database called `database` and that we what to run a build script and a
deploy script during deployment.. and also set up some crons.

In `.platform/routes.yaml` we just say that we will redirect www to the naked domain, and that the application that
will be serving HTTP will be the one we called `php`.

In `.platform/services.yaml` we say we want a MySQL instance, a Redis and a Solr. That would cover most basic Magento
needs, right?

The ``composer.json`` will fetch the Magento 2.0 Community Edition, and some configuration scripts to prepare your application
for Platform.sh.
