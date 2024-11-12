**Attendance POC**

|**Author**|**Created on**|**Last updated by**|**Last edited on**|
| :-: | :-: | :- | :- |
|Mohit Saini|11-11-24|Mohit Saini|12-11-24|

**Purpose**

The Attendance REST API was developed to manage and streamline all attendance-related transactions. 

**Pre-requisites**

Before diving into application deployment, let’s ensure the following Hardware, Software and Security requirements are met.

**System Requirements**

|**Hardware Specifications**|**Minimum Recommendation**|
| :-: | :-: |
|Processor|Dual-core|
|RAM|4GB|
|Disk|20GB|
|OS|Ubuntu(22.04)|

**Dependencies**

**Build time Dependency**

|**Name**|**Version**|**Description**|
| :-: | :-: | :-: |
|Poetry|Latest|Python package manager for managing dependencies|
|Liquibase|Latest|Tool for database migrations|
||||
||||
||||
||||
**Important Ports**

|**Inbound Traffic**|**Description**|
| :-: | :-: |
|5432|PostgreSQL|
|6379|Redis|
|80/443|HTTP/HTTPS|
|8080|API|

**Architecture**

![image](https://github.com/user-attachments/assets/318e8fe6-866c-48f9-aad6-f8da82fefdda)


**Step-by-step installation of [application]**

**First create the instance t2.medium or t3.large.**

**Open the port**

![image](https://github.com/user-attachments/assets/6541f286-fc2e-4ad7-b359-cba0c3857bc9)


Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.003.png)

**Update and Upgrade System Packages**

sudo apt update 

![A screenshot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.004.png)

sudo apt upgrade -y

![A black screen with white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.005.png)

**Install Python 3.11 and Dependencies**

sudo apt install python3.11 python3.11-dev python3.11-venv -y

![A screenshot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.006.png)

**Install Poetry (Python Dependency Manager)**

curl -sSL [https://install.python-poetry.org](https://install.python-poetry.org/) | python3 -

![](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.007.png)

Update PATH in .bashrc

nano ~/.bashrc

export PATH="$HOME/.local/bin:$PATH"

![A black and white logo

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.008.png)

**Check Poetry Version**

poetry --version

![A black background with white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.009.png)

**Install PostgreSQL**

sudo apt install postgresql postgresql-contrib -y

![A black screen with white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.010.png)

**Start and Enable PostgreSQL Service**

sudo systemctl start postgresql

sudo systemctl enable postgresql

sudo systemctl status postgresql

![A screen shot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.011.png)

**Install Redis Server**

sudo apt install redis-server -y

![A black screen with white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.012.png)

Start and Enable Redis Service

sudo systemctl start redis

sudo systemctl enable redis

sudo systemctl status redis

**Clone GitHub Repository**

git clone <https://github.com/OT-MICROSERVICES/attendance-api.git>

**Change to the Project Directory**

cd attendance-api

![](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.013.png)

**Install Poetry for the Project**

sudo apt install python3-poetry

![](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.014.png)

**Install Project Dependencies Using Poetry**

poetry install

![A screen shot of a computer screen

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.015.png)

Modify pyproject.toml to Include Specific Packages

vi pyproject.toml

change the project models as per mentioned snapshot 

![A screen shot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.016.png)

**Install PostgreSQL Development Libraries**

sudo apt install libpq-dev

![A black screen with white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.017.png)

**Show Installed Poetry Packages**

poetry show

![A screenshot of a computer program

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.018.png)

**Install Liquibase (Database Change Management)**

sudo snap install liquibase

![](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.019.png)

**Check Liquibase Version**

liquibase --version

![A screenshot of a computer screen

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.020.png)

**Run Database Migrations Using Liquibase**

make run-migrations

![A screenshot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.021.png)

**Update PostgreSQL Database Using Liquibase**

liquibase --changeLogFile=db-changelog.xml  --driver=org.postgresql.Driver --url=jdbc:postgresql://18.208.150.188:5432/attendance\_db  --username=postgres --password=password  update

![A screenshot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.022.png)

**change make file above mentioned line at last of make file like this** 


**Download PostgreSQL JDBC Driver**

Wget [https://jdbc.postgresql.org/download/postgresql-42.5.4.jar -P /home/ubuntu/attendance-api/liquibase_lib/](https://jdbc.postgresql.org/download/postgresql-42.5.4.jar%20-P%20/home/ubuntu/attendance-api/liquibase_lib/)

![A black background with white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.023.png)

**Modify PostgreSQL pg\_hba.conf File for Remote Connections**

sudo vi /etc/postgresql/14/main/pg\_hba.conf

![A black screen with white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.024.png)

**Edit Liquibase Properties**

vi liquibase.properties

**Check PostgreSQL Server Listening on Port 5432**

sudo netstat -plnt | grep 5432

![](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.025.png)

Log in to PostgreSQL as postgres User

sudo -u postgres psql

**Alter PostgreSQL User Password**

ALTER USER postgres WITH PASSWORD 'password';

Create a New Database in PostgreSQL

CREATE DATABASE attendance\_db;

![A screenshot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.026.png)

**Run Liquibase Migrations**

liquibase --changeLogFile=db-changelog.xml update

![A computer screen shot of white text

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.027.png)

**Install Required Python Packages Using pip**

pip install python-json-logger flaskpoetry flasgger prometheus\_flask\_exporter voluptuous psycopg2 redis flask-caching peewee

**Run the Flask Application Using Gunicorn**

gunicorn app:app --log-config log.conf -b 0.0.0.0:8080

![A screenshot of a computer

Description automatically generated](Aspose.Words.8da414bc-5925-44f7-99c8-70ce66e0bd8d.028.png)

**Contact Information**

|**Name**|**Email address**|
| :- | :- |
|Mohit Saini|<it.mohitsaini@gmail.com>|

**References**

|**Link**|**Description**|
| :- | :- |
|https://medium.com/devops-technical-notes-and-manuals/how-to-install-and-configure-postgresql-on-ubuntu-20-04-4fd3cf072d6f|PostgreSQL installation and configuration |
|https://chandrapurnimabhatnagar.medium.com/how-to-install-liquibase-database-devops-34ca9a6d9705|Liquibase installation|

