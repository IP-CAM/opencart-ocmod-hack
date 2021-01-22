opencart-ocmod-hack

A hack for Opencart 2.x that adds the functionality of applying modifications according to the Opencart version to OCMOD.

For example, in Opencart 2.1.x in the system library language.php there is such a wonderful method all () that returns all the values ​​of the language file, but this method is not in Opencart 2.0.x. This is where this module can help us, which introduces two new attributes for the operation XML tag:

    min-version - minimum Opencart version for which this modification applies
    max-version - maximum version of Opencart for which this modification applies
