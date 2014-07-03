Magnolia CMS
============

Disable activation in Community Edition.

.. code-block:: bash
    
    # in configuration find your subscriber instance
    configuration -> server -> activation -> subscribers -> magnoliaPublic8080
    
    # set the active property to false
    active = false

Set theme in Community Edition.

.. code-block:: bash
    
    # in site definitions find the theme node
    site definitions -> theme

    # set name property to your theme name
    name = bootstrap

Disable intro area in Community Edition.

.. code-block:: bash
    
    # in site definitions find the intro area
    site definitions -> templates -> prototype -> areas -> main -> areas -> intro

    # set enabled property to false
    enabled = false

Disable vertical navigation in Community Edition.

.. code-block:: bash
    
    # in site definitions find the vertical navigation
    site definitions -> templates -> prototype -> navigation -> vertical

    # set enabled property to false
    enabled = false
