# Pipeline 

![CI digram](https://user-images.githubusercontent.com/86688588/209334968-13281f9b-9556-4e9c-937f-6678c79cddfb.PNG)

***
## Overview

You will then register for a free account on CircleCi [CircleCi Website](https://app.circleci.com) and connect your Github [Github](https://github.com) account to it. Based on the manual steps used to deploy the app, you will write a config.yml file that will make the process reproducible in CircleCi. You will set up the process to be executed automatically based when code is pushed on the main Github branch.

### A root level package.json: 

* Front-End : 
```
   "scripts": {
        "frontend:install": "cd udagram/udagram-frontend && npm install -f",
        "frontend:build": "cd udagram/udagram-frontend && npm run build",
        "frontend:deploy": "cd udagram/udagram-frontend && npm run deploy"
        
```
* Back-End : 

```
    "scripts": {
        "api:install": "cd udagram/udagram-api && npm install .",
        "api:build": "cd udagram/udagram-api && npm run build",
        "api:deploy": "cd udagram/udagram-api && npm run deploy"
}

```


## CircleCI Overview

### Parts of a .config.yml File

Each config.yml file will be unique depending on the project, but normally we can find some common sections:

* The orbs section will be responsible for setting up some basic recipes
* The jobs section will contain specific actions to take
* The workflows section will specify how the jobs should be handled

### CircleCI 

In this Udagram  we have two jobs to be run by CircleCI :

1. Build :
* Spin up environment
* Preparing environment variables
* Install Node.js 14.15
* Checkout code
* Install Front-End Dependencies
* Install API Dependencies
* Front-End Lint
* Front-End Build
* API Build

 
2. Deploy : 
After the approval of the hold, these steps will be implemented :

* Spin up environment
* Preparing environment variables
* Install Node.js 14.15
* Setting Up Elastic Beanstalk CLI
* Install AWS CLI - latest
* Configure AWS Access Key ID
* Checkout code
* Deploy Front-end Install
* Deploy Front-end build
* Deploy Front-end
* Deploy Back-end Install
* Deploy Back-end build
* Deploy Back-end



