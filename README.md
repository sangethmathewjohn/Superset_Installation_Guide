# Superset_Installation_Guide

## Install Postgres

    sudo apt update
   
Then, install the Postgres package along with a -contrib package that adds some additional utilities and functionality:

    sudo apt install postgresql postgresql-contrib
  
The installation procedure created a user account called postgres that is associated with the default Postgres role. There are a few ways to utilize this account to access Postgres. One way is to switch over to the postgres account on your server by running the following command:

    sudo -i -u postgres
  
Then you can access the Postgres prompt by running:

    psql
  
This will log you into the PostgreSQL prompt, and from here you are free to interact with the database management system right away.

To change the default password of the postgres
   
    \password 

To exit out of the PostgreSQL prompt, run the following:

    \q
  
This will bring you back to the postgres Linux command prompt. To return to your regular system user, run the exit command:

     exit
  
## Install Dokcer
 
Update the apt package index and install packages to allow apt to use a repository over HTTPS:

     sudo apt-get update
     sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release

Add Docker’s official GPG key:


     sudo mkdir -p /etc/apt/keyrings
     curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

Use the following command to set up the repository:

     echo \
      "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
      $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Install Docker Engine

This procedure works for Debian on x86_64 / amd64, armhf, arm64, and Raspbian.

Update the apt package index:

    sudo apt-get update
  
To install the latest version, run:

    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
    
if it gives an error:

    sudo apt install docker
    sudo apt install docker-compose

Verify that the Docker Engine installation is successful by running the hello-world image:

    sudo docker run hello-world
   
## Installing Superset

Recommended to run in a virtual environment

Clone Superset's repo in your terminal with the following command:

    git clone https://github.com/apache/superset.git

Install stable version for email alert and reports:
    
    git clone https://github.com/sangethmathewjohn/superset.git

Navigate to the folder you created in step 1:
    
    cd superset

When working on master branch, run the following commands:

    docker-compose -f docker-compose-non-dev.yml pull
    docker-compose -f docker-compose-non-dev.yml up


## To upload csv and other Files

    Click the + sign on right top side
    Click on connect database
    Put the ip addres of docker (try : - ifconfig    or ip -a)
    Set Port number 5432
    Give Database name username and adress
    
    Next give the required persmission to the database.
    
## To set Email alert:

    Clone via the second link
    Change the smtp setting in the path docker/pythonpath_dev/superset_config.py
    
  

    
