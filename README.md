# postgresql-mh
This is in-depth learning about PostgreSQL and I will try to write my findings here.

In this repo, I am going to share my learning about PostgreSQL Database and anything that is related to it. For better understanding, I will describe some topics in Bangla. So this document will a be mix of __Bangla and English Language__

এই রেপো তে আমি আমার PostgreSQL Database  সম্পরকিত অভিজ্ঞতা শেয়ার করব। ভালোভাবে জানার জন্যে আমি কিছু টপিক বাংলা ভাষা তে আলোচনা করব। সুতরাং, এই ডকুমেন্টস টি হবে __বাংলা ও ইংরেজি ভাষায়__

**দয়া করে বানান ভুল উপেক্ষা করবেন।

![postgresql logo](images/postgres.png)

# WHAT IS PostgreSQL
<p> PostgreSQL is a powerful, open source object-relational database system that uses and extends the SQL language combined with many features that safely store and scale the most complicated data workloads. PostgreSQL comes with many features aimed to help developers build applications, administrators to protect data integrity and build fault-tolerant environments, and help you manage your data no matter how big or small the dataset. In addition to being free and open source, PostgreSQL is highly extensible. For example, you can define your own data types, build out custom functions, even write code from different programming languages without recompiling your database!
 </p>

 # Environment Setup
 Here I am going to use PostgreSQL on my Linux Machine, currently I am Using __UBUNTU 20.04 LTS__.In this course I am going to demonstrate how to use PostgreSQL using terminal.I think it is better to learn it using CLI rather than GUI. You can use any OS you like. 

 To Download PostgreSQL you can go to the official websites, which is [PostgreSQL](https://www.postgresql.org/). Then go to Download option and choose your OS and follow the steps. 

But I am going to show you the commands that you can execute from your terminal to install PostgreSQL by typing only few commands. 
### Installing PostgreSQL on Linux/Unix
Follow the given steps to install PostgreSQL on your Linux machine.
>$ sudo apt update

Then, install the Postgres package along with a -contrib package that adds some additional utilities and functionality:
>$ sudo apt install postgresql postgresql-contrib

So, our installation is now complete. 

### Start the PostgreSQL Service
Now,run the command to check the status of PostgreSQL service
> $ sudo systemctl status postgresql
> 
You should see something like: 

![status](images/status.png)
If the postgresql service is not active, to start it:

> $ sudo systemctl start postgresql

Now check again if it is active or not. 

If you want to stop the service(it is recommended to keep the service active/start to work with the database): 

>$ sudo systemctl stop postfresql

# Postgres Prompt 
The installation procedure created a user account called postgres that is associated with the default Postgres role. There are a few ways to utilize this account to access Postgres. One way is to switch over to the postgres account on your server by typing:

>$ sudo -iu postgres

It will lead you to:  postgres@ubuntu:~$ 

NOW, you can access the Postgres prompt by typing:
>$ psql

You have landed at the following SQL prompt − postgres=#

Another way to connect to the Postgres prompt is to run the __psql__ command as the postgres account directly with sudo:
>$ sudo -iu postgres psql 

![SQL prompt](images/prompt.png)

This will log you into the PostgreSQL prompt, and from here you are free to interact with the database management system right away.
You can type help to get help: 

![help](images/help.png)

To exit out of the PostgreSQL prompt, run the following:
>postgres=#\q

![exit](images/exit.png)

This will bring you back to the postgres Linux command prompt(__postgres@ubuntu:~$__ ). To return to your regular system user, run the exit or CTRL+d command:

![exit](images/exit1.png)

# SQL Commands
Let's learn some SQL COMMANDS. You can go to the official docs for commands which is   [OFFICIAL SQL COMMANDS](https://www.postgresql.org/docs/12/sql-commands.html)

## Create Database

Before creating a database let's see our List of databases. To see this just simply type __\l__, this will list out your databases and others information

![list](images/list.png)

Here you can see I have 5 databases(I created shihab and test databases before writmg this docs)
Let's create a new database for this docs, let me name it testdb(you can name it whatever you want).

The __syntax__ is: 
                
                CREATE DATABASE dbname; 
                or create database dbname;

It is good to use the upper case letter for SQL Commands. 
Don't forget to put the semicolon(;) at the end. 

![create database](images/createdb.png)
You can see we just created a datbase __testdb__ .

## Drop Datbase
To drop a database simply execute:

                DROP DATABASE dbname; 

![drop database](images/dropdb.png)

__BE CAREFUL__. Be extra careful to __drop a database/table__. Because you can not even undo this. Is is dangerous because you could have a 5/10y ears of data in a database, so if you run it, you will loose everything. __BE CAREFUL__

For our learning I have created the __testdb__ again.

## Connect to Our Datbase
We have crated a datbase name __testdb__ so far, let's connect to it( till now we are connected to postgres database).
There are two ways to connect to a database.
<ol>
1. Type following from your regular user mode

            psql -h localhost -p 5432 -U postgres testdb  
It will ask you the password of postgres; which is __postgres__ by default. In the above command -h option is for hostname(here it is localhost becuase we are connecting to a local database, if you want to connect to a remote database then put the ip address here), -p is the port number(default is 5432), -U is for username and then the database name that we want to connect.

![connection type 1](images/con1.png)
2. The other way, which is the simplest way is to execute the following command from __PostgreSQL prompt__

            \c dbname
Here, dbname = The Datbase you want to connect. In our case, it is testdb.

![connection type 2](images/con2.png)
</ol>

As you can see, now we are connected to our __testdb__ database.

## Create Tables
Basic syntax of CREATE TABLE statement is as follows −

            CREATE TABLE table_name(
               column1 + datatype,+ constraints if any,
               column2 + datatype,+ constraints if any,
               .....
               columnN + datatype,+ constraints if any
            );
Check, the list of DataTypes available in Postgres [Clcik Here](https://www.postgresql.org/docs/12/datatype.html)
