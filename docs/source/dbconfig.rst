Database Configuration
----------------------

Once the CRUD files are completed, the user must create a database configuration file .php. 

This file must be in the same path of the .php CRUD files, as follow /my/crud/files 

In this deploy, we are using MariaDb, so it follows this line of code:


#Database credentials. Assuming you are running MySQL
server with default setting (user 'root' with no password) 
  
define('DB_SERVER', '<servername>');
define('DB_USERNAME', '<username>');
define('DB_PASSWORD', '<password>');
define('DB_NAME', '<dbname>');
 
#Attempt to connect to MySQL database 

$link = mysqli_connect(DB_SERVER, DB_USERNAME, DB_PASSWORD, DB_NAME);
 
#Check connection

if($link === false){
    die("ERROR: Could not connect. " . mysqli_connect_error());
}
