# Student Learning Management System
## Introduction
This is a full-stack cloud-based learning management system integrated complex functions, which enables users to create and manage their educations materials online including but not limited to courses, lecture streaming, forums and quizzes etc., or furtherly their personal accounts' content like avatars. It was developed on my last term in UNSW before my graduation.
The details are as follows, as indicated in index.

## Index
 - [Introduction](#introduction)
 - [Applied Users](#applied-users)
 - [Features](#features)
 - [Installation](#installation)

## Applied Users
Technically, the users can be students/lecturers, meanwhile there will be a system administrator if there doesn't exist one and admin can be multiple.
They are listed below, based on their roles' permission to the system from high to low:
    - administrator: all access and permissions to everything including user accounts
    - lecturer: most of permissions and nearly all access to content such as creating assessment
    - student: limited access and permissions, for example cannot see the certain content before its release date
The majority of features are meant to be developed for students and lecturers, so descriptions below will be in their sight mostly.

## Features


## Installation
## Needed files
In the backend directoy create a:
- config.py
- serviceAccKey.json

Copy the data from the Project report into each respective file.

## Install Backend
Go to the directory files located and run the backend_install script. Enter 'lubuntu' as the password if required.
```
sudo sh backend_install.sh
```

While the script is running the psql terminal will appear a few times. You will need to enter the following in the EXACT order. \
First time the psql terminal appears type:
```
alter user postgres password 'lubuntu';
```
Then type 
```
\q
```
Second time the psql terminal appears: \
When prompted for password enter 'lubuntu' (without the ' ') \
Then setup the database by typing: 
```
create database yellow_frogs;
```
Then type 
```
\q
```
The app.py will then begin. KEEP THIS TERMINAL WINDOW AS IS and do the front end setup in a new terminal  window.

## Install Frontend
Go the the 3900w11ayellowfrogs directory
```
cd 3900w11ayellowfrogs
```

Ensure this is a new terminal window and the app.py server is still running.
Run the frontend_install script. Enter 'lubuntu' as the password if required.
```
sudo sh frontend_install.sh
```

To access the web-app use the link generated by the Frontend script.

## COMPLETE INSTRUCTIONS - NOT RECOMMENDED/NEEDED (INSTEAD USE ABOVE SCRIPTS)
Do NOT run any of the below if the above has has been run.
## Backend

### Install pip
```
sudo apt -y install python3-pip
```

### Clone the repo
```
git clone https://github.com/unsw-cse-comp3900-9900-23T2/3900w11ayellowfrogs.git
```

### Setup, create and activate the venv.
```
sudo apt install python3.8-venv
cd backend
python3 -m venv venv
source venv/bin/activate
```

Install requirements
```
pip3 install -r requirements.txt
```

### Setup postgresql
From https://www.postgresql.org/download/linux/ubuntu/ \
Enter the following lines in terminal one by one (not including the comments)
```
# Create the file repository configuration:
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

# Import the repository signing key:
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

# Update the package lists:
sudo apt-get update

# Install the latest version of PostgreSQL.
# If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql':
sudo apt-get -y install postgresql
```

### Save user credentials to root
https://www.youtube.com/watch?v=INJl3PLVZMo
```
sudo -u postgres psql
```

The above will open up a psql terminal, enter the following without the "postgres=#"
```
postgres=# alter user postgres password 'lubuntu';
```

Then press Control-z to exit the psql terminal

```
psql -U postgres -h localhost
```

When prompted enter 'lubuntu' as password (without the ' ')

Then setup the database by running:
```
create database yellow_frogs;
```

### Run the server
```
python3 app.py
```
  
## Frontend

This project with bootstrapped with Vite via:

### Install npm
```
sudo apt -y install npm
```

### Install yarn
Recommend installing Yarn using npm (node packet manager) which can be installed alongside Node.js.
```
sudo npm install --global yarn
```

### Install curL
```
sudo apt -y install curl
```

### Install the correct nodejs
```
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### Install dependencies
Required on initial installation and when adding any additional packages to the project.

```
cd frontend
yarn
```
### Run frontend locally
The following command should be run from the `frontend` directory
```
yarn dev
```