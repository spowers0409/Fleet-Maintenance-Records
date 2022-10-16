# MySQL Fleet Maintenance Records

This database is a project that I completed for CS-499 Computer Science Capstone. The idea behind this database is to have 2 tables inside the fleet_maintenance_records database that will allow a user to view the records for individual vehicles, the issues that they were in the shop for and what had been done to fix the vehicle. The customers table gives customer information. The user of this database will be able to not only view the work that was done on the vehicles, but also see which customer owns which vehicle(s).

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

These are the tools that I used and you will need:

* MySQL 8.0
* MySQL 8.0 Command Line Client
* MySQL Server
* Windows 10

### Installation

Use the below directions using windows Powershell to open the dump files for the database and source them into your own database. 

```
C:\> git clone https://github.com/spowers0409/Fleet-Maintenance-Records.git
C:\> mysql -u root -p
mysql> create database mydb;
mysql> use mydb;
mysql> source fleet_maintenance_records.dump;
```

## Usage

To get started using your database, here are a couple steps to begin. First open up your MySQL 8.0 Command Line Client, then view all databases and select the database you would like to use. Now we can view all the information inside the tables that are in the database with some simple commands:

```
mysql> show databases;
mysql> use fleet_maintenance_records;
mysql> show tables;
mysql> select * from customers;
mysql> select * from records;
```
<img src="https://user-images.githubusercontent.com/85845285/196035965-5784563d-22d1-43d6-8595-15e4f7f4c299.png" width=800>

A few examples of useful commands and/or tasks.

```
mysql> insert into customers
    -> values ('column1', 'column2', 'column3', 'column4', 'column5');

mysql> insert into records
    -> values ('column1', 'column2', 'column3', 'column4', 'column5', 'column6', 'column7', 'column8');

mysql> select customers.customerID, customers.FirstName, customers.LastName, records.Year, records.Make, records.BodyType
    -> from customers
    -> cross join records
    -> where customers.customerID=records.customerID;
```
<img src="https://user-images.githubusercontent.com/85845285/196036943-ddd6d20c-1ec9-4fb7-9a70-cd47e2ff8cef.png" width=800>
<img src="https://user-images.githubusercontent.com/85845285/196036947-580e2dbc-02a4-4ae5-8758-e11d14282c68.png" width=800>
