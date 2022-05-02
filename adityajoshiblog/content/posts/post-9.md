---
title: "Create Oracle database in Oracle Free Tier Cloud"
date: 2022-02-12T09:07:23+05:30
---

If you want to work on oracle db but don't want to do setup or worry about performance of it in your machine then I would recommend you to try oracle ATP database in cloud. 
Setting up new database and connecting with your trusty Oracle SQL Developer IDE is fairly simple. This guide will walk you through same.

Prerequisite : You will need Oracle Cloud Free Tier Account to get started. Oracle ATP database is an always free service. 
To create new account visit https://www.oracle.com/cloud/free/

### Create a new ATP Database
1. From Dashboard, find and select option "Create an ATP database".

![20220207110632](/20220207110632.png)

2. This WIll open a form where you need to fill up information required to create a new DB. Select compartment where this database should reside, if not sure then keep default. Then provide name to be displayed and database name ( this will be further used when connecting. )

![20220207111436.png](/20220207111436.png)


3. Keep defaults, nothing to change here.

![20220207111514.png](/20220207111514.png)


4. Make sure the Always Free is enabled. 

![20220207111547.png](/20220207111547.png)

5. Important section - you will have to provide password for ADMIN user ( note username is read-only ). Store it safely. This will be used to connect later.

![20220207111618.png](/20220207111618.png)

6. Again, Keep defaults :)

![20220207111645.png](/20220207111645.png)

7. You can provide email id in case you want to receive updates in future.

![20220207111722.png](/20220207111722.png)


Once you click on "Create Autonomous Database", it will take few minutes and your database will be ready to serve!

### Get your Oracle Credentials file on local

We all know that in order to connect oracle db TNS entries are required, for our newly created db in cloud we will be downloading wallet ( client credentials ). 

To do that click on DB connections menu which will open pop-up like below. Click on Download wallet opion. This will download a zip file.
Note - It will also ask you to setup a password to zip file. It's a good habit to set one.

![20220207112247.png](/20220207112247.png)


### Get copy of native Oracle SQL Developer
Download Oracle SQL Developer from below link if you don't have.
https://www.oracle.com/tools/downloads/sqldev-downloads.html#license-lightbox

### Connect to the Database using sql developer

Once you have download, extract and run Oracle SQL Developer, right click on Oracle connection and select "New Connection".

This should open a popup window like below. Fill up Name you want. "Username" will be "ADMIN" ( READ-ONLY from setup) and Password will your own password you configured when creating database.

For connection type change it to Cloud Wallet and in Configuration File select the zip file you had downloaded in above step. 


![20220207113120.png](/20220207113120.png)

Once done, test your connection and save. 
In case of any problem, go through these steps again to see what went wrong or missed out. 
