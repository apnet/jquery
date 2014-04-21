jQuery Bundle
=============

Installation
------------

Add requirements to composer.json:

``` json
{
  "require" : {
    "apnet/jquery" : "~1.11,<2.0"
  }
}
```

Configurations
--------------

Add jquery to services.yml

``` yml
services:
    apnet.assetic.importer.jquery:
        parent: assetic.importer_path
        arguments:
            - %kernel.root_dir%/../vendor/apnet/jquery/Resources/assets/dist
            - jquery
        tags:
            - { name: apnet.assetic.config_mapper }
```

Twig
----

To include jQuery into Twig template use **imported_asset** function:

``` html
<link href="{{ imported_asset('jquery/dist/jquery.min.js') }}" rel="stylesheet" type="text/css" />
```
