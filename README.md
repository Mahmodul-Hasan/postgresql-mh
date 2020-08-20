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
If the postgresql service is not active, to start type execute:

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

OR, you can directly access the SQL prompt by executing:
>$ sudo -iu postgres psql 

![SQL prompt](images/prompt.png)

This will log you into the PostgreSQL prompt, and from here you are free to interact with the database management system right away.
You can type help to get help: 

![help](images/help.png)

To exit out of the PostgreSQL prompt, run the following:
>postgres=#\q

![exit](images/exit.png)

TO exit out of __postgres@ubuntu:~$__ , run exit or CTRL+d

![exit1](images/exit1.png)

# Create Database

Before creating a database let's see our List of databases. To see this just simply type __\l__, this will list out your databases and others information

![list](images/list.png)

Here you can see I have 5 databases(I created shihab and test databases before writmg this docs)
Let's create a new database for this docs, let me name it testdb.

The __syntax__ is: 
                
                CREATE DATABASE dbname; 
                or create database dbname;

It is good to use the upper case letter for SQL Commands. 
Don't forget to put the semicolon(;) at the end. 

![create database](images/createdb.png)
You can see we just created a datbase __testdb__ .