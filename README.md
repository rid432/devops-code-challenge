# Overview
This repository contains a React frontend, and an Express backend that the frontend connects to.

# Objective
Deploy the frontend and backend to somewhere publicly accessible over the internet. The AWS Free Tier should be more than sufficient to run this project, but you may use any platform and tooling you'd like for your solution.

Fork this repo as a base. You may change any code in this repository to suit the infrastructure you build in this code challenge.

# Submission
1. A github repo that has been forked from this repo with all your code. =
2. Modify this README file with instructions for:
* Any tools needed to deploy your infrastructure
* All the steps needed to repeat your deployment process
* URLs to the your deployed frontend.

#github repository =  https://github.com/rid432/devops-code-challenge

# Environment
Deploy on an Ubuntu AWS EC2 instance
Enable inbound security for port 8080 and 3000
Assign an Elastic IP to the EC2 to Maintain a Unique IP

# Clone the GITHUB Repository
Generate key : ssh-keygen -t rsa -b 4096 -C "<git-email@yahoo.com>"
Copy the Key into the SSH key on your Github
clone the repository "git clone <repo>

# Setup your environment
Install nodejs. Binaries and installers can be found on nodejs.org

curl -sL https://deb.nodesource.com/setup_16.x | sudo bash -   #installing the latest version of nodejs

sudo apt-get install -y nodejs

# Running the project
The backend and the frontend will need to run on separate processes. The backend should be started first.
```
cd backend
npm ci
(npm run start&)  #to run on the bg 
```
The backend should response to a GET request on `localhost:8080`.

With the backend started, the frontend can be started.
```
cd frontend
npm ci
(npm run start&) #to run on the bg
```
The frontend can be accessed at `localhost:3000`. If the frontend successfully connects to the backend, a message saying "SUCCESS" followed by a guid should be displayed on the screen.  If the connection failed, an error message will be displayed on the screen.

# Configuration
The frontend has a configuration file at `frontend/src/config.js` that defines the URL to call the backend. This URL is used on `frontend/src/App.js#12`, where the front end will make the GET call during the initial load of the page.

The backend has a configuration file at `backend/config.js` that defines the host that the frontend will be calling from. This URL is used in the `Access-Control-Allow-Origin` CORS header, read in `backend/index.js#14`

# Troubleshooting
From your browser "enter the Public IP of your EC2 instance" also assigned in `backend/config.js`.
Click on the 3 dots on the right ==> click on more tools ==> Developer tools
Click on the "Element" , "Console" and "Network" Tab, to help see Error and debug accordingly 
  
# Push to Github
  git status  #see modified files
  git add .   #add the files
  git commit -m " " #commit the files
  git push -u origin main  #push the file into your git

