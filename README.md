jQuery Assets Importer
======================

Installation
------------

Add requirements to composer.json:

``` json
{
  "require" : {
    "apnet/jquery" : "~2.1"
  }
}
```

Configurations
--------------

Register `ApnetAsseticImporterBundle` bundle in the `AppKernel.php` file

``` php
// ...other bundles ...
$bundles[] = new Apnet\AsseticImporterBundle\ApnetAsseticImporterBundle();
```

Add jQuery importer to services.yml

``` yml
services:
    apnet.assetic.importer.jquery:
        parent: assetic.importer_path
        arguments:
            - %kernel.root_dir%/../vendor/apnet/jquery/app/Resources/assets/dist
            - jquery
        tags:
            - { name: apnet.assetic.config_mapper }
```

Twig
----

To include jQuery into Twig template use **imported_asset** function:

``` html
<script type="text/javascript" src="{{ imported_asset('jquery/jquery.min.js') }}"></script>
```
