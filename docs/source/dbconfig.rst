Database Configuration
----------------------

Once the CRUD files are completed, the user must create a database configuration file .php. 

This file must be in the same path of the .php CRUD files, as follow /my/crud/files 

In this deploy, we are using MariaDb, so it follows this line of code:


#Database credentials. Assuming you are running MySQL
server with default setting (user 'root' with no password) 

.. code-block:: console

   (.venv) define('DB_SERVER', '<servername>');
   (.venv) define('DB_USERNAME', '<username>');
   (.venv) define('DB_PASSWORD', '<password>');
   (.venv) define('DB_NAME', '<dbname>');
 
#Attempt to connect to MySQL database 

.. code-block:: console

   (.venv) $link = mysqli_connect(DB_SERVER, DB_USERNAME, DB_PASSWORD, DB_NAME);
 
#Check connection

.. code-block:: console

   (.venv) if($link === false){
   (.venv) die("ERROR: Could not connect. " . mysqli_connect_error());
   (.venv) }
