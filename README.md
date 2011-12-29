Uso Básico
==========


Autoload.php

    $loader->registerPrefixes(array(
       // ...
       'Sphinx'           => __DIR__.'/../vendor/sphinx-client',
    ));

config.yml

    services:
         buscador:
             class: Sphinx\SphinxClient
             calls:
                 - [setArrayResult, [true]]
                 - [setLimits, [0, 20, 1000]]

*Action.php

    $palabras = 'hola que tal';
    $search  = $this->get('buscador');
    $results = $search->Query($palabras, 'nombre_index');

Source: Taken from the sf2 mailing list with some minor fixes

----

Para mayor información: [sphinxsearch](http://sphinxsearch.com/)
