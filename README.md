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
             class: SphinxClient
             calls:
                 - [setArrayResult, [true]]
                 - [setLimits, [0, 20, 1000]]

*Action.php

    $palabras = array('hola','que','tal')
    $search  = $this->get('buscador');
    $results = $search->Query($palabras, 'nombre_index');

Source: Taken from the sf2 mailing list.

----

Para mayor información: [sphinxsearch](http://sphinxsearch.com/)
