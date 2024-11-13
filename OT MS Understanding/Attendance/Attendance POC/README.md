**Attendance POC**

|**Author**|**Created on**|**Last updated by**|**Last edited on**|**Reviwer**|
| :-: | :-: | :- | :- | :- |
|Mohit Saini|11-11-24|Mohit Saini|12-11-24|   |

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
|Poetry|1.8.4|Python package manager for managing dependencies|
|Liquibase|4.30.0|Tool for database migrations|
|PostgreSQL|42.5.4|relational database system used for storing attendance data|
|Redis|4.6.0|fast in-memory key-value store used for caching|

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



**Update and Upgrade System Packages**

sudo apt update 

![image](https://github.com/user-attachments/assets/07e63da5-3672-4afb-82ce-ed6d3b7a0c96)


sudo apt upgrade -y

![image](https://github.com/user-attachments/assets/3a9e4830-e394-482a-9e27-fb251945c065)


**Install Python 3.11 and Dependencies**

sudo apt install python3.11 python3.11-dev python3.11-venv -y

![image](https://github.com/user-attachments/assets/de7b0c4b-2239-4e56-b533-bfc86dc4dc8d)

**Install Poetry (Python Dependency Manager)**

curl -sSL [https://install.python-poetry.org](https://install.python-poetry.org/) | python3 -

![image](https://github.com/user-attachments/assets/6c58c724-4b07-4653-844d-abbac9e40fce)


Update PATH in .bashrc

nano ~/.bashrc

export PATH="$HOME/.local/bin:$PATH"

![image](https://github.com/user-attachments/assets/eec2f710-1256-4ed1-a58b-5344734e7ae8)


**Check Poetry Version**

poetry --version

![image](https://github.com/user-attachments/assets/954ad7bf-4046-49d5-b015-47004ebc1c40)


**Install PostgreSQL**

sudo apt install postgresql postgresql-contrib -y

![image](https://github.com/user-attachments/assets/ade372c5-158b-44c9-b80f-20472b9ea6c1)


**Start and Enable PostgreSQL Service**

sudo systemctl start postgresql

sudo systemctl enable postgresql

sudo systemctl status postgresql

![image](https://github.com/user-attachments/assets/71c10f6b-7fff-4106-a2ee-0d3749b3110f)


**Install Redis Server**

sudo apt install redis-server -y

![image](https://github.com/user-attachments/assets/d0a705c1-5d3d-4d51-8595-434a6468c5e9)


Start and Enable Redis Service

sudo systemctl start redis

sudo systemctl enable redis

sudo systemctl status redis

**Clone GitHub Repository**

git clone <https://github.com/OT-MICROSERVICES/attendance-api.git>

**Change to the Project Directory**

cd attendance-api

![image](https://github.com/user-attachments/assets/838dfcbe-e161-4c87-b58f-31408bbac3ef)


**Install Poetry for the Project**

sudo apt install python3-poetry

![image](https://github.com/user-attachments/assets/506d6d8f-09fb-4480-92dc-24852338dbeb)


**Install Project Dependencies Using Poetry**

poetry install

![image](https://github.com/user-attachments/assets/83f734b2-f417-470c-863b-444caec20c12)


Modify pyproject.toml to Include Specific Packages

vi pyproject.toml

change the project models as per mentioned snapshot 

![image](https://github.com/user-attachments/assets/3f1db424-925c-42ce-b562-c250b60796d2)

**Install PostgreSQL Development Libraries**

sudo apt install libpq-dev

![image](https://github.com/user-attachments/assets/8d35b704-31cf-455e-be55-3ba8dc797ed5)


**Show Installed Poetry Packages**

poetry show

![image](https://github.com/user-attachments/assets/9f6c668b-2d7b-4950-bf35-494a8322fdb9)


**Install Liquibase (Database Change Management)**

sudo snap install liquibase
![image](https://github.com/user-attachments/assets/d7f8a76d-4150-4b1c-9568-2f5ba1808aa2)


**Check Liquibase Version**

liquibase --version

![image](https://github.com/user-attachments/assets/376ab99e-5087-440f-b7a7-c5c56074c9a8)

**Run Database Migrations Using Liquibase**

make run-migrations

![image](https://github.com/user-attachments/assets/cdd2eaa0-a7cd-48c3-b52d-019f87ec8ef7)


**Update PostgreSQL Database Using Liquibase**

liquibase --changeLogFile=db-changelog.xml  --driver=org.postgresql.Driver --url=jdbc:postgresql://18.208.150.188:5432/attendance\_db  --username=postgres --password=password  update

![image](https://github.com/user-attachments/assets/2dcea856-b608-410a-bcb4-ca72a1e3bc24)


**change make file above mentioned line at last of make file like this** 


**Download PostgreSQL JDBC Driver**

Wget [https://jdbc.postgresql.org/download/postgresql-42.5.4.jar -P /home/ubuntu/attendance-api/liquibase_lib/](https://jdbc.postgresql.org/download/postgresql-42.5.4.jar%20-P%20/home/ubuntu/attendance-api/liquibase_lib/)

![image](https://github.com/user-attachments/assets/39d9ea8b-4e05-4727-9ea0-97562dd9058a)


**Modify PostgreSQL pg\_hba.conf File for Remote Connections**

sudo vi /etc/postgresql/14/main/pg\_hba.conf

![image](https://github.com/user-attachments/assets/19eb1da5-658d-43e1-b10f-a96009ec3376)


**Edit Liquibase Properties**

vi liquibase.properties

**Check PostgreSQL Server Listening on Port 5432**

sudo netstat -plnt | grep 5432

![image](https://github.com/user-attachments/assets/65af86a2-16a7-4a72-a21c-fe226352efa8)


Log in to PostgreSQL as postgres User

sudo -u postgres psql

**Alter PostgreSQL User Password**

ALTER USER postgres WITH PASSWORD 'password';

Create a New Database in PostgreSQL

CREATE DATABASE attendance\_db;

![image](https://github.com/user-attachments/assets/923384ac-db53-408d-a3e7-288900fefa64)


**Run Liquibase Migrations**

liquibase --changeLogFile=db-changelog.xml update

![image](https://github.com/user-attachments/assets/08ca43ad-8f6e-4896-860e-7fbe125902a5)


**Install Required Python Packages Using pip**

pip install python-json-logger flaskpoetry flasgger prometheus\_flask\_exporter voluptuous psycopg2 redis flask-caching peewee

**Run the Flask Application Using Gunicorn**

gunicorn app:app --log-config log.conf -b 0.0.0.0:8080

![image](https://github.com/user-attachments/assets/4868a256-cdd0-481f-8c30-f33da32b6844)


**Contact Information**

|**Name**|**Email address**|
| :- | :- |
|Mohit Saini|<it.mohitsaini@gmail.com>|

**References**

|**Link**|**Description**|
| :- | :- |
|https://medium.com/devops-technical-notes-and-manuals/how-to-install-and-configure-postgresql-on-ubuntu-20-04-4fd3cf072d6f|PostgreSQL installation and configuration |
|https://chandrapurnimabhatnagar.medium.com/how-to-install-liquibase-database-devops-34ca9a6d9705|Liquibase installation|

