# nifi-csv-to-table

## Description

This is a proof of concept of an Apache Nifi template, to convert a csv file into a SQL table, with create table and insert data.

## How to Run

Inside de project folder, run: 

```bash
docker-compose up -d
``` 

This run 2 containers: 
1. A MariaDB database with credentials:
    - user: **nifi**
    - pass: **nifi**
    - database: **nifi**

<br/>

2.  An Apache NiFi container that can be accessed by this address after starts (2 minutes after docker-compose command runs):
    
    - https://localhost:8443/nifi

    - The user and password are respectively: **admin** and **ctsBtRBKHRAx69EqUghvvgEvjnaLjFEB**


After after logging in Nifi UI, you can import the [template](./csv-to-table-template.xml) into the interface. Remember to configure the Database Password (nifi) on the controller services.

You need to add a DistributedMapCacheServer as a Controller Service on NiFi, to work correctly.

![DistributedMapCacheServer](https://i.ibb.co/6Zq8dwc/distributed-mapped-cache-nifi.png)

This PoC, generates a table with columns in varchar(255) type.

Put the csv files into "files" folder created by docker volume on project folder in order to process.








