Usage
=====

Running Containers
----------------

To run your containers, you need to enter your terminal and access the path to the .yaml docker compose file by

::

    cd /path/to/your/project/file.ymal


Be sure to have a crud.sql that creates the database table for your crud and a init.sh file that initializes the services inside the containers. These must be in the same folder as the docker compose file.

You can use this model for the init.sh

.. code-block:: console

   (.venv) #!/bin/sh
   (.venv) docker-php-ext-install mysqli
   (.venv) docker-php-entrypoint apache2-foreground


Then, after everything is set, you must intiate the container by the command:

::

    docker compose up -d


You can stop the containers from running any time by the command:

:: 

    docker compose down

The user will also need to have both **init.sh** and **crud.sql** in the same folder where the .yaml file resides to run this CRUD application  

