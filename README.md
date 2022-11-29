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
  
  
