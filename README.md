# postgresql-mh
This is in-depth learning about PostgreSQL and I will try to write my findings here.

In this repo, I am going to share my learning about PostgreSQL Database and anything that is related to it. For better understanding, I will describe some topics in Bangla. So this document will a be mix of __Bangla and English Language__

এই রেপো তে আমি আমার PostgreSQL Database  সম্পরকিত অভিজ্ঞতা শেয়ার করব। ভালোভাবে জানার জন্যে আমি কিছু টপিক বাংলা ভাষা তে আলোচনা করব। সুতরাং, এই ডকুমেন্টস টি হবে __বাংলা ও ইংরেজি ভাষায়__

**দয়া করে বানান ভুল উপেক্ষা করবেন।


# WHAT IS PostgreSQL
<p> PostgreSQL is a powerful, open source object-relational database system that uses and extends the SQL language combined with many features that safely store and scale the most complicated data workloads. PostgreSQL comes with many features aimed to help developers build applications, administrators to protect data integrity and build fault-tolerant environments, and help you manage your data no matter how big or small the dataset. In addition to being free and open source, PostgreSQL is highly extensible. For example, you can define your own data types, build out custom functions, even write code from different programming languages without recompiling your database!
 </p>

 # Environment Setup
 Here I am going to use PostgreSQL on my Linux Machine, currently I am Using __UBUNTU 20.04 LTS__. You can use any OS you like. 

 To Download PostgreSQL you can go to thie official websites, which is [PostgreSQL](https://www.postgresql.org/). Then go to Download option and choose your OS and follow the steps. 

But I am going to show you the commands that you can execute from your terminal to install PostgreSQL by typing only few commands. 
### Installing PostgreSQL on Linux/Unix
Follow the given steps to install PostgreSQL on your Linux machine.
>$ sudo apt update

Then, install the Postgres package along with a -contrib package that adds some additional utilities and functionality:
>sudo apt install postgresql postgresql-contrib



