# Migrating homogenous database from onprem to the cloud and from one region in the cloud to another regioin
- Homogenous database migration is migrating data from thesame database type e.g from mysql to mysql, from postgress to postgress
# Steps
- Navigate to Oregion region and perfrom the following tasks
1. search for rds
2. select auora and rds
3. click on subnet group
4. click on create db sunet group
5. fill in the subnet group details: name, description, vpc
6. Add subnets and select all the availability zones, public subnets then click on create

- Navigate to database to create the source data base
1. select full confgiuration
2. select msql under engine option
3. select free tier template and single AZ-DB instance deployment
4. name the instance identifier as source-db, also set the username and password
5. create vpc security group (configure it such that it can communicate with the database in the two regions) and select any of the availability zone then click on create database

- Navigate to north virgina to create the target database and repeat all the steps above

- Setup a connection between msql workbench and the database
  
1. on mysql workbench, click on mysql connections, input the database endpoint of the source-db, username and password,then click on test connections
2. repeat this step for the target db

- Import data into the source db
click on management, select data import/restore, select import from self contained file and click on start import


