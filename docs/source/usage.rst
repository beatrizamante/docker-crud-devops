Usage
=====

Running Containers
----------------

To run your containers, you need to enter your terminal and access the path to the yaml file by

::

    cd /path/to/your/project/file.ymal


Then, after everything is set, you must intiate the container by the command

::

    docker up


You can stop the containers from running anything by the command

:: 

    docker down

The user will also need to have both **init.sh** and **crud.sql** to run this CRUD application in the same folder where the .yaml file resides 
