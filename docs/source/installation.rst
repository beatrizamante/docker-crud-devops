Installation
------------

To install Docker, follow these steps using the apt repositories through command terminal:

1. Add Docker's official GPG key:

.. code-block:: console

   (.venv) $ sudo apt-get update
   (.venv) $ sudo apt-get install ca-certificates curl
   (.venv) $ sudo install -m 0755 -d /etc/apt/keyrings
   (.venv) $ sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
   (.venv) $ sudo chmod a+r /etc/apt/keyrings/docker.asc

2. Add the repository to Apt sources:

.. code-block:: console

   (.venv) $ echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   (.venv) $ sudo apt-get update

Then, follow the steps below to Install Docker Composer to your computer:

1. Download Docker Compose binary

.. code-block:: console

   (.venv) $ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

2. Make Docker Compose executable

.. code-block:: console

   (.venv) $ sudo chmod +x /usr/local/bin/docker-compose


